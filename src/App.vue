<script setup lang="ts">
import {ref} from "vue"
const msg = ref("")
const handleInput=(e:Event)=> {
  msg.value = (e.target as HTMLDivElement).innerText
}
</script>

<template>
  <div class="body">
    <div class="message">
      {{ msg }}
    </div>
    <div class="textarea-box">
      <div class="textarea-top"></div>
      <div style="padding: 0 25px;height: calc(100% - 3px);">
        <div class="content" contenteditable="true" @input="handleInput"></div>
        <div class="textarea-bottom">
          <div class="button">发送</div>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="less" scoped>
.body {
  width: 100vw;
  height: 100vh;
  background-color: #ffffff;

  .message {
    width: 100%;
    height: calc(100% - 250px);
  }

  .textarea-box {
    overflow: hidden;
    width: 100%;
    height: 250px;

    .textarea-top {
      cursor: pointer;
      width: 100%;
      height: 3px;
      background-color: #33333333;
    }

    .content {
      outline: none;
      padding: 10px;
      height: calc(100% - 3px - 80px);
      border: 1px solid #33333366;
      background-color: #ffffff;
      margin-top: 15px;
    }

    .textarea-bottom {
      height: 60px;
      display: flex;
      justify-content: flex-end;
      align-items: center;
    }
  }
}
</style>