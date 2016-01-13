![Image of Gopher flying](https://github.com/glycerine/zygomys/blob/master/biplane.png)

# zygomys - fast, high level control

zygomys is an embeddable Lisp interpreter and REPL (Read-Eval-Print-Loop;
that is, it comes with a command line interactive interface).
zygomys is focused on Domain Specific Language (DSL) creation for your
scripting and configuration needs. It is written in Go and plays easily with Go programs
and structs defined within them. It counts as its original ancestor
[Howard Mao's inspiring Glisp project](https://github.com/zhemao/glisp).
It borrows certain constructs from Clojure, and others from Go, and
aims to make scripting and configuration very easy with a minimal footprint.

Because it speaks JSON and Msgpack fluently, zygomys is ideally suited for driving
complex configurations and providing projects with a domain specific
language customized to your challenges and driving other code.
The example snippets in the tests/*.zy provide many examples.
The full [documentation can be found in the Wiki](https://github.com/glycerine/zygomys/wiki).

The standalone REPL is called simply `zygo`.

### Not your Grandfather's Parentheses... features in zygomys 1.3.1 include

 * [x] Use `zygo` to configure trees of Go structs, and then run methods on them at natively-compiled speed (since you are calling into Go code).
 * [x] `emacs/zygo.el` emacs mode
 * [x] JSON and Msgpack interop: serialization and deserialization.
 * [x] `(range key value hash (body))` range loops mirror for-range over a hash in Go.
 * [x] `(for [(initializer) (test) (advance)] (body))` for-loops match those in C and Go. Both `(break)` and `(continue)` are available for additional loop control.
 * [x] Raw bytes type `(raw string)` lets you do zero-copy `[]byte` manipulation.
 * [x] Record definitions `(defmap)` make configuration a breeze.
 * [x] Files can be recursively sourced with `(req path)` or `(source "path-string")`.
 * [x] Go style raw string literals, using `` `backticks` ``, can contain newlines and `"` double quotes directly. Easy templating.
 * [x] Easy to extend. See the `repl/random.go`, `repl/regexp.go`, and `repl/time.go` files for examples.
 * [x] Clojure like threading `(-> hash field1: field2:)` and `(:field hash)` selection. 
 * [x] Macros for your DSL. Syntax-quote templates work *anywhere*; inside lists, `[]` arrays and `{}` hashes.

### Obligatory XKCD

![Obligatory XKCD: "elegant weapons... for a more civilized age"](http://imgs.xkcd.com/comics/lisp_cycles.png)


### Additional features

 * [x] zygomys is a small Go library, easy to integrate and use/extend.
 * [x] Float, Int, Char, String, Symbol, List, Array, and Hash datatypes builtin.
 * [x] Arithmetic (`+`, `-`, `*`, `/`, `mod`, `**`)
 * [x] Shift Operators (`sll`, `srl`, `sra`)
 * [x] Bitwise operations (`bit-and`, `bit-or`, `bit-xor`)
 * [x] Comparison operations (`<`, `>`, `<=`, `>=`, `==`, `!=`, and `not=`)
 * [x] Short-circuit boolean operators (`and` and `or`)
 * [x] Conditionals (`cond`)
 * [x] Lambdas (`fn`)
 * [x] Bindings (`def`, `defn`, and `let`)
 * [x] Standalone and embedable REPL.
 * [x] Tail-call optimization
 * [x] Go API
 * [x] Macro System
 * [x] An actual *working* macexpand. `(macexpand your-macro)` makes writing/debugging macros easy. 
 * [x] Syntax quoting -- with caret `^()` instead of backtick.
 * [x] Channel and goroutine support
 * [x] Pre- and Post- function call hooks

[See the wiki for lots of details and a full description of the zygomys language.](https://github.com/glycerine/zygomys/wiki).

### where did the name zygomys come from?

zygomys is a contraction of Zygogeomys, [a genus of pocket gophers. The Michoacan pocket gopher (Zygogeomys trichopus) finds its natural habitat in high-altitude forests.](https://en.wikipedia.org/wiki/Michoacan_pocket_gopher)

The term is also descriptive. The stem `zygo` comes from the Greek for yoke, indicating a pair or a union of two things, and `mys` comes from the Greek for mouse. The union of Go and Lisp in a small cute package, that is zygomys.

### License

Two-clause BSD, see LICENSE file.

### Author

Jason E. Aten, Ph.D.

### Credits

The ancestor dialect, [Glisp](https://github.com/zhemao/glisp), was designed and implemented by [Howard Mao](https://zhehaomao.com/).

The Go gopher was designed by Renee French. (http://reneefrench.blogspot.com/)
The design is licensed under the Creative Commons 3.0 Attributions license.
Read this article for more details: https://blog.golang.org/gopher

[XKCD https://xkcd.com/297/](https://xkcd.com/297/) licensed under a Creative Commons Attribution-NonCommercial 2.5 License(https://xkcd.com/license.html).
