# tribute-page

This is project requirement on the FreeCodeCamp responsive web design course, showcasing basic HTML and CSS to create a fictional tribute page.

## Table of contents

- [Guidelines](#guidelines)
- [Tests to pass](#tests-to-pass)
- [Links](#links)
- [What I learned](#what-i-learned)
- [Code Validator](#code-validator)
- [Useful resources](#useful-resources)



## Guidelines

1. Your tribute page should have a `main` element with a corresponding `id` of `main`, which contains all other elements
2. You should see an element with an `id` of `title`, which contains a string (i.e. text), that describes the subject of the tribute page (e.g. "Dr. Norman Borlaug")
3. You should see either a `figure` or a `div` element with an `id` of `img-div`
4. Within the `#img-div` element, you should see an `img` element with a corresponding `id="image"`
5. Within the `#img-div` element, you should see an element with a corresponding `id="img-caption"` that contains textual content describing the image shown in `#img-div`
6. You should see an element with a corresponding `id="tribute-info"`, which contains textual content describing the subject of the tribute page
7. You should see an `a` element with a corresponding `id="tribute-link"`, which links to an outside site, that contains additional information about the subject of the tribute page. HINT: You must give your element an attribute of `target` and set it to `_blank` in order for your link to open in a new tab
8. Your `#image` should use `max-width` and `height` properties to resize responsively, relative to the width of its parent element, without exceeding its original size
9. Your `img` element should be centered within its parent element


## Tests to pass

1. You should have a `main` element with an `id` of `main`.
2. Your `#img-div`, `#image`, `#img-caption`, `#tribute-info`, and `#tribute-link` should all be descendants of `#main`.
3. You should have an element with an `id` of `title`.
4. Your `#title` should not be empty.
5. You should have a `figure` or `div` element with an `id` of `img-div`.
6. You should have an `img` element with an `id` of `image`.
7. Your `#image` should be a descendant of `#img-div`.
8. You should have a `figcaption` or `div` element with an `id` of `img-caption`.
9. Your `#img-caption` should be a descendant of `#img-div`.
10. Your `#img-caption` should not be empty.
11. You should have an element with an `id` of `tribute-info`.
12. Your `#tribute-info` should not be empty.
13. You should have an `a` element with an `id` of `tribute-link`.
14. Your `#tribute-link` should have an `href` attribute and value.
15. Your `#tribute-link` should have a `target` attribute set to `_blank`.
16. Your `img` element should have a `display` of `block`.
17. Your `#image` should have a `max-width` of `100%`.
18. Your `#image` should have a `height` of `auto`.
19. Your `#image` should be centered within its parent.


### Links

- Solution URL: https://soniaela.github.io/tribute-page/



### What I learned


```html
<html lang="en" dir="ltr">
```

This global attribute is an enumerated attribute that indicates the directionality of the element’s text. 

- `ltr` (left to right)
- `rtl` (right to left)
- `auto` uses a basic algorithm as it parses the characters inside the element until it finds a character with a strong directionality, then applies that directionality to the whole element.

***

```html
<html lang="en" dir="ltr">
```

I’ve been blindly adding this line to all my exercises without knowing what it does. According to MDN web docs:

> The browser's viewport is the area of the window in which web content can be seen. This is often not the same size as the rendered page, in which case the browser provides scrollbars for the user to scroll around and access all the content.
> 

> Some mobile devices and other narrow screens render pages in a virtual window or viewport, which is usually wider than the screen, and then shrink the rendered result down so it can all be seen at once. Users can then pan and zoom to see different areas of the page. For example, if a mobile screen has a width of 640px, pages might be rendered with a virtual viewport of 980px, and then it will be shrunk down to fit into the 640px space.
> 

> This is done because not all pages are optimized for mobile and break (or at least look bad) when rendered at a small viewport width. This virtual viewport is a way to make non-mobile-optimized sites in general look better on narrow screen devices.
>

A typical mobile-optimized site contains something like the following:

```html
<meta name="viewport" content="width=device-width, initial-scale=1" />
```

Not all devices are the same width; you should make sure that your pages work well in a large variation of screen sizes and orientations.

The basic properties of the "viewport" <meta> tag include:

- `width`: Controls the size of the viewport. It can be set to a specific number of pixels like width=600 or to the special value `device-width`, which is 100vw, or 100% of the viewport width. Minimum: 1. Maximum: 10000. Negative values: ignored.
- `height`: Controls the size of the viewport. It can be set to a specific number of pixels like height=400 or to the special value `device-height`, which is 100vh, or 100% of the viewport height. Minimum: 1. Maximum: 10000. Negative values: ignored.
- `initial-scale`: Controls the zoom level when the page is first loaded. Minimum: 0.1. Maximum: 10. Default: 1. Negative values: ignored.
- `minimum-scale`: Controls how much zoom out is allowed on the page. Minimum: 0.1. Maximum: 10. Default: 0.1. Negative values: ignored.
- `maximum-scale`: Controls how much zoom in is allowed on the page. Any value less than 3 fails accessibility. Minimum: 0.1. Maximum: 10. Default: 10. Negative values: ignored.

***

```html
<blockquote cite="https://www.azquotes.com/quote/555131?ref=budweiser">
              <p><em>Remember, "I" before "E", except in Budweiser.</em>
              </p>
              <p class='quote'>-Irwin Corey</p>
            </blockquote>
```

This is my first time working with quotes, so I decided to see if there was a more semantically inclined element to use for this type of content (other than div).
The `blockquote` HTML element indicates that the enclosed text is an extended quotation. Usually, this is rendered visually by indentation. A URL for the source of the quotation may be given using the `cite` attribute, while a text representation of the source can be given using the <cite> element.
Example from MDN Web Docs:
  
```html
<figure>
    <blockquote cite="https://www.huxley.net/bnw/four.html">
        <p>Words can be like X-rays, if you use them properly—they’ll go through anything. You read and you’re pierced.</p>
    </blockquote>
    <figcaption>—Aldous Huxley, <cite>Brave New World</cite></figcaption>
</figure>
```

```css
blockquote {
    margin: 0;
}

blockquote p {
    padding: 15px;
    background: #eee;
    border-radius: 5px;
}

blockquote p::before {
    content: '\201C';
}

blockquote p::after {
    content: '\201D';
}
```

My quotes had basic CSS element to center the text in italics and that’s it, but after seeing the above clear and elegant example of MDN Web Docs, I decided to add more styling to my project.

To change the indentation applied to the quoted text, use the CSS `margin-left` and/or `margin-right` properties, or the margin shorthand property.

To include shorter quotes inline rather than in a separate block, use the <q> (Quotation) element.



  ### Code Validator

The first HTML validator run yielded 2 warnings and 2 errors:

WARNING: Section lacks heading. Consider using h2-h6 elements to add identifying headings to all sections, or else use a div element instead for any cases where no heading is needed.

  BEFORE:
  ```html
  <section id='quote-section'>↩
           <figure>↩
            <blockquote cite="https://www.azquotes.com/quote/555131?ref=budweiser">↩
              <p><em>Remember, "I" before "E", except in Budweiser.</em>↩
              </p>↩
              <figcaption class='quote'>-Irwin Corey</figcaption>↩
            </blockquote>↩
           </figure> ↩
  ```

  AFTER:
   ```html
  <div id='quote-section'>↩
           <figure>↩
            <blockquote cite="https://www.azquotes.com/quote/555131?ref=budweiser">↩
              <p><em>Remember, "I" before "E", except in Budweiser.</em>↩
              </p>↩
              <figcaption class='quote'>-Irwin Corey</figcaption>↩
            </blockquote>↩
           </figure> ↩
  </div>
  ```

Explanation: as this section did not require any h2-h6 heading, the section was replaced by a <div>. Otherwise, we could have kept the <section> if we had added a h2-morning h6 heading.

    ***

ERROR: Element figcaption not allowed as child of element blockquote in this context. (Suppressing further errors from this subtree.)

  BEFORE:
  ```html
  <blockquote cite="https://www.azquotes.com/quote/555131?ref=budweiser">↩
              <p><em>Remember, "I" before "E", except in Budweiser.</em>↩
              </p>↩
              <figcaption class='quote'>-Irwin Corey</figcaption>↩
            </blockquote>↩
  </div>
  ```

  AFTER:
  ```html
  <blockquote cite="https://www.azquotes.com/quote/555131?ref=budweiser">↩
              <p><em>Remember, "I" before "E", except in Budweiser.</em>↩
              </p>↩
              <p class='quote'>-Irwin Corey</p>↩
            </blockquote>↩
  ```
  
  
 Explanation: <figcaption> element was replaced by <p> element. 
  
 After correcting the above, the HTML validator returned no errors/warnings. 




### Useful resources

- [Example resource 1](https://www.example.com) 
- [Example resource 2](https://www.example.com) 


