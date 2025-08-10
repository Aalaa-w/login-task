<template>
  <div class="chat">
    <div class="row">
      <div class="col-md-4">
        <div class="chat__conversations">
          <lazy-chats-chat-sort></lazy-chats-chat-sort>
          <lazy-chats-chat-list></lazy-chats-chat-list>
        </div>
      </div>
      <div class="col-md-8">chats</div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.chat {
  overflow: hidden;
  height: 100vh;
  .col-md-4 {
    padding: 0;
  }
  &__conversations {
    border: 1px solid #ebebeb;
    height: 100vh;
    overflow: auto;
  }
}
</style>
