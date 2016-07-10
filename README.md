This is a driver for all your [pure-most Cycle apps](https://github.com/cyclejs/most-run) (think [Motorcycle](https://github.com/motorcyclejs/core#merging-with-cyclejs)) displays [humane.js](http://wavded.github.io/humane-js/) notifications.

You don't have to include any CSS for humane.js themes, they will be loaded asynchronously from cdnjs.

### Install

```
npm install --save cycle-notification-most-driver
```


### Use

```javascript
import most from 'most'
import Cycle from '@cycle/most-run'
import {makeNotificationDriver} from 'cycle-notification-most-driver'

Cycle.run(app, {
  NOTIFICATION: makeNotificationDriver({
    timeout: 4000,
    baseCls: 'humane-bigbox'
  })
})

function app () {
  return {
    NOTIFICATION: most.from([
      'normal notification',
      ['info notification', 'info'],
      ['error notification with custom opts', 'error', {timeout: 8000}],
      ['custom', {addnCls: 'custom-class'}],
      {text: 'this works too', timeout: 1000, clickToClose: true}
    ])
  }
}
```
