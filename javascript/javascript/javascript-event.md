### Events is the notifications that are sent to notify the code that something happened on the webpage

Event references:

[https://developer.mozilla.org/zh-TW/docs/Web/Events](https://developer.mozilla.org/zh-TW/docs/Web/Events)

![](/assets/js-7)

## Event bubbling

Let's say we click the button using below HTML, the click event will bubble to its parent level until HTML root

\( P &gt;&gt; section &gt;&gt; main\)

![](/assets/js-26)

## Event Delegation

We can assign the parent of the clicked element to be its listener. This is so-called event delegation

#### When could we use the event delegation?

1. #### When we have an element with lots of child element that we are interested in.
2. #### When we want anevent handler attached to an element that is not yet in the DOM when our page is loaded.

![](/assets/js-28)

## 

## 

## 



