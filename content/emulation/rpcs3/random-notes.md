---
date: 2021-02-03T16:35
tags:
  - rpcs3
---

# Random RPCS3 Notes

## Automated clang-format checker on Pull Requests
This gist can take lines from a git diff and run clang-format on that file, which is what we want for RPCS3, to ensure new PRs get code style changes applied, without asking to reformat the entire file.
<https://gist.github.com/AtnNn/10d17408516ae408788484418740f18b>
In addition, this official tool seems to also do the same thing: <https://clang.llvm.org/docs/ClangFormat.html#script-for-patch-reformatting>