# What OES is

OES (Open Education Standards) is a set of open specifications for
education content: courses, practice sets, questions, articles, video
lessons and reference documents, plus a format for packaging and sharing
them.

## Plain files you can keep in git

Every OES document is a JSON file, with longer prose in Markdown. Nothing
needs a database or a server: a course is a folder you can put in a git
repository, review in a pull request, and host anywhere that serves files.
Who may read it is up to wherever you host it.

## Seven specs that compose

| Spec | Describes |
|---|---|
| OCF | A course: modules, lessons, and the items in each lesson |
| OPF | A practice set: an ordered list of questions |
| OQF | A single question, in one of 11 types |
| OAF | A written article |
| OVF | A video lesson around a video hosted elsewhere |
| ORF | A reference document, such as a PDF or a paper |
| OPK | A package: a named, versioned unit you can share |

A course doesn't contain its lessons; it points at them. Every reference
is either a `path` to a file next to it or a URL to one hosted elsewhere,
so the same question can appear in several practice sets.

## Content, not learner data

OES describes what a learner studies. Progress, attempts and grades are
deliberately left out: those belong to whatever app the learner uses.

## Read more

The full specifications are at
[open-education-standards.github.io/oes](https://open-education-standards.github.io/oes/).
