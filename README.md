# rehype-autolink-headings simple

[![bundlejs](https://img.shields.io/bundlejs/size/rehype-autolink-headings)](https://bundlejs.com/?q=rehype-autolink-headings-simple)

A simple version of [rehype-autolink-headings](https://github.com/rehypejs/rehype-autolink-headings).

Less dependencies and less useless code. Using typescript to develop.

## Usage

```bash
npm install rehype-autolink-headings-simple
```

```js
import { rehypeAutolinkHeadings } from "rehype-autolink-headings-simple";
import { unified } from "unified";
import { parse } from "rehype-parse";
import { stringify } from "rehype-stringify";

const processor = unified()
  .use(parse)
  .use(rehypeAutolinkHeadings, {
    behavior: "append",
    properties: {
      behavior: "append",
      properties: { className: ["anchor"] },
      content: { type: "text", value: "#" },
    },
  })
  .use(stringify);

const result = processor.processSync("<h1>Heading</h1>").toString();
```

## Known issues

Astro should change render order manually. See [Astro: Heading IDs and plugins](https://docs.astro.build/en/guides/markdown-content/#heading-ids-and-plugins)

## License

The MIT License (MIT).
