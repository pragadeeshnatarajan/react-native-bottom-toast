
## Getting started  

Add `react-native-bottom-toast` to your js file.   

npm install react-native-bottom-toast --save

Inside your component's render method, use Toast:   

```javascript
import Toast, {DURATION} from 'react-native-bottom-toast'

 render() {
         return (
             <View style={{flex:1}}>
                 ...
                 <Toast ref="toast"/>
             </View>
         );
 }
```

```javascript
 this.refs.toast.show('hello world!');
```
