<template>
  <div class="login-box">
    <a-form :model="form" :wrapperCol="{ span: 24 }" @finish="login" class="login-form">
      <h1>虚拟仿真实验平台</h1>
      <a-form-item :required="true" name="username">
        <a-input
          v-model:value="form.username"
          autocomplete="new-username"
          placeholder="请输入用户名或邮箱"
          class="login-input"
        />
      </a-form-item>
      <a-form-item :required="true" name="password">
        <a-input
          v-model:value="form.password"
          autocomplete="new-password"
          placeholder="请输入登录密码"
          class="login-input"
          type="password"
        />
      </a-form-item>
      <a-button htmlType="submit" class="login-button bg-primary-600" type="primary" :loading="loading" @click="$event=>{login}">
        登录
      </a-button>
      <a-divider></a-divider>
      <div class="terms">
        登录即代表您同意我们的
        <span class="font-bold">用户条款 </span>、<span class="font-bold"> 数据使用协议 </span>、以及
        <span class="font-bold">Cookie使用协议</span>。
      </div>
    </a-form>
  </div>
</template>
<script lang="ts" setup>
  import { reactive, ref, onMounted } from 'vue';
  import { useAccountStore } from '@/store';
  import useThemeStore from 'stepin/es/theme-editor/store';

  export interface LoginFormProps {
    username: string;
    password: string;
  }

  const { setBgSeriesColors } = useThemeStore();

  onMounted(() => {
    setBgSeriesColors({ 'bg-base': '#fff' }, true, '.login-box');
  });

  const loading = ref(false);

  const form = reactive({
    username: undefined,
    password: undefined,
  });

  const emit = defineEmits<{
    (e: 'success', fields: LoginFormProps): void;
    (e: 'failure', reason: string, fields: LoginFormProps): void;
  }>();

  const accountStore = useAccountStore();
  function login(params: LoginFormProps) {
    // console.log(params)
    loading.value = true;
    accountStore
      .login(params.username, params.password)
      .then((res) => {
        emit('success', params);
      })
      .catch((e) => {
        emit('failure', e.message, params);
      })
      .finally(() => (loading.value = false));
  }


</script>
<style lang="less" scoped>
  .login-box {
    .login-form {
      width: 440px;
      @apply py-12 h-fit border-border px-10 rounded-sm text-text bg-container;
      .third-platform {
        .third-title {
          @apply text-left mb-md;
          font-size: 16px;
        }
        .third-list {
          @apply flex;
          .icon {
            @apply text-gray-400 flex-1 hover:text-primary-500 cursor-pointer;
            font-size: 28px;
            &.wechat {
              @apply hover:text-green-600;
            }
            &.twitter {
              @apply hover:text-blue-400;
            }
            &.qq {
              @apply hover:text-red-600;
            }
          }
        }
      }
      .login-input,
      .login-button {
        @apply rounded;
        margin-top: 16px;
        height: 40px;
        width: 100%;
      }
      .terms {
      }
    }
  }
</style>
