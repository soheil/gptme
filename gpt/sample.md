

---==--==---

To ignore everything in the `gpt/` directory except for `sample.md`, you can create a `.gitignore` file inside the `gpt/` directory with the following content:

```
*
!sample.md
```

This `gitignore` configuration ignores all files and directories within the `gpt/` directory (`*`), but then negates the rule and includes `sample.md` (`!sample.md`), meaning that `sample.md` will not be ignored by Git.

---==--==---

git ignore for everything in gpt/ dir except sample.md

