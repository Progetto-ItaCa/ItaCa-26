# ItaCa 2026 talk abstracts

Edit **main.tex**. Its talk and names are illustrative. Set the talk title with
`\title{...}`, the presenting speaker with `\author{...}`, their affiliation with
`\institute{...}`, their email address with `\speakeremail{...}`, and collaborators
with `\jointwork{...}`. For a solo talk, delete the last command. You can use
ordinary prose and punctuation in either name field. Enter the email as plain text.
You can omit either contact field independently.

Write the abstract inside the `abstract` environment. Keep any references
after it. The text flows across pages automatically. On subsequent pages,
`\titlerunning{...}` sets a short heading alongside the page number.
It defaults to the workshop name when omitted. The diagram and reference
in the sample can both be deleted.

## Compile

Upload this ZIP as a new Overleaf project and compile **main.tex** with
**pdfLaTeX**. On a full TeX Live installation, run `latexmk -pdf main.tex`,
or run `pdflatex main.tex` twice. A minimal installation also needs the
Montserrat and Open Sans TeX font packages (`montserrat`, `opensans`).

## Design and sources

- **easychair.cls** is the unmodified EasyChair 3.5 class from the [official
  LaTeX distribution](https://easychair.org/publications/for_authors).
  The template uses the class's one-column A4 geometry, 145 mm measure,
  10 pt base size and compact bibliography.
- **itaca-abstract.sty** contains the workshop masthead, title treatment,
  speaker details, collaborator credit and continuation header. It uses Montserrat and Open Sans
  for headings and names, and Latin Modern for the abstract and mathematics.
- The [workshop site](https://progetto-itaca.github.io/ItaCa-26/) supplies
  the event details and palette. **assets/itaca-logo.png** is the
  [ItaCa wordmark](https://progetto-itaca.github.io/assets/images/itaca_logo.png).
