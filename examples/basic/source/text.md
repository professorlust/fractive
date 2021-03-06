{{Basic: Start}}

# Welcome!

Welcome to Fractive, a tool for creating hypertext fiction!

Fractive stories are written in Markdown, and you can add (optional) game logic in Javascript. Stories consist of "sections", which you might think of like one page of a book. Typically a section will give you a bit of narrative and then present one or more choices to the player; each choice takes the story to a different section, and in a different direction.

In Markdown, you declare the beginning of a new section by enclosing the section name (which must be unique!) in double curly braces with an optional list of tags. The section you're reading right now is called `Basic` and is declared as `\{{Basic: Start}}` which tags it as the first section to be shown in the story.

[Link to another section]({@AnotherSection})

{{AnotherSection}}

You just clicked a link that took you to another section! You create section links just like any ol' Markdown link, but in place of the URL you put a special _macro_ enclosed in single curly braces. There are three types of macros, each denoted by a symbol:

- @ denotes a section name to link to
- \# denotes a Javascript function to call
- $ denotes a Javascript variable

So if you set the URL to `\{@Start}` you'd have created a link back to the section called `Start`. If on the other hand you'd put `\{#Start}` you'd have created a link that would call a Javascript function called `Start`.

[What does it look like when a link calls a Javascript function?]({#FunctionLink})
[What happens if I set the link URL to a variable macro?]({#VariableLink})
[What else can I use macros for?]({@InlineMacros})

{{InlineMacros}}

Macros aren't only for links; you can also use them to add dynamic text to your sections.

>{#InlineFunction}

The above paragraph was the result of inlining a function call, which expects the function to return a string. You can also inline the value of a variable. Here's one: {$InlineVariable}

You can even inline an entire section:

>{@InlineSection}

The inlined function and section above are indented, but that's only because I prefaced them with the Markdown blockquote indicator for clarity. Inlines don't inherently get any special styling, so you can inline things totally seamlessly and your players will never know the difference.

Finally, you can create links which expand to text in-place, which is commonly used in e.g. [Twine](https://twinery.org/2/) games for artistic effect. You can link to a [variable]({$InlineExpansionVariable:inline}), or to the return value of a [function]({#InlineExpansionFunction:inline}), and they'll expand in-place.

[You can also do this with a section]({@InlineExpansionSection:inline})

[Can I use Markdown styling?]({@AboutFormatting})

{{InlineSection}}

This paragraph was written in an entirely different section, but it appears as part of the section you're already reading. This might be useful if you have some boilerplate text that needs to follow the player around from place to place; you could put it in a section and inline it, instead of copy-pasting the same sentences (or paragraphs) all over your story text.

{{InlineExpansionSection}}

Sections are kind of special though, in that they don't actually appear inline _per se_, because they're block-level elements (i.e. their own paragraphs) which means they'll put a paragraph break where they appear. They still replace their :inline macro link though, just like with variables and functions. When inline-expanding a section, you can still have paragraph breaks, *additional* **formatting**, and so on. And you can even inline sections which themselves contain [macros]({#RaiseAlert})!

{{AboutFormatting}}

Story text is written in Markdown, which means we have access to *all kinds* of **formatting**, including:

# Headers

## Sub-headers

- Unordered lists (like this one)
- Ordered lists (1, 2, 3, 4...)
- Links can also [*contain* **formatting**]({#RaiseAlert})

Basically, anything Markdown can do, you can do in your story text! You can even inline <span style="color:#ff0000">raw HTML</span> which means you could do video embeds, HTML5 canvas, and all kinds of other fancy stuff.

And of course, because fractive games are ultimately HTML in the end, you can create your own HTML template with whatever layout you want, and style it with CSS. For example, you could surround your game with a header and footer, or create a sidebar which (along with some custom Javascript) tracks your player's inventory and stats as they move through the story.

[How does fractive handle long/complicated stories?]({@LongStories})

{{LongStories}}

Fractive's main goal is to be the best tool for writing complex, dynamic hypertext fiction that has lots of branches and genuinely consequential choices. What you're reading right now is produced by a _very_ eary version of the tool, so this goal isn't fully realized yet, but it is the direction I'm heading.

You can split long story text up into as many individual Markdown files as you like, and they can be named whatever you like. The same goes for game logic in Javascript; you could have separate .js files for each logical class, or for each scene or major location in your story, or however else you'd like to organize it. When you publish your story, all the files in the story source folder are gathered up automatically, and everything gets compiled together into a single self-contained HTML file.

In the future I'll be exploring additional tools and visualizations to help authors understand, trace, and debug the complexity of large, deeply-branching narratives. Those tools and visualizers will likely be the most experimental, and pivotal, aspects of fractive's development.

Anything you'd like to review?

[What does it look like when a link calls a Javascript function?]({#FunctionLink})
[What happens if I set the link URL to a variable macro?]({#VariableLink})
[What else can I use macros for?]({@InlineMacros})
[Can I use Markdown styling?]({@AboutFormatting})
