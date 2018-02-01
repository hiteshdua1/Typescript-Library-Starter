# How to Contribute

## Getting setup

1. Clone this repository
```bash
git clone .......................
cd "...folder name..."
```
2.  Install dependencies
```bash
yarn # or 'npm install'
```

## Code reviews

All submissions, including submissions by project members, require review. We
use GitHub pull requests for this purpose. Consult
[GitHub Help](https://help.github.com/articles/about-pull-requests/) for more
information on using pull requests.

## Code Style

- coding style is fully defined in ........
- code should be annotated with tyoeDoc Tags
- comments should be generally avoided. If the code would not be understood without comments, consider re-writing the code to make it self-explanatory

To run code linter, use:
```
npm run lint
```

## Commit Messages

Commit messages should follow the Semantic Commit Messages format:

```
label(namespace): title

description

footer
```

1. *label* is one of the following:
    - `fix` - ..... bug fixes
    - `feat` - ..... features
    - `docs` - changes to docs, e.g. `docs(api.md): ..` to change documentation
    - `test` - changes to .... tests infrastructure
    - `style` - .... code style: spaces/alignment/wrapping etc
    - `chore` - build-related work, e.g. doclint changes / travis / appveyor
1. *namespace* is put in parenthesis after label and is optional
2. *title* is a brief summary of changes
3. *description* is **optional**, new-line separated from title and is in present tense
4. *footer* is **optional**, new-line separated from *description* and contains "fixes" / "references" attribution to github issues
5. *footer* should also include "BREAKING CHANGE" if current API clients will break due to this change. It should explain what changed and how to get the old behavior.

Example:

```
fix(Cell): fix cell.pizza method

This patch fixes cell.pizza so that it works with rows.pizza.

Fixes #111, Fixes #222

BREAKING CHANGE: cell.pizza now delivers pizza at prison by default.
To deliver to a different location, use "deliver" option:
  `cell.pizza({deliver: 'work-prison'})`.
```

## Adding New Dependencies

For all dependencies (both installation and development):
- **Do not add** a dependency if the desired functionality is easily implementable
- if adding a dependency, it should be well-maintained and trustworthy

A barrier for introducing new installation dependencies is especially high:
- **do not add** installation dependency unless it's critical to project success

## Writing Tests

- every feature should be accompanied by a test
- every public api event/method should be accompanied by a test
- tests should be *hermetic*. Tests should not depend on external services.
- tests should work on all three platforms: Mac, Linux and Win.

.... tests are located in [test/test.js](https://github.com/.../master/test/test.js)
and are written with a [TestRunner](https://github.com/.../master/utils/testrunner) framework.
Despite being named 'unit', these are integration tests, making sure public API methods and events work as expected.

- To run all tests:
```
npm run unit
```

## Public API Coverage

Every public API method or event should be called at least once in tests. To ensure this, there's a coverage command which tracks calls to public API and reports back if some methods/events were not called.

Run coverage:

```
npm run coverage
```

## Debugging 
See [Debugging Tips](README.md#debugging-tips) in the readme

