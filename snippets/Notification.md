### Notification

Renders a notification component.

Use the `React.useState()` to initialize the `isVisible` state variable to `true`.
Use an object, `style`, to hold the styles for notification div and the notification close button.
Return a notification div that is based on `isVisible`. When the close button's `onClick` event is fired, the `isVisible` is set to false, which dismisses the notification.

```jsx
function Notification({ title, message }) {
  const [isVisible, setVisible] = React.useState(true);

  const style = {
    notificationWrapper: {
      position: "absolute",
      background: "#e2e2e2",
      padding: "20px"
    },
    closeBtn: {
      position: "absolute",
      right: "10px",
      cursor: "pointer"
    }
  };

  return (
    isVisible && (
      <div style={style.notificationWrapper}>
        {title}
        <span style={style.closeBtn} onClick={() => setVisible(false)}>
          x
        </span>
        <p>{message}</p>
      </div>
    )
  );
}
```

```jsx
ReactDOM.render(<Notification {title: 'Hello World', message: 'Simple notification'} />, document.getElementById('root'));
```

<!-- tags: visual,state  -->

<!-- expertise: 0 -->
