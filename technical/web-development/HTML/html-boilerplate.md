# HTML Boilerplates

## HTML Index Pages

Whenever we create a web page, we should start with an `index.html` file for the _homepage_. This is because by default, web servers will look for an index.html page when landing on our websites.

## DOCTYPE

Every HTML page will start with a doctype declaration. The purpose of this is to tell the browser what version of HTML should render the document. The way to specify the latest version is to say:

```
<!DOCTYPE html>
```

and should be added to the very first line.

## HTML Element

Once the doctype has been dec;ared, we need to declare the `<html> element. This is the 'root element' of the document and again, should be included in every document.

Within this, we can specify the `lang` attribute which specifies the text content in that element. This will allow screen readers to adapt according to the language.

## Head Element

The `<head>` element contains important meta-information about the webpages, and the stuff required for the web page to render correctly in the browser. There should be no element displaying content within the head tag. Some examples of what to include are below

###### The Charset Meta Element
 
