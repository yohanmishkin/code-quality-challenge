# Run tests with wifi off

[link](https://forum.codequalitychallenge.com/t/day-9-run-tests-with-wifi-off/812)

First, a warning: today’s exercise is likely to generate tasks for you that will take longer than 20 minutes to fix. This doesn’t mean something bad has happened, or that you’ve failed. Just file a ticket to remind you to complete the work later.

Today’s exercise: run your test suite with your internet connection disabled.

Turns out, it’s fairly easy to accidentally rely on an external service during test runs (I’ve done it many times). This won’t just make your test suite slow, but brittle.

Chances are, you’ll see a few cryptic failures when you try this.

In general, I recommend reaching for a tool like Webmock5 to fix issues like these.

As a bonus, Webmock has a setting to disable external web requests during test runs. If you attempt to make a connection to the outside world, you’ll get an exception. This will prevent you from writing internet-hitting tests in the future.