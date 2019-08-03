# React-GraphQL

## React Basics

### NVM installation 
* Refer : https://github.com/nvm-sh/nvm
* Step  1 : curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
* Step  2 : close terminal and then open new termainal type "command -v nvm" you should see nvm if not do the step 3
* Step  3 : Check you have bash profile or not "nano ~/.bash_profile" At the bottom you could see nvm path with that add "source ~/.bashrc" then repeat step 2
* Step  4 : To rerun bash profile run "source ~/.bash_profile"
* Step  5 : Now run "nvm", you will see nvm installed details.
* Step  6 : "nvm install 10.16.1"
* Step  7 : "nvm use 10.16.1"

### NPM vs YARN

Install dependencies from package.json: npm install == yarn



Install a package and add to package.json: npm install package --save == yarn add package



Install a devDependency to package.json: npm install package --save-dev == yarn add package --dev



Remove a dependency from package.json: npm uninstall package --save == yarn remove package



Upgrade a package to its latest version: npm update --save == yarn upgrade



Install a package globally: npm install package -g == yarn global add package

### Create React App
* Refer : https://github.com/facebook/create-react-app

### Class Components

* We know that we can write functions that return HTML but we can also write classes that return HTML

* And the reason why we would want to use a class is because react has given us the ability to write classes
that have a lot more functionality on them versus a function that returns some HTML.

*  so class app extends this component that we get from reactive.And as a result we now have access to this render method inside of our app class and the render method returns any HTML.

* But the reason why we would want to use this kind of thing is if we wanted say instead to display this static string  what if I wanted something like let's say instead of an A tag we had a button and whenever you click this button it would change something.

* using a class component we actually get access to this thing called state. 

* what state is ? A javascript object with properties that we can access at any point inside of our class.

```jsx
constructor(props) {
  super(props);
  // Don't call this.setState() here!
  this.state = { counter: 0, name : "Guna" };
  this.handleClick = this.handleClick.bind(this);
}
```

* We can access the above set state with.
```jsx
<p>{this.state.name}</p>
```
* I wanted to change this value while the way I would do it is this class app that extends component this component also gives us this method called set state

```jsx
<button Onclick={()=> this.setState({name : "Gunaseelan"})}></button>
```

### Thinking In JSX

* The very first thing is that this syntax of JSX , uses the syntax of class name to distinguish between what we actually mean which is the actually giving it an HTML class VS a class in Javascript

* You see you're not allowed to modify state in react without calling this method set state. Now why is that because any time we change the state let's say a user clicks that button to change the state to a new string. 

* When that click happens what happens is react actually.Intercept because remember react as the one that's talking to the DOM. It's going to intercept that click and it's going to report back and say Hey I got to click on the Dom. What do I do. Well in this case what we're going to say is on click when the click happens I want you to update the state but we're not going to modify the state automatically.

* I'm going to say hey a click happened.State gets updated using set state and then that change is going to re render the components

* as soon as this set state gets called , Well what's going to happen this render method gets called again. Why does it get called. Well because state just got updated state now is a different thing.

* And remember the declarative approach with react is that as soon as state changes we re render the component with the new state

### Dynamic Content

map() + key attribute
A good rule of thumb as to when to use the key attribute, is this: Anytime you use the map() function inside of render, or you have a list of the same jsx elements one after another, they need a key attribute (and CRA will warn you about it if you miss it)

### Single Page Application

* So now with a single page application instead of requesting a page it's turn more into requesting for data. And this is when we have the ability to let's say communicate with outside servers maybe servers that we don't control.

### Fetching Content

* But the main one I want us to focus on is component did mount. Now what component did mount does is it's kind of like the name right when this component mounts, mounting is essentially one react puts our component on the page.It renders it onto the DOM for the first time when it does it calls whatever block of code we write inside component did mount

### Breaking Into Components

* this idea of breaking things down into small individual chunks is really really important.
*  we also have this flexibility of performance improvements potentially as well as having components that are really easy to test

### State vs Props

* state we passed down to the card list component as well an attribute right.Just like we have HTML attributes we sent down to the component, then component receives it as a prop.
* So that state gets turned into props into all these little components that we pass it down , that state usually lives in just one location or a specific state only on one location and it trickles down as props

### React Event

* Refer : https://reactjs.org/docs/events.html
* when a dom event happens because let's say a user clicks or types something in an input the DOM on change event is going to say hey something changed.
* Now react intercepts that and says oh something has changed. Let me go tell my react ad that something's happened and this is what a synthetic event
* It's kind of like a fake event that we pretend is a DOM event but it's something that will our ReACT robot is telling us saying hey there was an event on the DOM what should we do and this is our synthetic event.

* And this is an important distinction here because you would never run set state in render because well that's going to create some errors.because every time you call set state it renders and every time you render it's going to call that state. It's just going to create a loop.

