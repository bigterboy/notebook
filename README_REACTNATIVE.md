# NOTEBOOK

> NOTE FOR REACT NATIVE

## Introduction

## REACT_NATIVE

1. Change to use relative path
Create file `jsconfig.json`
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/components/*": ["src/view/components/*"]
    }
  }
}

2. Debug via safari: update file AppDelegate

- (NSURL *)sourceURLForBridge:(RCTBridge*)bridge
{
if DEBUG

  // return [[RCTBundleURLProvider sharedSettings] jsBundleURLForBundleRoot:@"index" fallbackResource:nil];    // comment this line
  return [NSURL URLWithString: [[[[RCTBundleURLProvider sharedSettings] jsBundleURLForBundleRoot: @"index" fallbackResource:nil] absoluteString] stringByAppendingString:@"&inlineSourceMap=true"]];   // <== add this line
}

3. How to remove all console.log `https://reactnative.dev/docs/performance/#using-consolelog-statements`
Using console.log statements
When running a bundled app, these statements can cause a big bottleneck in the JavaScript thread. This includes calls from debugging libraries such as redux-logger, so make sure to remove them before bundling. You can also use this babel plugin that removes all the console.* calls. You need to install it first with npm i babel-plugin-transform-remove-console --save-dev, and then edit the .babelrc file under your project directory like this: