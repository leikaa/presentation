In the world of programming, every lesson begins with hello, world.

### So, hello, world!
```html
<slide hello world>
```
By the way I'm going to read this presentation, so I hope you can live with it.

Back to business, so, why choose React?
Before we get started, let’s stop for a moment and think about it.

* Declarative
    * In React, you describe what to render (instead of telling the browser how to do it). This also means that the amount of boilerplate is greatly reduced.
* Clear syntax
    * JSX in React feels just like HTML, there’s no special syntax to learn
* Learning curve
    * Learning curve is very important when picking a UI framework. If you know JavaScript then you can probably start writing React code in a single day. 
    
Yes, it takes time to pick up best practices, but you will be able to start very fast.

* Functional
    * In React, all of the UI can be expressed as a set of pure functions.

In React you simply start coding, of course there are some setup involved, when u get started, but when it comes to the components, you can express them as pure functions.
```html
<5 slides with WHY>
```

### Let’s start coding!

React.js is just a library. Not a framework.
Like any other library, react can be added to the page with a simple script tag.
For simplicity, you can start working with react, as with a regular library, for example, jQuery, and in the future you can move to a better tool - create-react-app.

For beginning we'll be using react as a library.
We also need babel, to turn our strings which will be written in the JSX language into valid javascript code.
But I remember that another way to build our application - create-react-app from Facebook.
This is the most popular way to set up your environment and start coding. It comes with many required tools built-in.

For installation with a create-react-app we'll need Node js.
Node.js is a JavaScript runtime environment!
First of all, let’s make sure that you have Node.js installed. 
If not, you can download it from here: [https://nodejs.org/en/download](https://nodejs.org/en/download)

To install create-react-app globally:
```npm i -g create-react-app```

Then to build your first project run:
```create-react-app react-intro```

That’s all! Now, to start the application we can use these commands:
```cd react-intro```
and then
```npm start```

This will launch a development server and will allow you to open the brand new and shiny React application by going to [http://localhost:3000/](http://localhost:3000/) in your browser.
```html
<3 slides script and create-react-app>
```

After we dealt with previous step we can move to react itself.
This example will be extremely simplified, as we used the script method and we don't have much time.
First we start from index.html.
```html
<slide index.html>
```

The part that interests us is the ```<div id="root"></div>```. This is where our React application will go. The entire root div will simply be replaced with the contents of our React application. 

The line that does the magic is:

```ReactDOM.render(<App />, document.getElementById('root'));```

This line is a way of telling React to take our App component (we’ll discuss it in a bit), and place it within the root div that was defined above.
```html
<same slide with index.html>
```

Let’s now focus on the ```<App />``` part. This looks a lot like HTML, doesn’t it? This is called JSX, and is a special JavaScript syntax that React uses to do its magic. Note that it starts with a capital A — it is ```<App />``` , not ```<app />```. This is a convention used by React, which allows it to disambiguate between regular HTML tags and React components that we’ve created. If you don’t start your components with a capital letter, then React won’t be able to render your components.
```html
<slide with App>
```

If we have a many js files structure, whenever using JSX, we always have to import React by adding the following line within our .js file:
```import React from 'react';```
```html
<slide with import React>
```

Now we’re ready to take a look at our first component.
To describe components you can use classes or functions.

In order to create a React component, we have to create a class that inherits from React.Component. That is exactly what the line class Name extends React.Component does. 
All React components should implement a render method — as you may have guessed, all of the rendering is happening within this method. The render method has to return the markup to be rendered.
```html
<slide with 2 types of components>
```
A small side-note: the className attribute is equivalent to the class attribute in HTML, and is used to assign CSS classes for styling. Class is a reserved keyword in JavaScript, and cannot be used for an attribute name.

Let’s recap:
* The component is named Example (capital E)
* It extends the React.Component class

### Introducing props

Props is a concept, central to React. What props are exactly? Think for a second about parameters passed to a function. Props are just that — parameters passed down to a component.

Each component can have properties. They are stored in this.props, and are passed to the component as attributes.
For example:

```const person = {name: Mike, surname: Wazowski};```

```<MyComponent data={person} another_prop={[1,2,3,4,5]} />```

You can pass any JavaScript primitive, object, variable, or even expression to a property. The value of the property must be placed in curly brackets.

Values are available via ```this.props.PROPERTY_NAME``` (in stateful components - in short -> class components) or in the first argument of the function (in stateless - in short -> function components). 
In our case, if we talk about stateful, we get:
``` js
this.props.data - object {name: Mike, surname: Wazowski}
this.props.another_prop - array [1,2,3,4,5]
```
```this.props``` can be used for read-only!
```html
<slide props>
```

### Single Responsibility Principle

Single-Responsibility Principle is one of the most important principles to follow. It states that a module should do one thing, and it should do it well. Not following this principle alone can turn any codebase into a nightmare that is impossible to maintain.
How can we violate this principle? The most common way is placing unrelated things in the same file.

Common mistake when you place multiple unrelated components in the same file. This is a bad practice because this violates the Single Responsibility Principle. Components should be placed in a separate files.
Make sure that the filename matches the component name. For example App component should be placed in App.js and so on.
```html
<slide about single responsibility>
```

### Introducing state

State is another concept, central to React. This is where you want to keep your data that may change. 
You can use state only in stateful components (class components).

If you define some mutable property in a component, you must specify the initial state. To do this, you just need to define the state property of the component:
```html
<slide with states>
```
State is basically a plain JavaScript object that is stored as a property within the Article class component. Here we’re adding value visible to the class.
```html
<same slide with states>
```
```html
<slide with if block, dependent on states>
```

```this.setState(...)```
This is how we update the state of our components. We’re not supposed to update the component state directly, only via the setState method. And to update the value we simply pass an object with the updated values to the setState method:
```html
<slide with setState>
```

For example, to change the rating, you need to write the following setState:
```html
<same slide with setState>
```

To change all three properties:
```html
<same slide with setState>
```

Also, setState has the ability to specify a callback function that will be called after the new state is "established".
```html
<slide with callback>
```

Remember, changing the state calls the render component!
Obviously, if the parent component is rendered, all child components will be rendered as well.

### Styling

Styles in React are added simply by passing the styles in the style attribute (inline method) or via classes.
Remember, do not place the styles within the render method of our components. This significantly impairs readability.
```html
<slide with styles>
```

### What’s next?

This presentation was a little longer than I expected, but still we barely scratched the React's surface. There’s still a lot to cover and if you want to master React atleast at the basic level, I would strongly recommend you to check out this article:
[https://legacy.gitbook.com/book/maxfarseer/react-course-ru/](https://legacy.gitbook.com/book/maxfarseer/react-course-ru/)