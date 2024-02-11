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
