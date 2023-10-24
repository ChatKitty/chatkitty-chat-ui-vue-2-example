<template>
  <div id="app" class="container">
    <div class="header">
      <!-- Your header content -->
      <img alt="ChatKitty logo" src="./assets/logo.png">
    </div>
    <div class="chat-ui-wrapper">
      <!-- Chat UI will be rendered here -->
      <div id="chat-ui"></div>
    </div>
  </div>
</template>

<script>
import { loadChatUi } from "@chatkitty/ui";

export default {
  name: 'App',
  mounted() {
    loadChatUi({
      widgetId: 'UWiEkKvdAaUJ1xut',
      username: '2989c53a-d0c5-4222-af8d-fbf7b0c74ec6',
      container: {
        height: '100%'
      },
      chatComponent: (context) => ({
        menuActions: [
          {
            name: 'invite-user',
            title: `Invite User (${context.locale})`
          },
          {
            name: 'remove-user',
            title: `Remove User (${context.locale})`
          },
          {
            name: 'delete-channel',
            title: `Delete Channel (${context.locale})`
          }
        ],
        onMounted: () => {
          console.log('Chat UI mounted with context: ', context)
        },
        channelDetailsHandler: (channel) => {
          console.log(channel)
        },
        menuActionHandler: (action) => {
          console.log(action)
        }
      }),
      onNotificationReceived: (notification) => {
        console.log(notification)
      }
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
  height: 200px;
}

.chat-ui-wrapper {
  flex: 1; /* This allows the wrapper to take up the remaining space */
  min-height: 0; /* Fixes flexbox sizing issue in some cases */
}

body {
  margin: 0;
}
</style>
