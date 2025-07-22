# ac-library-python-stubs

[日本語のREADME](README_ja.md)

A package that adds type stubs for static analysis to [not522/ac-library-python](https://github.com/not522/ac-library-python).

Mainly adds Generic types to SegTree, LazySegmentTree, and FenwickTree.

Specifically, this allows you to specify types in places where `typing.Any` was previously used:

```python
Mono = tuple[int, int]
def op(x: Mono, y: Mono) -> Mono:
    return (x[0] + y[0], x[1] + y[1])
seg = SegTree(op, (0, 0), 10)
# > seg.prod(l: int, r: int) -> Mono

fen = FenwickTree[float](10)
# > fen.add(x: int, v: float) -> None
```

## Installation
```bash
pip install ac-library-python-stubs
```

## Requirement
- python 3.9+
- [ac-library-python v0.1.0](https://github.com/not522/ac-library-python/releases/tag/v0.1.0)

> [!NOTE]
> As of 2025-07-21, https://atcoder.jp judge uses [ac-library-python@58f324e](https://github.com/not522/ac-library-python@58f324ec020d57191e7b9e4957b0c5feb5ed3aff), which shows package version `0.0.1`, but the code has no differences from `0.1.0`.
