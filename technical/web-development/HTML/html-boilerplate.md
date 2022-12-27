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
 
The meta tag for the charset is vital because it ensures correct display if special symbols and characters from multiple languages.
 
```
<meta charset="utf-8">
```

###### Title Elements

The title element gives webpages a human-readable title which is displayed in the _browser tab_

```
 <title>My First Webpage</title>
```
 
Without the title tag, the webpage's title would default to its file name.

## Body Element

The final element required to complete the HTML 'boilerplate' we are creating is the `<body>` element. This contains all the content that will be displayed to users.

```
<body>
</body>
```
 
 
