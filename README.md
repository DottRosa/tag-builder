# tag-builder

TagBuilder provides a simple function to convert JSON in tags.
Previously you have to do this:

```js
var tag = "<section class='my-class1 my-class2' data-test='myTest' id='myId'>";
tag += "This is my tag";
tag += "</section>";
document.getElementById('containerDiv').appendChild(tag);
```

And now you can do this:

```js
var tagJson = {
    type: 'section',
    id: 'myId',
    classes: ['my-class1', 'my-class2'],
    data: {
        test: 'myTest'
    },
    content: 'This is my tag',
};

var tag = TagBuilder(tagJson);
document.getElementById('containerDiv').appendChild(tag);
```

##Documentation

###Structure

This is a full structure of a JSON element for TagBuilder:

```js
var tagJson = {
    type: 'section',
    id: 'myId',
    classes: ['my-class1', 'my-class2'],
    data: {
        media: 'val1',
        lightbox: 'val2'
    },
    attributes: {
        'aria-label': 'val3',
        'myattribute': 'val4'
    },
    content: 'This is my section',
    events: {
        click: function(){
            console.log('this is click event');
        },
        mouseover: function(){
            console.log('this is mouseover event');
        },
    },
    children: [
        {
            type: 'button',
            classes: ['my-class3'],
            data: {},
            attributes: {},
            content: 'Click me',
            children: []
        },
        {
            type: 'a',
            classes: [],
            data: {},
            attributes: {
                href: 'link....'
            },
            content: 'Click this link',
            children: []
        }
    ]
};
```

This structure create this html:


```html
<section id="myId" class="my-class1 my-class2" data-media="val1" data-lightbox="val2" aria-label="val3" myattribute="val4">
    This is my section
    <button class="my-class3">Click me</button>
    <a href="link....">Click this link</a>
</section>
```


###Type
