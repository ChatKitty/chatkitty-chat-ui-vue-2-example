<template>
  <div id="app" class="container">
    <div class="header">
      <!-- Your header content -->
      <img alt="ChatKitty logo" src="./assets/logo.png" height="125" width="125">
    </div>
    <div class="chat-ui-wrapper">
      <!-- Chat UI will be rendered here -->
      <div id="chat-ui"></div>
    </div>
  </div>
</template>

<script>
import {loadChatUi, template} from "@chatkitty/ui";

export default {
  name: 'App',
  mounted() {
    loadChatUi({
      widgetId: 'UWiEkKvdAaUJ1xut',
      username: '2989c53a-d0c5-4222-af8d-fbf7b0c74ec6',
      container: {
        height: '100%'
      },
      components: {
        chat: (context) => ({
          menuActions: [],
          onMounted: () => {
            console.log('Chat UI mounted with context: ', context)
          },
          onHeaderSelected: (channel) => {
            console.log(channel)
          },
          onMenuActionSelected: (action) => {
            console.log(action)
          }
        })
      },
      templates: {
        error: ({message}) => template`
        <style>
          .error {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100%;
            padding: 0 20px;
          }

          .error h1 {
            font-size: 24px;
            font-weight: 500;
            margin: 0;
          }

          .error p {
            font-size: 16px;
            margin: 0;
          }
        </style>
        <div class="error">
          <h1>Oops!</h1>
          <p>${message}</p>
        </div>
      `
      },
    }, {
      timeout: 50000,
    })
  }
}
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  height: 100vh; /* Assuming you want to take the full viewport height */
}

.header {
  /* Your header styles */
  display: flex;
  justify-content: center;
  height: 125px;
}

@media (max-width: 600px) {
  .header {
    display: none; /* Hide header on mobile */
  }
}

.chat-ui-wrapper {
  flex: 1; /* This allows the wrapper to take up the remaining space */
  min-height: 0; /* Fixes flexbox sizing issue in some cases */
}

body {
  margin: 0;
}
</style>
