---
layout: post
title:  "The basics of HTML"
date:   2018-10-17
categories: development
---

This post assumes that you have little or no previous knowledge of HTML. I won't cover everything about HTML but there's enough to get you started and understand the basics. I definitely won't cover every single element.

## Quick history lesson

In the mid 70s, a guy called Charles Goldfarb who worked at IBM, came up with a way to add structure to electronic documents - Standard Generalized Markup Language (SGML). It became an international standard for defining markup that describes the structure of different types of electronic documents.

I'd really recommend reading ["The Roots of SGML"]([http://www.sgmlsource.com/history/roots.htm) by Charles Goldfarb - the guy who invented SGML, without it, we wouldn't have HTML! :(

Hypertext Markup Language (HTML) is an application of SGML. HTML has a specific set of 'tags' that you're allowed to use e.g `<p>`, `<h1>`, `<body>` etc.

HTML was invented by a guy called Tim Berners-Lee in the early 90s when he was working at CERN. Tim was looking for a way for physicists to share documents with eachother.

## A basic HTML document

Here is a basic HTML document:

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Loveridge</title>
    </head>
    <body>
        <h1>Robert's website</h1>
        <p>Hello people of earth!</p>
        <p>
            <a href="stuff-for-sale.html">
                See things I have for sale
            </a>
        </p>
        <!-- remember to add comments -->
    </body>
</html>
```

HTML documents are a tree of elements and text. An element is defined by a start tag, such as `<h1>` and an end tag, such as `</h1>`. Although there are some tags that don't require end tags, such as `<hr>`, `<br>` and `<input>`.

Elements can have attributes and attributes define how an element works. In the example below, there is an `<a>` element with a `href` attribute:

```html
<a href="stuff-for-sale.html">See things I have for sale</a>
```

Attributes are placed inside the start tag with key/value pairs separated by an equals sign. You _can forget to quote the value_ but generally, it's best practice to use them!

## Adding text to your document

You can add headings to a page with `<h1>` all the way to `<h6>` with 1 being the biggest and 6 the smallest header. If you want to add a paragraph of text to a page, you'll use the `<p>` tag. You can add line breaks with the `<br>` tag. You can emphasize text by using `<em>` (emphasis) and `<strong>` (strong importance).

## Using tables

Table elements are declared with the `<table>` tag. In the HTML-for-email world, tables are still used for page layouts but if you're designing a website, you're probably gonna want to do it without tables and use some CSS instead!

Tables are actually really simple to understand and the 3 main tags you'll need to know about are `<table>` to start a table, `<tr>` for a row and `<td>` for a cell. Here's a basic table with 2 rows and 8 cells (4 columns):

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Loveridge</title>
    </head>
    <body>
    <table>
        <tr>
            <td>Row 1, cell 1</td>
            <td>Row 1, cell 2</td>
            <td>Row 1, cell 3</td>
            <td>Row 1, cell 4</td>
        </tr>
        <tr>
            <td>Row 2, cell 5</td>
            <td>Row 2, cell 6</td>
            <td>Row 2, cell 7</td>
            <td>Row 2, cell 8</td>
        </tr>
    </table>
    </body>
</html>
```

I will definitely be adding to this post as and when I have time!