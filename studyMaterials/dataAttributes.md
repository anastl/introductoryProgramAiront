# Data-Attributes  

Allow the storage of extra, custom information on standard, semantic HTML elements without other hacks such as non-standard attributes, or extra properties on DOM. The stored (custom) data can then be used in the page's JavaScript to create a more engaging user experience (without any Ajax calls or server-side database queries).  

Any attribute on any element whose attribute name starts with data- is a data attribute, and will be completely ignored by the user agent. For example: 

```
<article
    id="electric-cars"
    data-columns="3"
    data-index-number="12314"
    data-parent="cars">
    …
</article>
```

# Bibliography
* [MDN - Data attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)
* [W3 Schools - Data attributes](https://www.w3schools.com/tags/att_data-.asp)