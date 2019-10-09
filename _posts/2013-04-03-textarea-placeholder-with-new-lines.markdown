---
layout: post
title: "Textarea Placeholder with New Lines"
Slug: textarea-placeholder-with-new-lines
date: 2013-04-03 03:40:11
tags: [Javascript,jQuery,Open Source,Software Development]
---
It's been a while since I've posted something development related, and as I was just working on a problem that has a relatively easy solution and can apply to so many web sites, I thought I'd share it.

HTML5 comes with a new placeholder attribute, in to which you can place text to show in a form field when it's empty. Think of it like a suggestion or sample text. In previous lives, we would have had to add the suggestion as the default value, use JavaScript to hide the value on focus, and replace the suggestion on blur if the field was still empty.

Unfortunately, the people behind the design decision of the placeholder attribute have deemed that carriage returns or new lines do not form part of the specification. The rationale, as I understand it, is that a suggestion is a short piece of information to help someone complete the form.

There exists, however, a very common requirement to include sample content that may need new lines. In my case, I wanted to give a suggestion that showed sample comma separated values, which necessitated the inclusion of new lines. This is what it looked like:

![default](https://bendechrai.com/wp-content/uploads/2013/04/default.png)

Not quite what I was after. So, using some simple jQuery, I augmented just those textarea elements that had a placeholder attribute containing a new line.

The [latest code is available as a Gist](https://gist.github.com/bendechrai/545e70d4555fe8d029fd), the following may be outdated.

Taking the following HTML:

```
<pre class="lang:xhtml decode:true "><textarea placeholder="key,val
key,val
key,val"></textarea>
```

And this Javascript: ```
<pre class="lang:js decode:true">function textareaPlaceholderNewlines() {

<p>        $('textarea[placeholder*="\n"]').each(function(){

</p><p>                // Store placeholder elsewhere and blank it
                $(this).attr('data-placeholder', $(this).attr('placeholder'));
                $(this).attr('placeholder', '');

</p><p>                // On focus, if value = placeholder, blank it
                $(this).focus(function(e){      
                        if( $(this).val() == $(this).attr('data-placeholder') ) {
                                $(this).attr('value', '');
                                $(this).removeClass('placeholder');
                        }               
                });                     

</p><p>                // On blur, if value = blank, insert placeholder
                $(this).blur(function(e){
                        if( $(this).val() == '' ) {
                                $(this).attr('value', $(this).attr('data-placeholder'));
                                $(this).addClass('placeholder');
                        }
                });             

</p><p>                // Call blur method to preset element - this will insert the placeholder
                // if the value hasn't been prepopulated
                $(this).blur();
        });

</p><p>}</p>
```

As you can see, it uses jQuery, and adding a call to textareaPlaceholderNewlines() in your body ready block will target all applicable elements on the page. (Note that it won't automatically target new elements that would match the CSS selector criteria that are added to the DOM dynamically after initial render.) A final little touch of CSS:

```
<pre class="lang:css decode:true">textarea.placeholder {  
        color: #aaa;            
}
```

And we get: ![](https://bendechrai.com/wp-content/uploads/2013/04/new-placeholder.png)

And with no additional work (cos it's all in the function above), when you click on or tab to the element, and type away, it looks like a very normal textarea:

![](https://bendechrai.com/wp-content/uploads/2013/04/inserted-text.png)

This code is released under the [MIT license](http://opensource.org/licenses/MIT), but if you use this anywhere, I'd love you to say hi in the comments...
