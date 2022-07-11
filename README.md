# rads.hasht

This is a fork of [`hashp`](https://github.com/weavejester/hashp) which includes the `#t` reader tag to call `tap>` in addition to printing.

The original library was written by [@weavejester](https://github.com/weavejester) and the implementation was inspired by a [PR for `#t`](https://github.com/weavejester/hashp/pull/16) from [@PEZ](https://github.com/PEZ).

## Install

Installation is the same as `hashp` except using `com.github.rads/hasht` as the dependency.

### Leiningen

Add the following to `~/.lein/profiles.clj`:

```edn
{:user
 {:dependencies [[com.github.rads/hasht "0.2.1-alpha2"]]
  :injections [(require 'hashp.core)]}}
```

### Boot

Add the following to `~/.boot/profile.boot`:

```clojure
(set-env! :dependencies #(conj % '[com.github.rads/hasht "0.2.1-alpha2"]))

(require 'hashp.core)
(boot.core/load-data-readers!)
```

### Shadow-CLJS

Add the following to `shadow-cljs.edn`:
```clojure
{:dependencies [com.github.rads/hasht "0.2.1-alpha2"]
 :builds {:app {:devtools {:preloads [hashp.core]}}}}
```

Or alternatively via `~/.shadow-cljs/config.edn` and `--config-merge`:

`~/.shadow-cljs/config.edn`:
```clojure
{:dependencies [[com.github.rads/hasht "0.2.1-alpha2"]]}
```

Run:
```
shadow-cljs watch app --config-merge '{:devtools {:preloads [hashp.core]}}'
```
