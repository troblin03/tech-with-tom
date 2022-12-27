# HTML Links

In order to create links in HTML, we use _anchor elements_ - signified with `<a>`

Without specifying, an anchor element does not do anything. Instead we need to add `href` and specify where we are linking to. For example

```
<a href="https://www.theodinproject.com/about">click me</a>
```

Adds a clickable 'click me' link that directs to the about page of the Odin Project.

## Absolute and Relative Links

There are two primary types of link that are used in web dev.

1. Links to pages on other websites on the internet
2. Links to pages located on our own website

###### Absolute Links

Links to other pages on the internet are called absolute links

###### Relative Links

Links to other pages within our website are known as relative links. They do not include a domain name because they are _relative_ to the page the link is being created on.

To achieve this, as long as the two html files are in the same directory we can simply

```
<a href="newpage.html">New Page</a>
```

Normally however, we will have ONLY index.html in the root directory and the other html pages in their own directory.
