This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.<br>
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br>
You will also see any lint errors in the console.

### `Redux`
//Store -> Global State

//Action -> 描述我想做哪些事情
const increment = () =>{
    return{
        type: 'INCREMENT'
    }
}
const decrement = () =>{
    return{
        type: 'DECREMENT'
    }
}
//Reducer -> 描述用哪個Action要讓哪個State改成怎樣
const counter = ( state=0,action)=>{
    switch(action.type){
        case "INCREMENT":
            return state + 1
        case "DECREMENT":
            return state - 1
    }
}
let store = createStore(counter)

//Display it in console
store.subscribe(() => console.log(store.getState()))

//Dispatch -> 執行action
store.dispatch(increment());
store.dispatch(decrement());
store.dispatch(decrement());