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
