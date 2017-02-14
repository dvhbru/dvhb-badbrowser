# Bad Browser

## Install
```
npm i @dvhb/badbrowser
```

## Demo
http://dvhbru.github.io/badbrowser/

## Using
Put html for your alert windows in `/alerts/` with this pattern:
```
alerts/
 ru.html
 ru.mobile.html
 en.html
 en.mobile.html
 ...
```

```js
import badbrowser from '@dvhb/badbrowser'
```

Call `badbrowser.init`

```js
badbrowser.init({
    // path to your html alerts
    // could be a function:
    // function (ua) {
    //   return '/alerts/' + lang + '.html'
    // }
    path: '/alerts/en.html',
    // if `false` then user's choice will be saved in the cookies
    // and alert window will not be showen next time
    ignoreChoice: false,
    // Min version of browser that will be supported
    supported: {
        // user of chrome v.39 will see an alert winodw
        chrome: 42,
        firefox: 38,
        ie: 9,
        opera: 26,
        opera_mini: 7,
        safari_mobile: 7,
        android: 10,
        safari: 6,
        // if `false`, will show alert for any mobile browser
        mobile: false
    }
})
```

Instead of specifying *supported* property you can specify *unsupported* browsers:
```js
badbrowser.init({
    unsupported: {
        // the same as supported.chrome = 40
        chrome: 39,
        // the same as supported.firefox = 34
        firefox: 33,
        // will show alert for any mobile browser
        mobile: true
    }
})
```

# LICENSE
[MIT License](./LICENSE) © [dvhb](http://dvhb.ru/)