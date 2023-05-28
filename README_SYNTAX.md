1. New syntax

const array = ['Easy', 'Frontend']
const a = array[0]
const b = array[1]

// easy way
const [a, b] = ['Easy', 'Frontend']

2. Clone new object mà ko bị dính tham chiếu

ES6 spread operator (...)
const a = { name: 'Hau'}; // object
const b = { ... a }

const a = [1, ,2, 3]
const b = [ ... a]

```javascript
class App extends PureComponent {
  constructor(props) {
    super(props);
    this.state = {
      numberList: [],
    };
  }

  componentDidMount() {
    const { numberList } = this.state;
    numberList.push(1);

    // setState only shallow comparison ( mean compare address)
    this.setState({
      numberList: numberList, // vì cái này là shallow comparison nên dù thay đổi nhưng ko render lại
    });
  }

  render() {
    const { numberList } = this.state;
    return <Text>{numberList.length}</Text>;
  }
}
```

config color for console.log
`console.log(`%c${name}: ${rerenderCounter.current}`,'color:#205584; font-weight:bold')`

      console.log(
        '\x1b[31m%s\x1b[0m',
        '🚀 ~ file: versioning.js:29 ~ generateVersioningJSFile ~ error get tag_name from git. You forgot set tag to this commit before build.',
      );


colors = {
    reset: '\033[0m',

    //text color

    black: '\033[30m',
    red: '\033[31m',
    green: '\033[32m',
    yellow: '\033[33m',
    blue: '\033[34m',
    magenta: '\033[35m',
    cyan: '\033[36m',
    white: '\033[37m',

    //background color

    blackBg: '\033[40m',
    redBg: '\033[41m',
    greenBg: '\033[42m',
    yellowBg: '\033[43m',
    blueBg: '\033[44m',
    magentaBg: '\033[45m',
    cyanBg: '\033[46m',
    whiteBg: '\033[47m'
}

      console.log('\x1b[33m%s\x1b[0m','warning', '🚀 ~ file: versioning.js:29 ~ generateVersioningJSFile ~ error get tag_name from git. You forgot set tag to this commit before build.');
