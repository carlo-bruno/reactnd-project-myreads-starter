# MyReads

## Carlo Bruno | Udacity Front End Nanodegree

### Project \#6 React Application

## Table of Contents

- [Introduction](#introduction)
- [How to Use](#how-to-use)
- [For Developers](#for-developers)
- [Building the App](#building-the-app)

## Introduction

This is a Book shelf and sorter app made with ReactJS.

The main page of the app displays books that are sorted into three different shelves. Books can be moved to a different shelf by using their respective drop down menu, showed as a button at the lower right of the book image.

The search page allows users to search for books by title or author. Note that the search functionality of the back-end is limited to a particular set of search terms. Refer to [SEARCH_TERMS.md](SEARCH_TERMS.md).

The resulting books from the search may be moved to a particular shelf in the main page using the same drop down menu. Books that are shown in the main page will have their respective shelves selected in the said menu.

---
## How to Use

This application is used to help manage a list of books and organize them into the following categories: Currently Reading, Want to Read, and Read. The option 'None' will remove the book from the user's library.

The Seach Page, accessed by the "+" button or by going to the URL "/search", allows users to search and add books to their library.

You can go back to the Main Page by using the &larr; next to the input, or by simply using your browser's back button.

### For Developers

This was created using `create-react-app` so it is very simple to get started.

1. Clone this [repo](https://github.com/carlo-bruno/udacity-fend-project-myreads) or
`git clone https://github.com/carlo-bruno/udacity-fend-project-myreads.git`
2. Go to the application folder, install dependencies using `npm install`
3. Run the application `npm start`

## Building the App

This is how structured my React Components

```bash
├── <App />
│   └─ <BookLibrary /> # Main Page
│      └─ <BookShelf /> # One BookShelf for each category
│         └─ <Book />
│            └─ <BookChanger />
└── <SearchBooks /> # Search Component
    └── <Books />
        └── <BookChanger />

# React Router is used to traverse between pages
```

_App.js_ is the only stateful component of this build. It holds the state of both the Main Page books as well as the Search Page.

### Built with
+ [Create React App](https://github.com/facebookincubator/create-react-app)
+ [React 16](https://reactjs.org/)
+ [React Router](https://reacttraining.com/react-router/)

### Tutorials and ideas
+ [Thinking in React](https://reactjs.org/docs/thinking-in-react.html)
+ [React Udemy Course by Maximilian Schwarzmüller](https://www.udemy.com/share/1000uMBUQScFpQQw==/)
+ [Free React.js Bootcamp](https://www.youtube.com/watch?v=8GXXGJRDMdQ) by [Tyler McGinnis](https://tylermcginnis.com/)
+ [Study Jam by Maeva NAP](https://www.youtube.com/watch?v=i6L2jLHV9j8&t=8s)

---

## A Udacity Project

This is the starter template for the first project for Udacity's React Fundamentals course. The goal of this template is to save time by providing a static example of the CSS and HTML markup that may be used, but without any of the React code that is needed to complete the project. 

The students are given these files:

```bash
├── CONTRIBUTING.md
├── README.md - This file.
├── SEARCH_TERMS.md
├── package.json
├── public
│   ├── favicon.ico
│   └── index.html
└── src
    ├── App.css
    ├── App.js
    ├── App.test.js 
    ├── BooksAPI.js
    ├── icons
    │   ├── add.svg
    │   ├── arrow-back.svg
    │   └── arrow-drop-down.svg
    ├── index.css
    └── index.js
```
---
### Backend Server

To simplify development process, Udacity provided a backend server for students to develop against. The provided file [`BooksAPI.js`](src/BooksAPI.js) contains the methods needed to perform necessary operations on the backend:

- [`getAll`](#getall)
- [`update`](#update)
- [`search`](#search)

### `getAll`

Method Signature:

```js
getAll();
```

- Returns a Promise which resolves to a JSON object containing a collection of book objects.
- This collection represents the books currently in the bookshelves in the app.

### `update`

Method Signature:

```js
update(book, shelf);
```

- book: `<Object>` containing at minimum an `id` attribute
- shelf: `<String>` contains one of ["wantToRead", "currentlyReading", "read"]
- Returns a Promise which resolves to a JSON object containing the response data of the POST request

### `search`

Method Signature:

```js
search(query);
```

- query: `<String>`
- Returns a Promise which resolves to a JSON object containing a collection of a maximum of 20 book objects.
- These books do not know which shelf they are on. They are raw results only. We have to make sure that books have the correct state while on the search page.

