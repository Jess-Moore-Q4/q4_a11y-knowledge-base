# Best Practices

## Common Scenarios

### Embedded Iframes 
- Source code is not that of Q4's and can be dismissed

### Links to files
- Avoid generic uses of “Download PDF (Opens in new window)”. This is especially confusing to screenreader users when there are multiple links using the same vague description. Use aria-label or aria-labelled by to provide more context to generic link text. See good example below
``` html
<li class="module-sec_download-list-item module-sec_pdf">
    <a class="module_link module_link-sec" href="/somedocument.pdf" target="_blank" aria-label="4 filing dated 10/06/2021 in pdf format">
        <span class="q4icons_icon" aria-hidden="true"></span>
        <span class="sr-only">pdf Format Download (opens in new window)</span>
    </a>
</li>
```

### Outlines
- Be careful when setting `outline-color: inherit` for buttons if the color property of the text is the same as the background color then the outline will not display.

### Color Contrast
- WCAG specifies minimum font sizes for color contrast in pt instead of px when analyzing if the font size and color combination is accessible. These translate to the following:
    - 14pt = 18.66px
    - 18pt = 24px

- When using background-image CSS property, background-color should still be set depending on foreground and background color as scans analyze the nearest set background-color. 

- According to the [WCAG](https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum.html): text or images of text that are part of an inactive user interface component, that are pure decoration, that are not visible to anyone, or that are part of a picture that contains significant other visual content, have no contrast requiremen

### Alt Tags
- Not every image requires an alt tag, some are purely decorative and it’s actually a better experience to hide these from screen readers (aria-hidden, alt=””)
``` html
<img src="//s22.q4cdn.com/309914286/files/images/environmental-commitment.jpg" alt="">
```
- The same rule applies to icons, however if there is no visable text related to the icon - a `sr-only` alternative shuld be provided
``` html
<li class="module-sec_download-list-item module-sec_pdf">
    <a class="module_link module_link-sec" href="/somedocument.pdf" target="_blank" aria-label="4 filing dated 10/06/2021 in pdf format">
        <span class="q4icons_icon" aria-hidden="true"></span>
        <span class="sr-only">pdf Format Download (opens in new window)</span>
    </a>
</li>
```

### Tabs And Other UI Controls
- Elements that control the ui, ie. tabs, modal links, etc should semantically be a `<button>` instead of a link
``` html
<button class="disclaimer_link"> Copyright © 2021, S&P Global Market Intelligence (and its affiliates as applicable). All rights reserved. </button>
```

### Tables
-Tables must contain a `<caption>` or have an aria-describedby attribute. Providing a `<caption>` should be the first option. 

- Don’t use tables for presentation purposes. An example is the email alert checkboxes, in which case use `role=”presentation”`

- For tables with multi-line headings make sure that the screen reader reads out the heading all at once. If a `<br>` is used it will cause break up the heading into multiple lines and the user will need to press the down arrow multiple times to read the heading. 
	- Proposed solution: Use `<div><span class=”sr-only”>&nbsp;</span></div>` instead of `<br>`

- Table headers must be announced as a table header
    - Solution use `scope=”col”` and `scope=”row”`

- For responsive views and zoom (200% and 400%) make sure that the table is responsive and does not exceed the dimensions of the screen. (1.4.10 AA)

