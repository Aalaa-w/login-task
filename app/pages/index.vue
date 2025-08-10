<template>
  <div class="container d-flex justify-content-center vh-100 form">
    <form class="form__login" @submit.prevent="onSubmit">
      <!-- Logo -->
      <h4 class="text-center mb-4 mt-5">Welcome back</h4>

      <!-- Email -->
      <div class="mb-3">
        <input
          type="email"
          v-model="email"
          class="form-control"
          :class="{ 'form__login__input--error': emailError }"
          placeholder="Email address"
        />
        <div class="text-danger error-massage">{{ emailError }}</div>
      </div>

      <!-- Password -->
      <div class="mb-2">
        <input
          type="password"
          v-model="password"
          class="form-control"
          :class="{ 'form__login__input--error': passwordError }"
          placeholder="Password"
        />
        <!-- <div class="text-danger error-massage">{{ passwordError }}</div> -->
        <small class="text-danger mt-2 form__login__forget"
          ><svg
            xmlns="http://www.w3.org/2000/svg"
            width="12"
            height="12"
            viewBox="0 0 12 12"
            fill="none"
          >
            <g clip-path="url(#clip0_1_61)">
              <path
                d="M6 12C9.31371 12 12 9.31371 12 6C12 2.68629 9.31371 0 6 0C2.68629 0 0 2.68629 0 6C0.00358594 9.31223 2.68777 11.9964 6 12ZM5.50001 3C5.50001 2.72386 5.72386 2.50001 6 2.50001C6.27614 2.50001 6.49999 2.72386 6.49999 3V7.00001C6.49999 7.27615 6.27614 7.5 6 7.5C5.72386 7.5 5.50001 7.27615 5.50001 7.00001V3ZM6 9C6.27614 9 6.49999 9.22385 6.49999 9.49999C6.49999 9.77613 6.27614 9.99998 6 9.99998C5.72386 9.99998 5.50001 9.77613 5.50001 9.49999C5.50001 9.22385 5.72386 9 6 9Z"
                fill="#BF2C25"
              />
            </g>
            <defs>
              <clipPath id="clip0_1_61">
                <rect width="12" height="12" fill="white" />
              </clipPath>
            </defs>
          </svg>
          Forgot password?</small
        >
      </div>

      <!-- Submit -->
      <button
        class="btn btn-dark w-100 mb-3 mt-2 form__login__submit"
        @click="handleLogin"
      >
        Continue
      </button>

      <!-- Signup -->
      <p class="text-center">
        Don't have an account?
        <a href="#" class="form__login__sign-up">Sign up</a>
      </p>

      <!-- Divider -->
      <div class="form__login__divider mb-3">
        <span class="from__login__divider__text px-3">OR</span>
      </div>

      <!-- Social Login -->
      <button class="w-100 mb-2 form__login__socialBtns">
        <img
          src="https://www.svgrepo.com/show/355037/google.svg"
          width="20"
          class="me-2"
        />
        Continue with Google
      </button>
      <button class="w-100 mb-2 form__login__socialBtns">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="20"
          height="20"
          fill="currentColor"
          class="bi bi-apple me-2"
          viewBox="0 0 16 16"
        >
          <path
            d="M11.182.008C11.148-.03 9.923.023 8.857 1.18c-1.066 1.156-.902 2.482-.878 2.516s1.52.087 2.475-1.258.762-2.391.728-2.43m3.314 11.733c-.048-.096-2.325-1.234-2.113-3.422s1.675-2.789 1.698-2.854-.597-.79-1.254-1.157a3.7 3.7 0 0 0-1.563-.434c-.108-.003-.483-.095-1.254.116-.508.139-1.653.589-1.968.607-.316.018-1.256-.522-2.267-.665-.647-.125-1.333.131-1.824.328-.49.196-1.422.754-2.074 2.237-.652 1.482-.311 3.83-.067 4.56s.625 1.924 1.273 2.796c.576.984 1.34 1.667 1.659 1.899s1.219.386 1.843.067c.502-.308 1.408-.485 1.766-.472.357.013 1.061.154 1.782.539.571.197 1.111.115 1.652-.105.541-.221 1.324-1.059 2.238-2.758q.52-1.185.473-1.282"
          />
          <path
            d="M11.182.008C11.148-.03 9.923.023 8.857 1.18c-1.066 1.156-.902 2.482-.878 2.516s1.52.087 2.475-1.258.762-2.391.728-2.43m3.314 11.733c-.048-.096-2.325-1.234-2.113-3.422s1.675-2.789 1.698-2.854-.597-.79-1.254-1.157a3.7 3.7 0 0 0-1.563-.434c-.108-.003-.483-.095-1.254.116-.508.139-1.653.589-1.968.607-.316.018-1.256-.522-2.267-.665-.647-.125-1.333.131-1.824.328-.49.196-1.422.754-2.074 2.237-.652 1.482-.311 3.83-.067 4.56s.625 1.924 1.273 2.796c.576.984 1.34 1.667 1.659 1.899s1.219.386 1.843.067c.502-.308 1.408-.485 1.766-.472.357.013 1.061.154 1.782.539.571.197 1.111.115 1.652-.105.541-.221 1.324-1.059 2.238-2.758q.52-1.185.473-1.282"
          />
        </svg>
        Continue with Apple
      </button>
      <button class="w-100 form__login__socialBtns--phone">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-telephone"
          viewBox="0 0 16 16"
        >
          <path
            d="M3.654 1.328a.678.678 0 0 0-1.015-.063L1.605 2.3c-.483.484-.661 1.169-.45 1.77a17.6 17.6 0 0 0 4.168 6.608 17.6 17.6 0 0 0 6.608 4.168c.601.211 1.286.033 1.77-.45l1.034-1.034a.678.678 0 0 0-.063-1.015l-2.307-1.794a.68.68 0 0 0-.58-.122l-2.19.547a1.75 1.75 0 0 1-1.657-.459L5.482 8.062a1.75 1.75 0 0 1-.46-1.657l.548-2.19a.68.68 0 0 0-.122-.58zM1.884.511a1.745 1.745 0 0 1 2.612.163L6.29 2.98c.329.423.445.974.315 1.494l-.547 2.19a.68.68 0 0 0 .178.643l2.457 2.457a.68.68 0 0 0 .644.178l2.189-.547a1.75 1.75 0 0 1 1.494.315l2.306 1.794c.829.645.905 1.87.163 2.611l-1.034 1.034c-.74.74-1.846 1.065-2.877.702a18.6 18.6 0 0 1-7.01-4.42 18.6 18.6 0 0 1-4.42-7.009c-.362-1.03-.037-2.137.703-2.877z"
          />
        </svg>
        Continue with phone
      </button>

      <!-- Links -->
      <div class="text-center mt-3 small form__login__links mt-5">
        <a href="#">Terms of Use</a>
        <span class="mx-2">|</span>
        <a href="#">Privacy Policy</a>
      </div>
    </form>
  </div>
