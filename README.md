# Toaster-JS

The vanilla JavaScript ES6 minimalistic easy-to-use toast pup-up messages module.
The solution which "just works" – add the module to your project and go further.

Supported by all major browsers and IE 10+ (requestAnimationFrame support). Safe to use with ReactJS
and other virtual-dom frameworks.

Preview
-------

![Screenshot](https://cloud.githubusercontent.com/assets/4989256/14760552/9480e966-094f-11e6-9425-739e000ffbd2.png)

Features
--------

+ Simple CSS-animated customizable toast pop-ups for any design;
+ Toasts have different types and apply any style you need;
+ Toasts appear and disappear by specifying optional timeout.

Installation & Usage
--------------------

```bash
npm install toaster-js --save-dev
```

```javascript
import { Toast } from "toaster-js";

new Toast("Welcome!");
new Toast("There is no more toasts!", Toast.TYPE_ERROR, Toast.TIME_NORMAL);
```

You can import pre-defined css/scss styles for your toasts. 
There are two files (css/scss) available.

```javascript
import "toaster-js/default.scss"; // or @import "../node_modules/toaster-js/default.scss"; from SCSS
```

You can set up additional options if you need. See the API below.

```javascript
import { configureToasts } from "toaster-js";

configureToasts({
    topOrigin: 0
});
```

API
---

+ [Toast(message, type, timeout)](#toastmessage-type-timeout)
    + [TIME_SHORT](#time-short)
    + [TIME_NORMAL](#time-normal)
    + [TIME_LONG](#time-long)
    + [TYPE_INFO](#type-info)
    + [TYPE_MESSAGE](#type-message)
    + [TYPE_WARNING](#type-warning)
    + [TYPE_ERROR](#type-error)
    + [TYPE_DONE](#type-done)
+ [configureToasts(options)](#configuretoastsoptions)

##### Toast(message, type, timeout)
Creates a new toast pop-up message on the screen. Pass a string `message` to specify the message,
`type` = `Toast.TYPE_*` to specify the type and `timeout` = `Toast.TIME_*` to specify the timeout.
Timeout constant is the number of milliseconds for message to stay, so
`new Toast("test", Toast.TYPE_ERROR, 10000)` message would stay for 10 seconds.

+ TIME_SHORT = 2 seconds
+ TIME_NORMAL = 4 seconds
+ TIME_LONG = 8 seconds
+ TYPE_INFO = "info"
+ TYPE_MESSAGE = "message"
+ TYPE_WARNING = "warning"
+ TYPE_ERROR = "error"
+ TYPE_DONE = "done"

##### configureToasts(options)
Allows to configure some options of the toast. The available optional options are listed below:

```js
configureToasts({
    topOrigin: -100 // [default=0] Y-axis origin of the message. 
});
```