* So what we're doing here is we're actually defining a function not running it just letting them know hey on change I want this to happen and react internally with this synthetic event is going to say Hey any time on change happens it's going to be an event just run this function.

* once again reactive smart we're not actually interacting with the DOM what it's going to say is when we do set state it's going to say hey react but we have some updates that we want to make to the DOM. Can you do it for us and our little robot is going to say yep I can do it.

* But you know what.

* I know when the best time to do that is I know when to do it. Just let me handle it. I'll take care of it.

* So it actually doesn't happen right away. What it does is essentially it schedules and batches work. And that's why react good.Because it figures out for us the best time and the best way to update the Dom we just tell it that we want an update.

### Where To Put State?

* Why wouldn't we put state in functional component ?? 
* Remember because of one way data flow data can only flow one way.

###  Class Methods and Arrow Functions

* Well this is a special keyword in javascript that references the context in which it's being invoked, So what does that mean ?? 

* Well when I say "this.states" we know that I'm trying to reference the state on the component right

* Now the weird thing is that in JavaScript when we write our own class methods we'll see that the this keyword actually gets bound differently depending on how we write the class method.

* ComponentDidMount, render methods are borrowed from react componenet right ? And when we borrow them from component component actually sets the context of "this" inside of them for us to our class based components

* if we were to write our own method we would have to be careful about how we write it. we have to use arrow function not our normal way of creating function.

* In case if use normal fucntion like below our set state reference to this will be undefined.
```jsx
handleClick() {
    this.setState({test: "hai"})
}
<button onClick={this.handleClick}>

```
* The reason for this is because javascript by default doesn't set its scope of this on functions.

* You have to actually explicitly state what context you want this to be for us.

* We want this to be our app component and the method in which we can do it is to define it in our constructor

* because our constructor is the code that runs first before anything gets called right.So we want to make sure that the context of this is correct in all of our methods before any code gets written.

```jsx
constructor(){
    super();
    this.state ={
        test: "hello"
    }
    this.handleClick = this.handleClick.bind(this);
}
```
* Now what is ".bind" what dot bind is a method on any function that returns a new function where the context of this is set to whatever we passed to it.

* This is not the best practice !!! because for each and every method we have to bind new context , to avoid that we can use the ES6 arrow function.

* While arrow functions automatically allow you to set "this" 
```jsx
handleClick =() => {
    this.setState({test: "hai"})
}
```

* So when our component is getting run by javascript for the first time and it's like oh I got to instantiate this new app class it checks inside and it sees that there's this handle change method that points to an arrow function.

* So then it defines the arrow function based on what code we've given it right. And the moment it sees the this keyword it's like oh this is an arrow function I'm going to automatically bind this to the place where this arrow function was defined  and the context of this arrow function is our app component so that's the crazy thing about Arrow functions

###  Asynchronous setState

* it usually batches multiple sets state calls because sometimes we can have in our app multiple set state calls so or multiple locations where we change the DOM
*  instead of calling set state every single time. It sometimes gets smart and says oh don't worry if there's a lot of states happening I'll bash them
together and update them all into one single update for performance.
* But react actually does not guarantee that when we call this and we update state that this is going to work why is that ??
* Well because this call offsets state is asynchronous and what does that mean ??
* It means that when we click on the button this doesn't happen immediately when we call this setState We give control to the reactive library and we say hey you take care of this you know the best time to update the state for me. I don't care just do it for me and I'll keep doing something else 
* so unlike a synchronous call that this happens immediately when we call it asynchronous it just happens sometime in the future 
* We can give a second parameter to our set state call which is our callback and the callback simply takes a function so it can just have a simple arrow function that console logs that.
```jsx
this.setState({count: this.state.count + 1},
() => console.log(his.state.count);
);
```
* See that now everything is in sync Okay so that works.
* This is actually that practice. Why is that. ?? 
* This is working however because of the way. Set state batches work into a single update like I mentioned.If we had multiple set state calls it doesn't guarantee for latest state

```jsx
this.setState((prevState, prevProps) => {
    return {count: prevState.count + 1}
},
() => console.log(this.state.count);
);
```
* prevPros , in case this component have some props as "incrementval" we could access with prevProps

```jsx
this.setState((prevState, prevProps) => {
    return {count: prevState.count + prevProps.incrementval}
},
() => console.log(this.state.count);
);
```
* Incase if we are going to use props inside constructor we have give props as arguments for both contructor and super 
```jsx
constructor(props){
    super(props);
    this.state ={
        count: 59 + this.props.incrementval
    }
}
```
* keep in mind state updates are a synchronous and we want to be careful.
* The rule is this. Do you ever want to manipulate or use this state somehow after the update.Then add in a second parameter which will be a function where you can use that updated state 