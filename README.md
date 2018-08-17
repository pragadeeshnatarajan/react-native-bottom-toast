
## Getting started  

Add `react-native-bottom-toast` to your js file.   

`import Toast, {DURATION} from 'react-native-bottom-toast'`  

Inside your component's render method, use Toast:   

```javascript
 render() {
         return (
             <View style={styles.container}>
                 ...
                 <Toast ref="toast"/>
             </View>
         );
 }
```

>Note:  Add it in the bottom of the root view.

Then you can use it like this:   

```javascript
 this.refs.toast.show('hello world!');
```

That's it, you're ready to go!  

show a toast, and execute callback function when toast close it:

```javascript
    this.refs.toast.show('hello world!', 500, () => {
        // something you want to do at close
    });
```

Show a toast forever until you manually close it:
```javascript
 this.refs.toast.show('hello world!', DURATION.FOREVER);
```

Or pass an element:
```javascript
    this.refs.toast.show(<View><Text>hello world!</Text></View>);
```

 // later on:
 this.refs.toast.close('hello world!');
```

Optional you can pass a delay in seconds to the close()-method:
```javascript
 this.refs.toast.close('hello world!', 500);
```

Currently, the default delay for close() in FOREVER-mode is set to 250 ms (or this.props.defaultCloseDelay, which you can pass with)

```jsx
 <Toast ... defaultCloseDelay={100} />
```



### Basic usage  

```javascript
render() {
        return (
            <View style={styles.container}>
                <TouchableHighlight
                    style={{padding: 10}}
                    onPress={()=>{
                        this.refs.toast.show('hello world!');
                    }}>
                    <Text>Press me</Text>
                </TouchableHighlight>
                <Toast ref="toast"/>
            </View>
        );
    }
```

### Custom Toast   

```javascript
render() {
        return (
            <View style={styles.container}>
                <TouchableHighlight
                    style={{padding: 10}}
                    onPress={()=>{
                        this.refs.toast.show('hello world!',DURATION.LENGTH_LONG);
                    }}>
                    <Text>Press me</Text>
                </TouchableHighlight>
                <Toast
                    ref="toast"
                    style={{backgroundColor:'red'}}
                    position='top'
                    positionValue={200}
                    fadeInDuration={750}
                    fadeOutDuration={1000}
                    opacity={0.8}
                    textStyle={{color:'red'}}
                />
            </View>
        );
    }
```