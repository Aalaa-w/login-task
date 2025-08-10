<template>
  <div class="chat__conversations__body px-3">
    <!-- Conversations List -->
    <div
      v-for="(chat, index) in chats"
      :key="index"
      class="d-flex align-items-center py-2 border-bottom"
    >
      <!-- Avatar -->
      <img
        :src="chat.image"
        alt=""
        class="rounded-circle me-3"
        width="50"
        height="50"
      />

      <!-- Content -->
      <div class="flex-grow-1">
        <div class="d-flex justify-content-between mb-2">
          <small class="text-muted">{{ chat.company }}</small>
          <span class="status">
            <span
              class="rounded-pill"
              :class="chat.type === 'General Info' ? 'primary' : 'warning'"
            ></span>
            {{ chat.type }}
          </span>
        </div>
        <div class="d-flex justify-content-between">
          <h6>{{ chat.name }}</h6>
          <small class="text-muted">{{ chat.time }}</small>
        </div>
        <div class="d-flex justify-content-between">
          <p class="mb-0 text-muted small">{{ chat.message }}</p>
          <span v-if="chat.count" class="badge">{{ chat.count }}</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import userImage from "@/assets/images/user.png";
const chats = [
  {
    image: userImage,
    company: "Chevrolet Alghanim",
    name: "Ahmed Salem",
    type: "General Info",
    message: "Hello Ahmed, this is Sara from Chevrolet...",
    time: "15 min",
    count: 2,
  },
  {
    image: userImage,
    company: "Zain Telecom",
    name: "Yousef Al-Mutairi",
    type: "Complain",
    message: "Hello Yousef, a quick reminder about our new...",
    time: "Yesterday",
    count: 5,
  },
  {
    image: userImage,
    company: "Chevrolet Alghanim",
    name: "Ahmed Salem",
    type: "General Info",
    message: "Hello Ahmed, this is Sara from Chevrolet...",
    time: "15 min",
    count: 2,
  },
  {
    image: userImage,
    company: "Zain Telecom",
    name: "Yousef Al-Mutairi",
    type: "Complain",
    message: "Hello Yousef, a quick reminder about our new...",
    time: "Yesterday",
    count: 5,
  },
  {
    image: userImage,
    company: "Chevrolet Alghanim",
    name: "Ahmed Salem",
    type: "General Info",
    message: "Hello Ahmed, this is Sara from Chevrolet...",
    time: "15 min",
    count: 2,
  },
  {
    image: userImage,
    company: "Zain Telecom",
    name: "Yousef Al-Mutairi",
    type: "Complain",
    message: "Hello Yousef, a quick reminder about our new...",
    time: "Yesterday",
    count: 5,
  },
  {
    image: userImage,
    company: "Chevrolet Alghanim",
    name: "Ahmed Salem",
    type: "General Info",
    message: "Hello Ahmed, this is Sara from Chevrolet...",
    time: "15 min",
    count: 2,
  },
  {
    image: userImage,
    company: "Zain Telecom",
    name: "Yousef Al-Mutairi",
    type: "Complain",
    message: "Hello Yousef, a quick reminder about our new...",
    time: "Yesterday",
    count: 5,
  },
];
</script>

<style lang="scss" scoped>
.chat {
  &__conversations {
    &__body {
      .badge {
        background: var(--color-primary);
        height: fit-content;
        border-radius: 50%;
      }
      .status {
        border: 1px solid #ebebeb;
        padding: 4px 8px;
        border-radius: 20px;
        display: flex;
        font-size: 10px;
        align-items: center;
        gap: 5px;
        font-weight: 500;
        .rounded-pill {
          width: 7px;
          height: 7px;
        }
        .rounded-pill.primary {
          background: var(--color-primary);
        }
        .rounded-pill.warning {
          background: var(--color-warning);
        }
      }
    }
  }
}
</style>
