# Summary for the 56th meeting of Ecma TC39

- [SharedArrayBuffer](https://github.com/tc39/ecmascript_sharedmem) reached Stage 4
  - test262 tests written
  - Specification is done, integration in progress
    - See especially detailed notes for users and implementers about memory model
  - Four browsers have implementations behind a flag
- Bug fixes
  - Another [cleanup](https://github.com/tc39/ecma262/pull/767) to module namespace objects
  - Considered [earlier errors for bad super usage](https://github.com/tc39/ecma262/pull/762); looking for implementation feedback
  - [Revert](https://github.com/tc39/ecma262/pull/781) the semantics for `class extends null` to the ES2015 state
  - Fixing up [another funny case](https://github.com/tc39/ecma262/issues/753) in sloppy-mode block-scoped function hoisting--committee agrees on shape of solution; more spec mechanics work needed
- This is it for new features in ES2017
  - See a summary of [features](http://www.2ality.com/2016/02/ecmascript-2017.html) by Axel Rauschmeyer
  - Many bug fixes, web reality fixes and non-normative cleanups
  - The branch is (logically) cut; we can still backport bug fixes.
- Making TC39 and specifications more accessible
  - Consider a multipage version of the specification to augment the single-page one
  - Improve community outreach, e.g., meet with user groups to discuss their needs
  - In the May meeting, we'll devote three days for discussing the vision for JavaScript
- Null propagation operator reached stage 1 [slides](https://docs.google.com/presentation/d/11O_wIBBbZgE1bMVRJI8kGnmC6dWCBOwutbN9SWOK0fU/view#slide=id.p)
  - Strawman syntax: `x?.y` => `x === undefined ? x : x.y`
- Intl (ECMA 402)
  - New proposals for options for DateTimeFormat: [hourCycle](https://github.com/zbraniecki/proposal-ecma402-hourcycle) and [style](https://github.com/tc39/ecma402/issues/108)
  - Intl in ES2017 will have [Intl.DateTimeFormat.prototype.formatToParts](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DateTimeFormat/formatToParts) and [constructor web-compat fix](https://github.com/tc39/ecma402/pull/84)
- Administration
  - TC39 is looking for a chair or other management structure! Please let us know if you have any good candidates
  - Code of Conduct [proposed](https://github.com/tkellen/tc39-code-of-conduct-proposal/blob/master/Conduct.md) based on JSFoundation Code of Conduct. Input wanted.
  - Jordan Harband will be TC39's official "GitHub Curator", helping keep track of current status of proposals
  - We will have a template to help new spec authors through the process
- [Unambiguous module grammar](https://github.com/bmeck/UnambiguousJavaScriptGrammar) did not reach consensus
- Larger integer types
  - Initially, [proposal](http://es.slideshare.net/BrendanEich/int64) for Int64/Uint64
  - Instead, pursuing BigInts, see [explainer](https://github.com/littledan/proposal-bigint).
- Library proposals
  - New Stage 1 proposals:
    - Standardization of [Error.prototype.stack](https://github.com/ljharb/proposal-error-stacks) and more detailed stack introspection
    - [Realm API](https://github.com/tc39/proposal-realms) for isolation, virtualization and more in a light-weight context
  - RegExp features
    - [Overview of proposals](https://mathiasbynens.be/notes/es-regexp-proposals) by Mathias Bynens
    - [Named groups](https://github.com/tc39/proposal-regexp-named-groups) got to Stage 2; still working out details
    - Other proposals had Stage 3 reviewers named; we may have a decent package of features for ES2018
  - [Promise.prototype.finally](https://github.com/tc39/proposal-promise-finally) made tweaks, got Stage 3 reviewers
  - [global](https://github.com/tc39/proposal-global) faces web compat issues, looking for a new name
- Public and private class fields
  - Remain at Stage 2
  - May get new syntax starting with `own` for instance fields (e.g., `class X { own y = z; own #a = b; static c = d; }`)
  - Anticipating proposal to change order of evaluation for object literals, to be consistent with [Munich resolution on class evaluation order](https://github.com/tc39/tc39-notes/blob/master/es7/2016-05/classevalorder.pdf)