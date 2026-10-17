# m01l04-05 · Following the tree down to the file

**Lesson:** [What A Commit Really Is](https://learnsome.tech/learn/git-course/m01l04) (lesson 1.4, module 1: How Git Thinks) · Free  
**Check:** Graded

## Goal

You will be able to open a commit object and name every field inside it.

## Files

- [`starter/session.sh`](starter/session.sh): the listing from the lesson
- [`expected.txt`](expected.txt): the output the check compares with
- [`check.json`](check.json): how `./check` runs and checks this lab

## Steps

1. Go to the starter: `cd labs/m01l04/m01l04-05/starter`
2. Read `session.sh`.
3. The session types these commands, in order:

   ```sh
   git cat-file -p 'HEAD^{tree}'
   git cat-file -t HEAD:notes.txt
   git cat-file -p HEAD:notes.txt
   ```
4. Run it: `bash session.sh`.
5. Check it from the repository root: `./check m01l04-05`.

## Expected output

```text
$ git cat-file -p 'HEAD^{tree}'
100644 blob 06fcdd77c9348567c50638b30d406500f521c304	notes.txt
$ git cat-file -t HEAD:notes.txt
blob
$ git cat-file -p HEAD:notes.txt
first line
second line
```

## How to check

`./check m01l04-05` copies `starter/` into a scratch directory and runs `bash session.sh` there, the way the site's lab sandbox does: that directory is the working directory and `HOME`, `LANG=C.UTF-8`, `TZ=UTC`, a limit of 10 seconds and 256 KiB of output per stream.

It passes when the output matches `expected.txt` by the site's rules, within the limits. Standard output and standard error are compared after what depends on the machine or the git release is masked: object ids, dates, temporary directories, transfer sizes, the git version, `hint:` advice lines, the padding of counts and blank lines. A pass here is a pass on the site.

---

[Open the lesson on LearnSome.tech](https://learnsome.tech/learn/git-course/m01l04) · [All labs of this lesson](../README.md) · [Course README](../../../README.md)
