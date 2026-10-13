# Write your first question

A question is one `question.json` file. Here is a complete multiple-choice
question:

```json
{
  "oqf_version": "0.2.0",
  "id": "capital-of-france",
  "type": "mcq",
  "title": "Capital of France",
  "statement": "What is the capital of France?",
  "type_config": {
    "options": [
      { "id": "a", "content": "Paris" },
      { "id": "b", "content": "Lyon" }
    ],
    "answer": "a"
  }
}
```

- `type` picks one of 11 question types, such as `mcq`, `fill_blank`,
  `code` or `essay`.
- `statement` is the question itself, in Markdown. A long statement can
  live in its own `statement.md` instead.
- `type_config` holds what that type needs: here, the options and the
  answer.

## Practice or graded

With the answer inline, as above, the question suits self-practice: an
app can check a learner's answer straight away. For a graded question,
move the answer into a separate file named by `answer_key`. An app
showing the question to a learner then never receives the answer.

## Put it in a set

A practice set (`set.json`) lists questions in order and gives each its
points. Points belong to the set, not the question, so the same question
can be worth different amounts in different sets.

## Check it

The `oes` command line tool validates documents and checks that every
reference resolves:

```bash
npx @inklyre/oes-lint lint ./my-course
```
