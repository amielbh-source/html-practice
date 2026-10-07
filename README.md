# HTML Practice

Hands-on HTML exercises for students who are learning to structure a web page. Each practice is a small page, a short brief, and an automated test. The tests look at the document the browser would build, so a passing result means the page has the right elements, text, and attributes.

The exercises are grouped into ten chapters. Each chapter is one subject from the course presentations, in teaching order. The environment-setup presentation (VS Code, Live Server, and extensions) is not a chapter here.

## Who it is for

Students who are new to HTML and can open a folder in VS Code. You edit `index.html`. In [Link a Stylesheet](07-head-and-metadata/03-link-a-stylesheet/), you also connect a `style.css` file. You do not need a browser to run the tests.

CSS properties such as color, fonts, the box model, and layout are not in this set. The third course presentation could not be read when these exercises were written, so those topics were left out rather than guessed.

## How a practice works

1. Open the next chapter, starting at [01 — Text](01-text/).
2. Open the next exercise in that chapter, starting at [Hello Heading](01-text/01-hello-heading/).
3. Read that folder's `README.md`.
4. Edit `index.html`. A comment marks the spot to write in.
5. Run the test for that exercise.
6. Read the failure message, change the page, and run the test again.

The early pages ask for one element. Later pages ask you to combine headings, regions, media, and forms you have already practiced.

The files `index.html`, `moshe.html`, and `images/` in the repository root are separate from this exercise set. Do the work in the numbered chapter folders.

Leave these files as they are:

- `test.js` in each practice
- `lib/`
- `package.json`, `package-lock.json`, and `jest.config.js`
- `.github/workflows/tests.yml`
- `solutions/`

`solutions/` holds one finished page per practice so the tests themselves can be checked. Try the exercise before you open a solution.

## Install

You need Node.js 20 or newer. The GitHub Action uses Node.js 24.

```bash
npm install
```

## Run the tests

Every practice:

```bash
npm test
```

One exercise:

```bash
npm test -- 01-add-a-link
```

One chapter:

```bash
npm test -- 02-links
```

Check the reference solutions:

```bash
npm run test:solutions
```

A failing practice test means that page is not finished. The message names the missing element or the text it expected, for example: `Expected the <h1> text to be "Hello World".`

## Work on one exercise

```bash
cd 02-links/01-add-a-link
```

Edit `index.html`, then from the repository root:

```bash
npm test -- 01-add-a-link
```

You can also open `index.html` with Live Server in VS Code. The tests do not need that preview.

## GitHub Actions

`.github/workflows/tests.yml` runs on every push and pull request. It checks out the repository, installs Node.js 24, installs dependencies, and runs the tests.

Two jobs run:

| Job | What it checks |
| --- | --- |
| Practice exercises | Your `index.html` files inside the chapter folders |
| Reference solutions | The pages in `solutions/` |

The practice job stays red until the exercises are solved. The reference job should stay green. That second job tells you the tests still describe the tasks correctly.

## Recommended order

Finish each chapter before the next one, and do the exercises inside a chapter from 01 upward. Chapter 10 combines the earlier subjects into full pages.

| Chapter | Exercises |
| --- | --- |
| [01 — Text](01-text/) | Hello Heading, A Paragraph, Heading and Paragraph, Emphasis, Heading Hierarchy |
| [02 — Links](02-links/) | Add a Link, A Relative Link, Meaningful Link Text |
| [03 — Lists](03-lists/) | An Unordered List, Lists |
| [04 — Images](04-images/) | Add an Image, Image and Link |
| [05 — Tables](05-tables/) | A Simple Table |
| [06 — Forms](06-forms/) | A Simple Form, Accessible Labels, A Complete Form |
| [07 — Head and Metadata](07-head-and-metadata/) | Head and Metadata, HTML Comments, Link a Stylesheet |
| [08 — Semantic Structure](08-semantic-structure/) | Page Regions, Article and Aside, A Semantic Article |
| [09 — Media and Embeds](09-media-and-embeds/) | Video and Audio, Captions and Embeds |
| [10 — Pages](10-pages/) | Personal Profile, About Me |
