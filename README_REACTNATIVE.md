# NOTEBOOK

> NOTE FOR REACT NATIVE

## Introduction

## NOTE

## REACT_NATIVE

1. Change to use relative path

`yarn add babel-plugin-module-resolver`

Create file `jsconfig.json`
{
"compilerOptions": {
"baseUrl": ".",
"paths": {
"@/components/_": ["src/view/components/_"]
}
}
}

2. Debug via safari: update file AppDelegate

- (NSURL _)sourceURLForBridge:(RCTBridge_)bridge
  {
  if DEBUG

  // return [[RCTBundleURLProvider sharedSettings] jsBundleURLForBundleRoot:@"index" fallbackResource:nil];    // comment this line
return [NSURL URLWithString: [[[[RCTBundleURLProvider sharedSettings] jsBundleURLForBundleRoot: @"index" fallbackResource:nil] absoluteString] stringByAppendingString:@"&inlineSourceMap=true"]]; // <== add this line
  }

3. use `import memoize from "memoize-one";`

class Example extends Component {
// State only needs to hold the current filter text value:
state = { filterText: "" };

// Re-run the filter whenever the list array or filter text changes:
filter = memoize(
(list, filterText) => list.filter(item => item.text.includes(filterText))
);

handleChange = event => {
this.setState({ filterText: event.target.value });
};

render() {
// Calculate the latest filtered list. If these arguments haven't changed
// since the last render, `memoize-one` will reuse the last return value.
const filteredList = this.filter(this.props.list, this.state.filterText);

    return (
      <Fragment>
        <input onChange={this.handleChange} value={this.state.filterText} />
        <ul>{filteredList.map(item => <li key={item.id}>{item.text}</li>)}</ul>
      </Fragment>
    );

}
}

4. Fix error request api NETWORK ENROL WITH API HTTP

update file Info.plist

<key>NSAppTransportSecurity</key>
<dict>
<key>NSAllowsArbitraryLoads</key>
<true/>
<key>NSExceptionDomains</key>
<dict>
<key>localhost</key>
<dict>
<key>NSTemporaryExceptionAllowsInsecureHTTPLoads</key>
<true/>
</dict>
</dict>
</dict>

5. How to use ref
   <https://stackoverflow.com/questions/66664209/how-can-i-use-forwardref-in-react>

6. How to remove all console.log `https://reactnative.dev/docs/performance/#using-consolelog-statements`
   Using console.log statements
   When running a bundled app, these statements can cause a big bottleneck in the JavaScript thread. This includes calls from debugging libraries such as redux-logger, so make sure to remove them before bundling. You can also use this babel plugin that removes all the console.\* calls. You need to install it first with npm i babel-plugin-transform-remove-console --save-dev, and then edit the .babelrc file under your project directory like this:

7. Learn

useEffect, useMemo, useCallback, useRef

8. Life cycle

- Mounting
  constructor()
  static getDerivedStateFromProps()
  render()
  componentDidMount()

- Updating
  static getDerivedStateFromProps()
  shouldComponentUpdate()
  render()
  getSnapshotBeforeUpdate()
  componentDidUpdate()

- Unmounting
  componentWillUnmount()

9. Layout style
   `https://reactnative.dev/docs/layout-props`

## NOTE ANIMATED

1. `useNativeDriver: true`
   thì animated sẽ dc chạy trên native thread chứ không chạy trên js thread nhưng native thread chỉ support một số thuộc tính mà không gây thay đổi layout của bạn: transform, opacity. Còn những cái như margin, flex, backgroundColor, ...

2. `interpolate` để convert ra thông số phù hợp với input cho trong 1 khoản

```javascript
 opacity: animatedValue.interpolate({
            inputRange: [0, 100],
            outputRange: [1, 0],
}),
```

emulator @Pixel_C_API_28

## Reset React Native
Clear:
1. `npm start -- --reset-cache`
2. `pod deintegrate`

## Config

`adb devices`
`adb -s <device name> reverse tcp:8081 tcp:8081`


```Javascript
adb shell input text "RR"   // reload 
adb shell input keyevent 82 // open dialog menu on android
cd android && ./gradlew clean && cd ..
npx react-native start --reset-cache
pod deintegrate
```

## Set up firebase 

```pod
  # pod 'Firebase', :modular_headers => true
  # pod 'FirebaseCore', :modular_headers => true
  pod 'GoogleUtilities', :modular_headers => true
  # pod 'FirebaseCoreExtension', :modular_headers => true
  # pod 'FirebaseFirestoreInternal', :modular_headers => true
  $RNFirebaseAsStaticFramework = true
```

## Run ios with specific iphone version

```sh
npx react-native run-ios --simulator="iPhone X"
xcrun simctl list devices # get all current devices
```
## Run android with specific android devices
```sh
adb devices # list all devices
npx react-native run-android --deviceId <device_id>
```


## Can debug android with cable
```
adb reverse tcp:8081 tcp:8081
```