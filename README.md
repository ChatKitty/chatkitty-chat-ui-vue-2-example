# ChatKitty Chat UI Vue 2 Example

This is an example project that demonstrates how to integrate ChatKitty's Chat UI with a Vue 2 application. ChatKitty provides a fully-featured chat interface out-of-the-box and this project aims to make the integration with Vue 2 as seamless as possible.

## Features

- Fully functional chat interface
- Easy to customize
- Real-time updates

## Prerequisites

- Node.js (>= 12.x)
- npm (>= 6.x)

## Installation

1. Clone this repository

    ```bash
    git clone https://github.com/ChatKitty/chatkitty-chat-ui-vue-2-example.git
    ```

2. Navigate to the project directory

    ```bash
    cd chatkitty-chat-ui-vue-2-example
    ```

3. Install the dependencies

    ```bash
    npm install
    ```

## Usage

1. Start the development server
    ```bash
    npm run serve
    ```

This will start the development server, and you can navigate to `http://localhost:8081` to see the chat interface in action.

## Configuration

In the `App.vue` file, a div container with the ID `chat-ui` is specified as the location where the ChatKitty UI will be rendered.

```html
<div id="chat-ui"></div>
```

This div container acts as a placeholder where the ChatKitty chat interface will be dynamically loaded and displayed. When calling the `loadChatUi` function during the Vue component's `mounted` lifecycle hook, the chat interface will be rendered within this div container.

It's essential to ensure this container is present in your Vue template and properly styled, so the chat interface displays correctly within your application layout.

The following properties are passed to `loadChatUi`:

- `widgetId`: Your ChatKitty widget UI identifier
- `username`: The unique username for the chat session
- `container`: Object specifying the container properties, e.g., `id` (of the placeholder div), `height`, `width`

Furthermore, you can customize the chat components and handle different actions, such as mounting the chat UI, handling channel details, and handling menu actions.

For example,

```javascript
loadChatUi({
  widgetId: 'UWiEkKvdAaUJ1xut',
  username: '2989c53a-d0c5-4222-af8d-fbf7b0c74ec6',
  container: {
    height: '100%'
  },
  ...
});
```

## Customization

The container styles can be customized. Here's an example:

```css
.container {
  display: flex;
  flex-direction: column;
  height: 100vh;  
}

.header {
  display: flex;
  justify-content: center;
  height: 200px;
}

.chat-ui-wrapper {
  flex: 1;
  min-height: 0; 
}
```

To customize the chat widget, use the [ChatKitty Platform API](https://chatkitty.com/docs/api).

`PATCH` `https://api.chatkitty.com/widgets/{id}`
```
Content-Type: application/json+merge-patch
```
```json
{
  "styles": {
    "$version": "0.0.1",
    "base-theme": "light",
    "overrides": {
      ...
    }
  }
}
```

The complete list of styles that can be customized can be found [here](https://chatkitty.com/docs/ui/schemas/styles).

## Demo Dependencies

- `vue: ^2.6.14`
- `@chatkitty/ui: ^1.2.0`

## License

This project is licensed under the MIT License.

For any issues, please [create an issue](https://github.com/ChatKitty/chatkitty-chat-ui-vue-2-example/issues) on GitHub.
