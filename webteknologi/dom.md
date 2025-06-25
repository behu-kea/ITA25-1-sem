Nicklas det er Benjamin her. Jeg flyttede det her fra HTML på uge 2 til her. Synes det giver mere mening at bruge tid på DOM når de skal arbejde med det. 



Gud Benjamin - er det dig? Troede lige det var en anden



# HTML DOM

## Learning goal

- Can explain what the DOM is and convert an html document to a DOM tree



DOM stands for Document Object Model. It is a representation of the html elements! The individual html elements are represented as nodes. 



#### Why do we even have the DOM? What is it used for?

The browser uses the DOM to render a page. So a browser takes your html, transforms it into the DOM and then it starts rendering the DOM. 

When working with javascript you will actively be using this DOM. You dont need to understand the code. This is simply an example to show that the DOM is a very concrete and real thing. 

```js
// The document object model
const dom = window.document;
// Here we are grabbing a specific node (the html element div with the class of user-name)
const usernameDomNode = dom.querySelector('div.user-name');
// Now we are changing the text inside of the node
usernameDomNode.innerText = "Heriette Hansen";
```



![Image not loaded go to https://github.com/behu-kea/dat20-classes/blob/master/week-1/assets/dom.png to see image](../../dat20-classes/HTML:CSS/assets/dom.png)



The nodes have relationships between each other. 

- Who is the parent of the `body`?
- What relationship does the `div` with id `div1`  has to the `h1`?
- Who is the `h1`'s grandparent?
- How many children does the `HTML` element have?

If all of this is a bit confusing i get it! Try go [here](https://software.hixie.ch/utilities/js/live-dom-viewer/ ) where you can see the html file, the DOM and the rendered html.