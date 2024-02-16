# Tailwind CSS From Scratch

Udemy course [Tailwind CSS From Scratch](https://www.udemy.com/course/tailwind-from-scratch)

Links:

- [Tailwind From Scratch](https://tailwindfromscratch.com/)
- [Tailwind sandbox](https://github.com/bradtraversy/tailwind-sandbox)
- [Tailwind CSS](https://tailwindcss.com/)

Tailwind CSS is:

- Low level classes
- Flexible
- Customizable with directives & functions
- You need to know CSS

Dynamic conditional classes:

```html
<div class="flex flex-col md:flex-row">
 <div>
  <a href="#" class="hover:text-blue-500">Item 1</a>
 </div>
</div>
```

Above - medium and up we actually want to have row. State based - on hover.

## Section 1 - Intro

### Lecture 1.5 - Environment setup

VS Code extensions:

- [Live server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
- [PostCSS Language Support](https://marketplace.visualstudio.com/items?itemName=csstools.postcss)
- [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)

And Emmet comes with VS code. Type and press tab

```html
div{Item $}*10
```

it adds:

```html
<div>Item 1</div>
<div>Item 2</div>
...
<div>Item 10</div>
```

Cmd+Shift+P - edit JSON settings.

### Lecture 1.6 - Tailwind Sandbox Setup

Follow [tailwind-sandbox-done](https://github.com/bradtraversy/tailwind-sandbox/tree/main/tailwind-sandbox-done).

## Section 2 - Fundamentals

## Lesson 2.8 - Working with colors

See [colors from sandbox starter](tailwind-sandbox-starter\02-colors\index.html)

Shades - black and white do not have shades. So we only have `text-white` and `text-black`.

If we use any color, we have to specify shade. So we have `text-red-50` for example.

The shades are from 50 to 900.

Shadow opacity is defined with `/N` where `/100` is the default:

```html
    <button class="shadow-lg bg-cyan-500 shadow-purple-500/50">
      Subscribe
    </button>
```

You can directly use arbitrary colors:

```html
    <div class="bg-[#427fab]">Hello</div>
    <div class="bg-[rgb(255,150,255)]">Hello</div>
    <div class="bg-[steelblue]">Hello</div>
```

## Lesson 2.9 - Containers and spacing

Breakpoints:

```java
    container None width: 100%;
    sm (640px)     max-width: 640px;
    md (768px)     max-width: 768px;
    lg (1024px)    max-width: 1024px;
    xl (1280px)    max-width: 1280px;
    2xl (1536px)   max-width: 1536px;
```

To make a `div` a _container_ we add class `container` and to center it horizontally we add `mx-auto` (margin on the X):

```html
<div class="container mx-auto"> ...
```

**Margins**:

- `m` all around
- `mx` horizontal
- `my` vertical
- `ml` on the left
- `mr` on the right
- `mt` on the top
- `mb` on the bottom

we can also have a numeric value from 0 to 96 proportional to the _root-em_:

```css
mx-1 margin-left: 0.25rem; /* 4px */
...
ml-96 margin-left: 24rem; /* 384px */
```

You can directly use arbitrary value like `mr-[20px]`.

**Paddings** just uses `p` instead of `m`.

**Space between** X or Y: `space-x-...` or `space-y-...`.

We can have flex row:

```html
      <div class="flex mt-4 space-x-4">
        <div>Item 1</div>
        <div>Item 2</div>
...
```

we can have flex column:

```html
      <div class="flex flex-col mt-4 space-y-4">
        <div>Item 1</div>
```

## Lesson 2.10 - Typography

We have the following _families_:

- font-sans (the default one)
- font-serif
- font-mono

You can use custom font, edit your `tailwind.config.js` when generated with `tailwind` CLI.

With the CDN we can have `script` tag:

```html
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
      tailwind.config = {
        theme: {
          fontFamily: {
            sans: ['ui-sans-serif', 'system-ui'],
            serif: ['ui-serif', 'Georgia'],
            mono: ['ui-monospace', 'SFMono-Regular'],
          },
        },
      };
    </script>
```

And if we want to add a custom font like [Google Fonts Tapestry](https://fonts.google.com/specimen/Tapestry?sort=date&query=tapestry), then we have to include the font from Google and we can use for let's say "serif":

```html
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Tapestry&display=swap"
      rel="stylesheet"
    />
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
      tailwind.config = {
        theme: {
          fontFamily: {
            sans: ['ui-sans-serif', 'system-ui'],
            serif: ['Tapestry', 'Georgia'],
            mono: ['ui-monospace', 'SFMono-Regular'],
          },
        },
      };
    </script>
```

We have the following _font sizes_: from `text-xs` to `text-9xl`.
