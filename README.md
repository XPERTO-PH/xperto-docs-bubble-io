# XPERTO Bubble.io Convention
XPERTO Documentation for Bubble.io

# Quick start

It is recommended to install `docsify-cli` globally, which helps initializing and previewing the website locally.

```bash
npm i docsify-cli -g
```

# Preview your site

Run the local server with `docsify serve`. You can preview your site in your browser on `http://localhost:3000`.

```
docsify serve docs
```

# Writing more pages

If you need more pages, you can simply create more markdown files in your docsify directory. If you create a file named `guide.md`, then it is accessible via `/#/guide`.

For example, the directory structure is as follows:

```text
.
└── docs
    ├── README.md
    ├── guide.md
    └── zh-cn
        ├── README.md
        └── guide.md
```

Matching routes

```text
docs/README.md        => http://domain.com
docs/guide.md         => http://domain.com/#/guide
docs/zh-cn/README.md  => http://domain.com/#/zh-cn/
docs/zh-cn/guide.md   => http://domain.com/#/zh-cn/guide
```

# Read more
For more information visit [Docsify](https://docsify.js.org/#/).