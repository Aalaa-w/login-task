<template>
  <div class="chat__conversations__header">
    <div class="chat__conversations__header__search p-3">
      <div class="d-flex justify-content-between align-items-center mb-3">
        <h5 class="chat__conversations__header__title">Conversations</h5>
        <!-- <div class="chat__conversations__header__action">
          <button class="sort-btn" aria-label="Sort conversations">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="14"
              height="14"
              fill="currentColor"
              class="bi bi-arrow-down-up"
              viewBox="0 0 16 16"
            >
              <path
                fill-rule="evenodd"
                d="M11.5 15a.5.5 0 0 0 .5-.5V2.707l3.146 3.147a.5.5 0 0 0 .708-.708l-4-4a.5.5 0 0 0-.708 0l-4 4a.5.5 0 1 0 .708.708L11 2.707V14.5a.5.5 0 0 0 .5.5m-7-14a.5.5 0 0 1 .5.5v11.793l3.146-3.147a.5.5 0 0 1 .708.708l-4 4a.5.5 0 0 1-.708 0l-4-4a.5.5 0 0 1 .708-.708L4 13.293V1.5a.5.5 0 0 1 .5-.5"
              />
            </svg>
          </button>
        </div> -->
      </div>
      <input
        type="search"
        id="conversation-search"
        class="form-control"
        placeholder="Search"
      />
    </div>
    <ul
      class="chat__conversations__header__categories d-flex gap-1 align-items-center px-3 pt-3 flex-wrap"
      aria-label="Conversation categories"
    >
      <li class="selected">All</li>
      <li>Mine <span class="mx-1">9</span></li>
      <li>Ai <span class="mx-1">4</span></li>
      <li>Need to followup <span class="mx-1">2</span></li>
    </ul>
  </div>
</template>
<style lang="scss" scoped>
.chat {
  &__conversations {
    &__header {
      position: sticky;
      top: 0;
      z-index: 99;
      background: #ffff;
      &__search {
        border-bottom: 1px solid #ebebeb;
        input {
          border: 1px solid #ebeee7;
          background: #f7f7f7;
          height: 40px;
          padding: 0 10px;
          &::placeholder {
            color: var(--text-muted);
          }
        }
      }
      &__action {
        .sort-btn {
          border: 1px solid #ebebeb;
          background: #fff;
          border-radius: 50%;
          padding: 5px 10px;
        }
      }
      &__categories {
        list-style: none;
        padding: 0;
        li {
          border: 1px solid #ebebeb;
          padding: 5px 15px;
          font-size: 14px;
          color: var(--text-muted);
          border-radius: 20px;
          &.selected {
            border: 1px solid var(--color-primary);
            color: var(--color-primary);
            background: #4d98e238;
          }
        }
      }
    }
  }
}
</style>
