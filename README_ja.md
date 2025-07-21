# ac-library-python-stubs

[not522/ac-library-python](https://github.com/not522/ac-library-python) に静的解析のための型スタブを追加するパッケージです。

主に SegTree, LazySegmentTree, FenwickTree に Generic 型を追加します。

具体的には、従来 typing.Any が使われていた部分で以下のように型を指定できるようになります。

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
pip install git+https://github.com/kairi003/ac-library-python-stubs.git@v0.1.0
```

## Requirement
- python 3.9+
- [ac-library-python v0.1.0](https://github.com/not522/ac-library-python/releases/tag/v0.1.0)

> [!NOTE]
> 2025-07-21 現在 https://atcoder.jp のジャッジは [ac-library-python@58f324e
](https://github.com/not522/ac-library-python@58f324ec020d57191e7b9e4957b0c5feb5ed3aff) を使用しており、そのパッケージバージョンは `0.0.1` と表示されますが、コードは `0.1.0` と差分がありません。
