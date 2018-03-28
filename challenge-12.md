# Audit your dependencies

[link](https://forum.codequalitychallenge.com/t/day-16-audit-your-dependencies/816)

Crack open your Gemfile, package.json, setup.py, or whatever file your language/dependency manager uses.

Give it a slow scan. Ask yourself:

Do you still need everything in there?

Does anything need to be updated?

Can you reduce a production dependency to a development/test one?

Rubyists: maybe run bundler-audit3 to automatically check for gems with known vulnerabilites.

Is your file nicely laid out and sorted alphabetically? Should it be?