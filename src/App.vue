<template>
  <div id="app" class="container">
    <div class="header">
      <!-- Your header content -->
      <img alt="ChatKitty logo" src="./assets/logo.png">
    </div>
    <div class="chat-ui-wrapper">
      <!-- Chat UI will be rendered here -->
      <ChatWidget id="UWiEkKvdAaUJ1xut" username="2989c53a-d0c5-4222-af8d-fbf7b0c74ec6" height="100%"/>
    </div>
  </div>
</template>

<script>
import {ChatWidget} from '@chatkitty/chat-ui-vue2'

export default {
  name: 'App',
  components: {
    ChatWidget
  }
}
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  height: 100vh;  /* Assuming you want to take the full viewport height */
}

.header {
  /* Your header styles */
  display: flex;
  justify-content: center;
  height: 200px;
}

.chat-ui-wrapper {
  flex: 1; /* This allows the wrapper to take up the remaining space */
  min-height: 0; /* Fixes flexbox sizing issue in some cases */
}
</style>
