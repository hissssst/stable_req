# StableReq

[![CI](https://github.com/hissssst/stable_req/actions/workflows/ci.yml/badge.svg)](https://github.com/hissssst/stable_req/actions/workflows/ci.yml)
[![Hex Docs](https://img.shields.io/badge/documentation-gray.svg)](https://hexdocs.pm/req)

StableReq is a batteries-included HTTP client for Elixir.

With just a couple lines of code:

```elixir
Mix.install([
  {:req, github: "hissssst/stable_req", tag: "v1.0.7.4"}
])

Req.get!("https://api.github.com/repos/hissssst/stable_req").body["description"]
#=> "Req, but stable"
```

we get automatic response body decoding, following redirects, retrying on errors,
and much more. Virtually all of the features are broken down into individual functions called
_steps_. You can easily re-use and re-arrange built-in steps (see [`Req.Steps`] module) and
write new ones.

## This is a fork of Req

Req has been infamous for introducing breaking changes which lead to many incidents across various Elixir productions,
Being the most popular modern HTTP client in Elixir, it was unable to define a stable API for 4 years now.
Someone just has to do this, so thats what this fork is about.

This fork won't be locking you from updates or any new features in the upstream, it just makes
an extra step to introduce backward compatibility with codebases which use the old API

If you want to introduce a feature or a bug fix, please do this in Req: https://github.com/wojtekmach/req

If you find compatibility issues, please make an issue in this repository.

## Differences from Req

* No breaking changes, only deprecation warnings
* API will always be compatible to v0.7.4

## Versioning

If you want to use Req with features present in version `vA.B.C`, then just use the StableReq with version `v1.A.B.C`