</template>

<script setup>
import { useForm, useField } from "vee-validate";
import * as yup from "yup";

const schema = yup.object({
  email: yup
    .string()
    .required("Email is required")
    .email("Invalid email address"),
  password: yup
    .string()
    .required("Password is required")
    .min(6, "Password must be at least 6 characters"),
});

const { handleSubmit } = useForm({
  validationSchema: schema,
});

const { value: email, errorMessage: emailError } = useField("email");
const { value: password, errorMessage: passwordError } = useField("password");

const onSubmit = handleSubmit((values) => {
  console.log("Form Data:", values);
});
</script>
<style scoped lang="scss">
.form {
  &__login {
    max-width: 300px;
    width: 100%;
    h4 {
      font-family: var(--font-secondary);
      font-weight: 600;
    }
    &__submit {
      border-radius: var(--standard-border);

      height: var(--standard-height);
    }
    &__sign-up {
      text-decoration: none;
      color: var(--color-primary);
      font-weight: 500;
    }
    &__forget {
      font-size: 12px;
    }
    &__divider {
      display: flex;
      align-items: center;
      text-align: center;
      color: #000;
      font-weight: 500;
      &::before,
      &::after {
        content: "";
        flex: 1;
        border-bottom: 1px solid #000;
        opacity: 6%;
      }
    }

    &__socialBtns {
      border-radius: var(--standard-border);
      font-size: 14px;
      height: var(--standard-height);
      border: 1px solid var(--color-border);
      background: #fff;
      &--phone {
        background: #f2f2f3;
        border-radius: var(--standard-border);
        font-size: 14px;
        height: var(--standard-height);
        border: 1px solid var(--color-border);
      }
    }
    &__links {
      font-weight: 600;

      a {
        color: var(--color-secondary);
      }
      span {
        color: var(--color-secondary);
      }
    }
    &__input {
      &--error {
        border: 1px solid var(--color-danger);
         &::placeholder {
          color: var(--color-danger);
          opacity: 0.8;
        }
      }
      
    }
    .error-massage {
      font-size: 12px;
    }
  }
}
</style>
