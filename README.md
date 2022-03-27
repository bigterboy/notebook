# notebook

1. jsconfig.json

{
    "compilerOptions": {
        "baseUrl": "src",
    },
    "include": ["src"]
}

2. Debug with safari
3. 
- (NSURL *)sourceURLForBridge:(RCTBridge *)bridge
{
#if DEBUG
  // return [[RCTBundleURLProvider sharedSettings] jsBundleURLForBundleRoot:@"index" fallbackResource:nil];    // comment this line
  return [NSURL URLWithString: [[[[RCTBundleURLProvider sharedSettings] jsBundleURLForBundleRoot: @"index" fallbackResource:nil] absoluteString] stringByAppendingString:@"&inlineSourceMap=true"]];   // <== add this line
#else
  return [[NSBundle mainBundle] URLForResource:@"main" withExtension:@"jsbundle"];
#endif
}
