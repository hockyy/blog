---
title: Why You Should Blog
tags: [Blogging Tips]
toc: true
toc_label: "Contents"
author_profile: true
excerpt: First attempt of Hocky's productivity over the suck summer vacation. 🐜
published: true
---

## Introduction

Holy, when I wrote the post before this one, I kept on getting some ideas about stuffs. Here is some of it.

## Markdown Blog Posting

I mainly use markdown (It's like a text language with lots of good syntax, it basically parses your stuffs with html, and you can do lots of things with it).

This is some of my favorite tags

```markdown
<!-- Spoilers -->
<details>
  <summary>Spoiler title here</summary>
  Spoiler text here
</details>

<!-- Strikethrough -->
<strike> asdasd </strike> 

<!-- Posting images -->
<div align="center"><img src="your-link-here" alt="alt-title-here" width="700"/><br> <b><i>Title here</i></b></div> <br>

<!-- Quoting or emphases -->
> asdasdasd

<!-- Line break -->
This is the line 1 (insert space two times)*space**space*
This it the line 2
```

The result will be like
<!-- Spoilers -->
<details>
  <summary>Press Me</summary>
  

  <div align="center"><img src="https://i.ibb.co/n6662w4/rickroll.jpg" alt="rickroll" width="400"/><br> <b><i>Never Gonna Give You Up</i></b></div> <br>

  <strike>Never Gonna Let You Down</strike> 
  > Never gonna run around and desert you
</details>

<br>
Don't forget to use the comment markdown feature to make sure what image to insert while you still remember and what stuffs you should write.  
<div align="center"><img src="https://i.ibb.co/Fg6cKVr/Markdown-Comments.png" alt="md-comments" width="600"/><br> <b><i>Markdown Comments</i></b></div> <br>

## Windows Tips

Windows is good, we all know that. One of its most strongest feature is snip and sketch. Try to press these combinations of key:

### Snip and Sketch

The magic buttons 🏹:

`⊞ Win + ⇧ Shift + S`

Best tool for doing fast snip and sending it to people through chat messenger, like Whatsapp, LINE, or Facebook messenger. Just simply `Ctrl + V` to the chat box and Voila!

**Windows 1-0 Linux**

### Windows Clipboard

The magic buttons 🏹:

`⊞ Win + V`

Don't forget to toggle the clipboard in Settings → System → Clipboard.

<div align="center"><img src="https://i.ibb.co/F85Fq9V/Clipboard-Setting.png" alt="clipboard-win-10" width="600"/><br> <b><i>Clipboard Settings Windows 10</i></b></div> <br>

**Windows 2-0 Linux**

### Paste Into File Github

Download this [PasteIntoFile](https://github.com/EslaMx7/PasteIntoFile) App, so you can right click on desktop and save your snip. It's that simple. You can even save texts and stuff. Don't forget to put the binary executable files into your wanted folder of programs, not just the download folder. ☹️

<div align="center"><img src="https://i.ibb.co/4mhfvMg/Paste-Into-File.png" alt="paste-into-file" width="200"/><br> <b><i>Paste Into File Look</i></b></div> <br>

As it modifies your registry and add a context menu when first opening it, it basically allows you to do the right click and save stuff. 😄

I'll show you how to fix it, if you accidentally move, put, or delete it in the wrong place.

**Windows 3-0 Linux**

### Run

The magic buttons 🏹:

`⊞ Win + R`

type `cmd` for fast command prompt.  
type `regedit` for registry editor.  
type `dxdiag` for quick inspection of your computer specifications.

**Windows 4-0 Linux**

## C++, Auto, Template, and Function Expression

This is a bit out of context, but here is some good stuffs you should try. I'll just give you the idea and not explain too much. Why? Because
<strike>IM LAZY AF BOI</strike> it's better for you to explore it by yourselves.

In C++11 you can do something like this:
```c++
auto y = [] (int first, int second){
  return first + second;
};

y(0, 2);
```
It's basically the same thing with arrow function and lambda in JavaScript and Python.

You can also do this if in the function you have some sort of stuffs you should refer by reference. It's called the capture clause and it will take the outer scope (out the function).

Pass stuffs by reference:
```c++
vector <int> arr(1000);
auto y = [&] (int first, int second){
  return arr[first] < arr[second];
};
y(1, 4);
```

Pass stuffs by value:
```c++
vector <int> arr(1000);
vector <int> arrB(1000);
auto y = [=] (int first, int second){
  return arr[first] < arr[second];
};
y(1, 6);
```

Pass stuffs you choose:
```c++
vector <int> arr(1000);
vector <int> arrB(1000);
auto y = [arrB, &arr] (int first, int second){
  return arr[first] < arr[second];
};
y(1, 6);
```

You get the point. If it's empty, it's not capturing anything. If you wanna pass something by value, you can skip the `=` prefix, but if you wanna pass something by reference, you can use the `&` prefix before the variable. 💻

Here is how you recurse:
```c++
auto dfs = [&dfs, adjList] (int pos){
  // Do your stuffs here
};
y(1, 6);
```

Use this code at your own risk and don't forget to google stuffs. all of the above might be a lie or even can't be compiled. HAHAHAHAHAHA. Just wanna show you how you can do stuffs out of context. 😆

> I DON'T EVEN KNOW WHY THIS PART CAN GET INTO THIS POST.

## Regedit Context Menu

Paste into file (the app I showed you before) can be a trick when error. To fix, here is the step:

- Open the registry editor
- Go to `Computer\HKEY_CLASSES_ROOT\Directory\Background\shell\Paste Into File`
- Aight, fix it yourself. It's intuitive.
- It basically adds an option to allow the "Right Click Paste" trick. So yeah, I'm too lazy to explain.
- Profit