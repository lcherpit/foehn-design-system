---
title: "Fœhn - VD.ch"
status: ready
---

## Under development !

**This styleguide is under development. Please, refer to the [official one](http://dsi-vd.github.io/foehn/).**

## What is a styleguide ?

According to wikipedia, a styleguide is:<br>
_A set of standards for the writing and design of documents, either for general use or for a specific publication, organization, or field. (It is often called a style sheet, though that term has other meanings.) A style guide establishes and enforces style to improve communication._

## Framework

This styleguide is extensively based on the framework Bootstrap version 4 using the preprocessor SASS. Further information can be fetched on [the official documentation](https://v4-alpha.getbootstrap.com/)

## Content & hierarchy

All the components are organized accordingly to the [atomic design](http://atomicdesign.bradfrost.com/) philosophy by Brad Frost.<br>
You can navigate through all theses components with the help of the left side navigation bar.

Additionaly, a few example pages are designed to give an overview of all these elements integrated together

## Usage

Each component are listed with a quick documentation box and an example of the displayed element with his source code. It should give you all the infos to apply this design guideline to any web tools you seek to develop

More technical infos (to use or contribute to the styleguide) are referenced on the README file of the repo [FOEHN](https://github.com/DSI-VD/foehn)

## Getting started

### Install as node dependency

With Yarn:

```bash
$ yarn add https://github.com/DSI-VD/foehn
```

or

```bash
$ yarn add git+ssh://git@git.etat-de-vaud.ch:typo3/foehn
```

or NPM:

```bash
$ npm install https://github.com/DSI-VD/foehn
```

or

```bash
$ npm install git+ssh://git@git.etat-de-vaud.ch:typo3/foehn
```

### How to include

Put this in your `<head/>` tag:

```html
{% render '@styles-header' %} {% render '@scripts-header' %}
```

Put this just before the closing `</body>` tag:

```html
{% render '@scripts-footer' %}
```
