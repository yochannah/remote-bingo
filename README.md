# Remote Bingo

![img/remote-bingo.png](img/remote-bingo.png)

[![https://img.shields.io/badge/rseng-project-purple](https://img.shields.io/badge/rseng-project-purple)](https://rseng.github.io/) [![https://good-labs.github.io/greater-good-affirmation/assets/images/badge.svg](https://good-labs.github.io/greater-good-affirmation/assets/images/badge.svg)](https://good-labs.github.io/greater-good-affirmation) [![Gitter](https://badges.gitter.im/rseng/community.svg)](https://gitter.im/rseng/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

The [Remote Bingo](https://rseng.github.io/remote-bingo/) project 
is intended to provide a fun way to play Bingo (either on your own or with others).
The interface will cache your current board, allow for export, and customizing
the items via the [remote-bingo.csv](remote-bingo.csv) file.

 - [Usage](#usage)
   - [Single Player](#single-player)
   - [Multiplayer](#multiplayer)
   - [Customize](#customize)
 - [Contributing](#contributing)


And see [this post](https://vsoch.github.io/2020/remote-bingo/#bingo-lists) for a writeup
about the development of this interface.

## Usage

Generally, you get a bingo notification when you:

 - fill a row or column
 - get a diagonal
 
And if you want to play for the super win (filling the entire board) you'll get
a bigger congratulations notification.

### Single Player

If you want to play with the current questions present in [remote-bingo.csv](remote-bingo.csv),
then just go to the [Remote Bingo](https://rseng.github.io/remote-bingo/) interface on GitHub pages and you
are good! 

### Multiplayer

While the interface isn't actually shared between people, if many people load the same
page and load the same set of items, the order of the items will be different, 
and you can play until someone has a bingo. You can strive to get bingo
for rows, columns, or (the ultimate win) is an entire board.

### Customize

However, if you want to customize this interface for your own bingo items:

 1. Fork the repository
 2. Clone your fork
 3. Edit the remote-bingo.csv to be your questions, or generate a new questions file

For the third point above, if you change the name of the file you'll need to edit [index.js](assets/js/index.js)
to load in that file:

```js
var bingo = new Bingo()
bingo.load_csv("remote-bingo.csv")
```

And then you can add other lists to the interface as follows:

```js
bingo.add_bingo_list("bingo-lists/new-programmer.csv")
bingo.add_bingo_list("bingo-lists/quarantine-cooking.csv")
bingo.add_bingo_list("bingo-lists/indoor-activities.csv")
```

And they are available at the bottom of the interface for a user to select to
change the board:

![img/choose-list.png](img/choose-list.png)

If you create a fun set of items or want to update the existing lists, 
please [contribute them here!](https://github.com/rseng/remote-bingo)

## Contributing

If you'd like to contribute, here are a few ideas:

 - create a custom list of bingo items to add to [bingo-lists](bingo-lists), or add to an existing one
 - add a color picker so the user can select the color [#2](https://github.com/rseng/remote-bingo/issues/2)
 - add support for local cache, so refreshing the page can reload a previous state [#3](https://github.com/rseng/remote-bingo/issues/3)
 - tags loaded from remote-bingo-csv (or requested file for another deploy) can be filtered [#4](https://github.com/rseng/remote-bingo/issues/4)
 - filling the entire board should have a more explosive congratulations [#5](https://github.com/rseng/remote-bingo/issues/5)
 - ability to save picture of board to file [#6](https://github.com/rseng/remote-bingo/issues/6)

This software is under a permissive [MIT License](LICENSE).

## Boards Available

Please open a PR to update and improve these lists! More items mean better randomization
and variety for playing different boards.

### Remote Bingo

The default "remote bingo" includes items that are related to working remotely,
COVID-19, and general conference calls.

![img/remote-bingo.png](img/remote-bingo.png)

### Quarantine Cooking

![img/quarantine-cooking.png](img/quarantine-cooking.png)


### Virtual Conference

![img/virtual-conference.png](img/virtual-conference.png)

### Indoor Activities

![img/indoor-activities.png](img/indoor-activities.png)

### New Programmer

![img/new-programmer.png](img/new-programmer.png)

### Cookies

![img/cookies.png](img/cookies.png)


## Thank you!

Thank you to [A Game of Dabs](https://codepen.io/nbrombal/pen/JAedG) on Codepen
that I was able to refactor into a Vue.js application to serve a custom board.
I'm terrible at JavaScript and this example was exactly what I needed to get started.
