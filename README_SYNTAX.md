

1. New syntax

const array = ['Easy', 'Frontend']
const a = array[0]
const b = array[1]

// easy way
const [a, b] = ['Easy', 'Frontend']


2. Clone new object mà ko bị dính tham chiếu

ES6 spread operator (...)
const a = { name: 'Hau'};    // object
const b = { ... a }

const a = [1, ,2, 3]
const b = [ ... a]


```javascript
    class App extends PureComponent{
        constructor(props){
            super(props)
            this.state = {
                numberList: []
            }
        }

        componentDidMount(){
            const {numberList} = this.state
            numberList.push(1)

            // setState only shallow comparison ( mean compare address)
            this.setState({
                numberList: numberList  // vì cái này là shallow comparison nên dù thay đổi nhưng ko render lại
            })
        }

        render(){
            const {numberList} = this.state
            return(
            <Text>
                {numberList.length}
            </Text>
            ) 
        }

    }
```



config color for console.log
`console.log(`%c${name}: ${rerenderCounter.current}`,'color:#205584; font-weight:bold')`
