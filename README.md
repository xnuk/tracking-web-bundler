## [evanw/esbuild]
### Pros
- No boilerplate for transforming/bundling javascript files - just `esbuild something.js --bundle --outfile=/path/to/out.js` and that's it
- Has IIFE output option

### Cons
- *"No boilerplate"* doesn't mean its output is correct
  - Mostly incorrect for common project, so minor tweakings may be needed
- No supports for:
  - modifying AST (which means babel-like plugin system)
  - hot module reloading
  - [These are officially non-goal for esbuild](https://github.com/esbuild/esbuild.github.io/blob/31423c64748bb35f94d3760ed24aaa31b4e8c961/src/content/faq.yml#L228-L239)
- No [HTML entry point](https://github.com/evanw/esbuild/issues/31), or regular text file output
- [No support for `react-jsx` transform](https://github.com/evanw/esbuild/issues/334)
- Minifier isn't that good; have to pass into [Terser] once after esbuild minify
- [Doesn't care about preserving comments](https://github.com/evanw/esbuild/issues/516#issuecomment-725093126)

## [swc-project/swc](https://github.com/swc-project/swc)
### Pros
- [Plugins can play with AST](https://swc.rs/docs/usage/plugins)
  - Still in beta, but [they say it won't gonna change far away](https://github.com/swc-project/swc/discussions/3540)
### Cons
- Transforming a single file needs lots of `.swcrc` boilerplate
- No IIFE output options
- Bundling isn't ready
  - No output entries support except javascript
    - Seems [there is CSS or something but undocumented](https://github.com/swc-project/swc/issues/3900)
  - [Does not minify during bundling files](https://github.com/swc-project/swc/issues/2451)
  - [Sourcemap output is absolute path, not relative to project root](https://github.com/swc-project/swc/issues/2149)

## [microsoft/TypeScript]
### Cons
- Why are you using this with hoping fast and sane build results kthx gotta sleep gnight

[Terser]: https://github.com/terser/terser
[evanw/esbuild]: https://github.com/evanw/esbuild
[swc-project/swc]: https://github.com/swc-project/swc
[microsoft/TypeScript]: https://github.com/microsoft/TypeScript
