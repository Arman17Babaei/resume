# Arman Babaei resume

The academic and professional resumes and the imec application use the shared
`resume.cls` layout and EB Garamond font.

| Document | LaTeX source | Generated PDF | Pages |
| --- | --- | --- | --- |
| Academic CV | `academic.tex` | `academic.pdf` | 2 |
| Professional resume | `professional.tex` | `professional.pdf` | 2 |
| imec System Software Engineer CV | `imec-cv.tex` | `imec-cv.pdf` | 2 |
| imec cover letter | `imec-cover-letter.tex` | `imec-cover-letter.pdf` | 1 |

## Build locally

Install TeX Live with `latexmk`, the `ebgaramond` and `ulem` packages, and their
dependencies. Build the application from the repository root:

```sh
latexmk -pdf -file-line-error -halt-on-error -interaction=nonstopmode imec-cv.tex imec-cover-letter.tex
```

## Continuous integration

The **Build resume PDFs** workflow compiles all four documents and verifies
their page counts on relevant pull requests, pushes to `main`, and manual runs.
Download the **resume-pdfs** artifact from the workflow run to review the PDFs.
Pull-request runs do not push changes. After a merge to `main`, the workflow
updates the tracked PDFs if the branch still matches the built revision.
