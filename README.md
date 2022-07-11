# rads.hasht

This is a fork of [`hashp`](https://github.com/weavejester/hashp) which includes the `#t` reader tag to call `tap>` in addition to printing.

The original library was written by [@weavejester](https://github.com/weavejester) and the [PR for `#t`](https://github.com/weavejester/hashp/pull/16) was provided by [@PEZ](https://github.com/PEZ).

## Install

Installation is the same as `hashp` except using `rads/hasht` as the dependency.

### Leiningen

Add the following to `~/.lein/profiles.clj`:

```edn
{:user
 {:dependencies [[rads/hasht "0.2.1"]]
  :injections [(require 'hashp.core)]}}
```

### Boot

Add the following to `~/.boot/profile.boot`:

```clojure
(set-env! :dependencies #(conj % '[rads/hasht "0.2.1"]))

(require 'hashp.core)
(boot.core/load-data-readers!)
```

### Shadow-CLJS

Add the following to `shadow-cljs.edn`:
```clojure
{:dependencies [rads/hasht "0.2.1"]
 :builds {:app {:devtools {:preloads [hashp.core]}}}}
```

Or alternatively via `~/.shadow-cljs/config.edn` and `--config-merge`:

`~/.shadow-cljs/config.edn`:
```clojure
{:dependencies [[rads/hasht "0.2.1"]]}
```

Run:
```
shadow-cljs watch app --config-merge '{:devtools {:preloads [hashp.core]}}'
```
