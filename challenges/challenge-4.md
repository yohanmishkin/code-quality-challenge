# Excise some unused code

Let’s track down some code that’s not actually in use (and delete it, naturally).

Those of you with statically-compiled languages will probably have little to do today, but in dynamic languages like Ruby and JavaScript, it’s pretty easy to end up with unused code laying around.

To track down your unused code, I recommend a tool like unused: https://unused.codes/25. I’ve personally used it to good effect in Ruby, and I believe it will work well with JavaScript and Elixir (see the docs).

If you have a different method for finding unused code that works well for you, please share it here so others can benefit.

As always, please share your results. I’d love to hear how many lines you manage to excise.