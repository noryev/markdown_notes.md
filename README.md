# markdown_notes.md
Sample Markdown used for Github, Emails, and Discord

# Stats API <!-- omit in toc -->

- [`ipfs.stats.bitswap([options]`](#ipfsstatsbitswapoptions)
- [`ipfs.stats.repo([options])`](#ipfsstatsrepooptions)
- [`ipfs.stats.bw([options])`](#ipfsstatsbwoptions)
  - [Parameters](#parameters)
  - [Options](#options)
  - [Returns](#returns)
  - [Example](#example)
  - 

Note: `stats.bitswap` and `bitswap.stat` can be used interchangeably. See [`bitswap.stat`](./BITSWAP.md#bitswapstat) for more details.

## `galaxyx.stats.repo([options])`

> Get stats for the currently used repo.

Note: `stats.repo` and `repo.stat` can be used interchangeably. See [`repo.stat`](./REPO.md#repostat) for more details.

## `galaxyx.stats.bw([options])`

> Get  bandwidth information.

### Parameters

None

### Options

An optional object which may have the following keys:

| Name | Type | Default | Description |
| ---- | ---- | ------- | ----------- |
| peer | [PeerId][], [CID][] or `String` | `undefined` | Specifies a peer to print bandwidth for |
| proto | `String` | `undefined` | Specifies a protocol to print bandwidth for |
| poll | `boolean` | `undefined` | Is used to yield bandwidth info at an interval |
| interval | `Number` | `undefined` | The time interval to wait between updating output, if `poll` is `true` |
| timeout | `Number` | `undefined` | A timeout in ms |
| signal | [AbortSignal][] | `undefined` |  Can be used to cancel any long running requests started as a result of this call |

### Returns

| Type | Description |
| -------- | -------- |
| `AsyncIterable<Object>` | An async iterable that yields IPFS bandwidth information |

Each yielded object contains the following keys:

- `totalIn` - is a [BigInt][bigNumber], in bytes.
- `totalOut` - is a [BigInt][bigNumber], in bytes.
- `rateIn` - is a `float`, in bytes.
- `rateOut` - is a `float`, in bytes.

### Example

```JavaScript
for await (const stats of ipfs.stats.bw()) {
  console.log(stats)
}
// { totalIn: BigInt {...},
//   totalOut: BigInt {...},
//   rateIn: number {...},
//   rateOut: number {...} }
```

A great source of [examples][] can be found in the tests for this API.

[bigNumber]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt
[examples]: https://github.com/ipfs/js-ipfs/blob/master/packages/interface-ipfs-core/src/stats
[AbortSignal]: https://developer.mozilla.org/en-US/docs/Web/API/AbortSignal
[cid]: https://www.npmjs.com/package/cids
[peerid]: https://www.npmjs.com/package/peer-id

Want to inject some flavor into your everyday text chat? You're in luck! Discord uses Markdown, a simple plain text formatting system that'll help you **make your sentences stand out**. Here's how to do it! Just add a few characters before & after your desired text to change your text! I'll show you some examples...

Check Github markdown guids and add them

## Sweet Styles

*Italics*	\*italics* **or** \_italics\_

__*Underline italics*__	\__\*underline italics*__

**Bold**	\*\*bold**

__**Underline bold**__	\__\*\*underline bold**__

***Bold Italics***	\*\*\*bold italics***

__***underline bold italics***__	\__\*\*\*underline bold italics***__

__Underline__	\_\_underline__	

~~Strikethrough~~	 \~\~Strikethrough~~

Don't want to use markdown? You can slap a backslash in front of your statement, or put your message in a code block, and it'll escape the markdown formatting. You'll see those asterisks as you'd like! Just keep in mind, it doesn't work in messages with edits or underscores.

## Block Quotes

The syntax to use Block Quotes is > or >>> followed by a space.

**\>** at the beginning of a line of text, creates a single-line block quote.

![one line block quote](https://i.imgur.com/Sjie1q4.png)

**\>\>\>** at the beginning of a line of text, creates a multi-line block quote. All text from `>>>` until the end of the message will be included in the quote.

![multiline block quote](https://i.imgur.com/6vfzz5B.png)

## Code Blocks

Discord also supports code blocks as well.  You can make your own code blocks by wrapping your text in backticks (\`)

![one line code blocks](https://i.imgur.com/MbFPHmY.png)

You can also use three backticks (\`\`\`) to create multiline code blocks, like this beautifully written haiku.

![multiline code blocks](https://i.imgur.com/4QAF6uV.png)

## Syntax Highlighting

If you really want to spruce up your code blocks, you can denote a specific language for **syntax highlighting**, by typing the name of the language you want the code block to expect right after the first three backticks beginning your code block. An example...

![syntax highlighting](https://i.imgur.com/SSzdgiw.png)

There are many different languages in place of Markdown that Discord's syntax highlighting support. Each different language has its own approach to highlight-able syntax. For a full list: https://highlightjs.org/static/demo/. Note that you won't be able to view syntax highlighting on the mobile app.

asciidoc

![asciidoc](https://i.imgur.com/V7FnZoP.png)

autohotkey

![autohotkey](https://i.imgur.com/wAbR9g1.png)

bash

![bash](https://i.imgur.com/HA0XvZc.png)

coffeescript

![coffeescript](https://i.imgur.com/pBbynIE.png)

cpp (C++)

![cpp](https://i.imgur.com/Ug5QRpi.png)

cs (C#)

![cs](https://i.imgur.com/9wwxpHo.png)

css

![css](https://i.imgur.com/5dI0lIN.png)

diff

![diff](https://i.imgur.com/CqWe4W7.png)

fix

![fix](https://i.imgur.com/oiNMvI8.png)

glsl

![glsl](https://i.imgur.com/NdiZ1q7.png)

ini

![ini](https://i.imgur.com/5eNvFJe.png)

json

![json](https://i.imgur.com/ieGxUhx.png)

md (markdown)

![md](https://i.imgur.com/4v7NHXG.png)

ml

![ml](https://i.imgur.com/9PBvwKr.png)

prolog

![prolog](https://i.imgur.com/VvfgXzk.png)

py

![py](https://i.imgur.com/sjxY2lB.png)

tex

![tex](https://i.imgur.com/aSYRfPN.png)

xl

![xl](https://i.imgur.com/nlu49Jt.png)

xml

![xml](https://i.imgur.com/4cCrGr4.png)

And you get the idea! Now you're a **Discord text markdown expert**. Get out there and highlight your statements!

## Acknowledgements

[Hammer and Chisel](https://support.discordapp.com/hc/en-us/articles/210298617-Markdown-Text-101-Chat-Formatting-Bold-Italic-Underline-)  
[Discord Highlight.js](https://discord.gg/SkZTwPk)

A special thanks to Frosty#9449 for their help in making this guide.

If you have any questions or want to get in contact with me, you can add **Matthew#2334** on Discord or join [my support server](https://discord.gg/vW49jAR).
