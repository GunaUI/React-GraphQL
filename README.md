# React-GraphQL

## Birth of react

* Now react came out in 2013. But what do we have before then before we act. just HTML, CSS, Javascript.because it became easier and easier to work with the DOM we had the birth of a single page application.

* You see traditionally we just had a small files for each page and every time we moved to a different page we would request from the serve

* but with more advancement like we had with Jquery backbone and something called Ajax we now had a different system. What generally happened now is we focused less on HTML and more on Javascript.

* You only load the application code once instead of us making new requests to the server where we returned a new document instead.Now our applications acted more like a desktop application where we stay on the same page the entire time and the javascript file simply changes or updates the HTML for the DOM to display new things.

*  this way of writing applications are single page applications became really really popular. And in 2010 angular J.S. which was created by Google really became the standard way of building applications. MVC Pattern

* angular J.S. came out people started to notice it's getting harder and harder to find bugs in the code and understand how each part of the
app was affecting the other.

* Meanwhile Facebook developers were finding it hard as well on their end to maintain their app especially their Facebook ads.

* We need to think about how we organize our code how we manipulate data and how that data flows through our programs. So Facebook came up with a solution and that solution worked really really well for them.

* That in 2013 they released react to the developer community at J.S. conf 2013 and their solution was really really good.And it took off because react devolved a whole new way to build front end applications.

* It also happened that in 2014 angular J.S. realized that the way that they've architected their framework just didn't allow good applications to be built anymore so they decided in 2014 that they're going to rewrite the entire library.Call it angular but because they wanted to do an entire rewrite a lot of people during that time moved to react.

## Declarative vs Imperative

* Now the success of React comes down to four key things.
    * the first one reacts says hey don't touch DOM i will do it. 
        * You see many existing frameworks and libraries before react where directly manipulating this Dom on every page. Dom is our Document Object Model.
        It's what the browser uses to display while a Web site or a web app.  Javascript is simply manipulating this Dom. That's all javascript is doing.
        * this way of programming was called imperative that is in an imperative paradigm you directly change individual parts of your app in response to various user events.
        * This sounds intuitive but the problem with this imperative approach is that it becomes difficult to see the relationships between events and all these edge cases.
        *  well instead of this imperative approach react came up with a novel concept a more declarative approach 
        *  Dom manipulation is one of the biggest performance bottlenecks. It takes a long time for Dom changes to happen.
        * The browser has to do two really intensive operations.
            * One is to repaint.That is change an element and added onto a page and then refloat which is to recalculate the layout of the page and move things around if need be. So changing the Dom was a really expensive operation. So react says hey you know what. Let me take care that I'll find the best way for me to change the Dom and just declare to me what your app should looks like.
            * So all we need to do is say hey this is a javascript object of how I want the app to look and react is going to hold this javascript object this massive massive blueprint of how things should look. And based on this blueprint that we give it will react just says hey just tell me what the page should look like and I'll take care of it. I'll do everything for you. I'll find the best way to use the DOM. You're never going to touch the DOM.Just tell me what the page should look like. This is called declarative paradigm.
            * the name react is simply saying hey based on whatever the state or data of the app is that describes her app I'm just going to react to it and change everything for you so that you get the display that you want.

* Building websites like lego blocks.
    * reactors designed around the concept of reusable components.

* unidirectional data flow.
    * state and component combined together and then it will create a virtual DOM , ie it creates a javascript version of the Dom.
    * A virtual DOM is tree like object that gives react a blueprint of how it should update the actual DOM
    * the react little bot over here is going to go look at the blueprint of what it needs to build and modifies the DOM for us now this idea of a unique directional data flow means that any time we want something to change on our Web page.
    * Let's say I click on the sign up.React is going to say hey somebody just clicked on the sign out button. How are we going to change the state. Well internally we would say that if somebody clicks on the sign out we're gonna change is logged in to now say false and react as soon as the state changes reacts to that change. just say combine the new state and the components we have and update the DOM, the data only flows one way a better way.
    * our application is simply built with this virtual DOM,  as soon as a state changes it's going to trickle down that information and let everybody know hey the state just changed, Display this version of the app.
    *  data can never move up.But the key takeaway here is that by having this restriction of data only being able to move down from the state of our application all the way to the DOM and if any changes or events happen that change the state while we go back to the state and that's state change trickles down to different components in one direction.
    * restriction on how data can move through our app and by adding this restriction it's really easy to debug code.For example if there's something wrong with our sign our function.I can go to wherever the state is logged in lives.

* UI, Rest up to you.
    * Remember how with angular it came with all these things built in that is angular J.S.. It was a framework and a framework is kind of like a whole kitchen.It gives the developers all the tools necessary to build an application.
    * So if you're a cook in a kitchen while you get the oven you get the nife you get the drawers you get the pots and pans. You have the stove you have everything for you. And this is how you cook or this is how you build a Web site. It's very opinionated.
    * On the other hand react said Hey I only care about this whole idea of components and virtual DOM and I only am going to work with the view the user interface everything else that you need while you can just use other modules other libraries and mix and match and have whatever you want customized to your need.
    * So it was a library a UI library which is not like a kitchen. It's more like let's say the stove they gave you the stove to cook your soup on but everything else like knife cutting board spoon. Well you can pick whichever one you want. It's up to you what you use to build that soup. All we give you is this oven
    * the key idea was that because it was so small you can learn once and write anywhere. What does that mean. Well react doesn't make assumptions about what technology stack you use all we give you is hey here sis this idea of components of a blueprint that we can use a massive javascript object to make changes.And here's also a robot that will interact with the Dom and makes changes for you.