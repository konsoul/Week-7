# Elements

You can use elements’ names like div or p to generate HTML tags. Emmet doesn’t have a predefined set of available tag names, you can write any word and transform it into a tag: div → "< div> < /div>" foo → < foo>< /foo> and so on.

You can also set up your head and meta tags very quickly with just an ! in a blank html document.

<br>
<br>
<br>

# Nesting operators

Nesting operators are used to position abbreviation elements inside generated tree: whether it should be placed inside or near the context element.
<br>
<br>
<br>

## Child: >

- You can use the > operator to nest elements inside each other:

```
div>ul>li would produce the following structure in html.

<div>
  <ul>
    <li></li>
  <ul>
</div>

```

---

<br>
<br>
<br>

## Sibling: +

- you can use the + operator to place elements near each other, on the same level:

```
div+p+bq will produce:

<div></div>
<p></p>
<blockquote></blockquote>
```

---

<br>
<br>
<br>

## Multiplication: \*

With the \* operator you can define how many times element should be outputted:

```
ul>li*5 would produce:

<ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```

---

<br>
<br>
<br>

## Grouping: ()

Parenthesises are used by Emmets’ power users for grouping subtrees in complex abbreviations:

```
div>(header>ul>li*2>a)+footer>p would produce:

<div>
    <header>
        <ul>
            <li><a href=""></a></li>
            <li><a href=""></a></li>
        </ul>
    </header>
    <footer>
        <p></p>
    </footer>
</div>
```

- You can nest groups inside each other and combine them with multiplication \* operator:

```
(div>dl>(dt+dd)*3)+footer>p would produce:

<div>
    <dl>
        <dt></dt>
        <dd></dd>
        <dt></dt>
        <dd></dd>
        <dt></dt>
        <dd></dd>
    </dl>
</div>
<footer>
    <p></p>
</footer>
```

---

<br>
<br>
<br>

# Attribute operators

Attribute operators are used to modify attributes of outputted elements. For example, in HTML and XML you can quickly add class attribute to generated element.

<br>
<br>
<br>

## ID and CLASS

In CSS, you use elem#id and elem.class notation to reach the elements with specified id or class attributes. In Emmet, you can use the very same syntax to add these attributes to specified element:

```
div#header+div.page+div#footer.class1.class2.class3
...will output

<div id="header"></div>
<div class="page"></div>
<div id="footer" class="class1 class2 class3"></div>
```

---

<br>
<br>
<br>

## Custom attributes

You can use [attr] notation (as in CSS) to add custom attributes to your element:

```
td[title="Hello world!" colspan=3] will produce:

<td title="Hello world!" colspan="3"></td>
```

- You can place as many attributes as you like inside square brackets.
- You don’t have to specify attribute values: td[colspan title] will produce <td colspan="" title=""> with tabstops inside each empty attribute (if your editor supports them).
- You can use single or double quotes for quoting attribute values.
- You don’t need to quote values if they don’t contain spaces: td[title=hello colspan=3] will work.

---

<br>
<br>
<br>

# Text: {}

You can use curly braces to add text to element:

```
a{Click me} would produce:

<a href="">Click me</a>
```

- Note that {text} is used and parsed as a separate element (like, div, p etc.) but has a special meaning when written right after element. For example, a{click} and a>{click} will produce the same output, but a{click}+b{here} and a>{click}+b{here} won’t:
