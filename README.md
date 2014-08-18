# SC_TestComponent

A strawman component to be shared across different apps

## Requirements for apps using components from the "SC_" ecosystem

- Only base styles are SC_base

## Requirements for authoring components

Base styles won't change without a version bump, so you can rely on them.

But be mindful of [properties](http://stackoverflow.com/a/5612360/91934) that your component may inherit from ancestor components. In particular:

- Prefer px for dimensions, unless you're intentionally baking in the ability for the component to inherit different font-sizes



## Unsure

Should each component commit compiled versions to a `dist` directory?

#### Pros:

- consumer apps don't need to know how to compile anything - just need a method of requiring & concatenating plain CSS (and one day JS) files out of a `node_modules` directory
- and thus, fast compile times in consumer apps!
- Fewer rigid rules around authoring components (don't need Sass or Coffee? Write CSS or JS, consumer apps don't care)
  
#### Cons:

- Compiled crud in commit diffs
- Every component needs its own compilation method (but extractable into a common npm module)
- No way for browserify/webpack to dedup dependencies (only really an issue for JS components)
