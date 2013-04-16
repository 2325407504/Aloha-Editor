All changes are categorized into one of the following keywords:

- **BUGFIX**: The change fixes a bug.
- **FEATURE**: The change introduces a new feature, or modifies the function,
               usage, or intent of an existing one.
- **ENHANCEMENT**: The change improves the software, but otherwise makes no
                   functional change to any feature.
----


- **BUGFIX**: core: Aloha incorrectly reported that Chrome was not supported.
- **ENHANCEMENT**: state-override: when pressing a formatting
	button and the cursor is not within a word, a state override
	will be set such that any text that is subsequently typed will
	acquire the appropriate formatting.
- **ENHANCEMENT**: state-override: preserve formatting state across line breaks
	For example, when writing a word in bold, pressing enter and
	writing another word on the next line, the second word will also
	be bold. This behaviour more closely matches how popular word
	processors behave.
- **BUGFIX**: paste: paste from word causes unwanted content

	Pasting from word on OSX with Firefox caused the contents
	of style elements to be pasted as text.

	This has been fixed in the default sanitize content handler
	configuration. If you have your own santize configuration, you can
	adapt it by adding the following property

	remove_contents: ['style', 'script']
- **BUGFIX**: backspace: deleting formatted text leaves formatting in place

	For example, with the DOM looking like this <p>a<b>b{}</b>c</p>,
	hitting backspace would not delete the wrapping <b> element.
- **BUGFIX**: state-overide: insertion of non-visible characters

	When a non-text key such as backspace was pressed when a
	state-override was active, it may have been inserted as a
	non-visible character into the HTML text.
