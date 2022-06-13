# NOTEBOOK

> NOTE FOR REACT NATIVE

## Introduction

## NOTE
1. Redux 

Action just a javascript object describe a action


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
https://stackoverflow.com/questions/66664209/how-can-i-use-forwardref-in-react