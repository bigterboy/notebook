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
