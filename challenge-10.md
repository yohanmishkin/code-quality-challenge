# Investigate your slowest test(s)

[link](https://forum.codequalitychallenge.com/t/day-10-investigate-your-slowest-test-s/814)

If you happen to use Ruby and RSpec, finding your 10 slowest tests is simply a matter of adding --profile to your test command. If you’re using something else, hopefully a similar flag is only a quick google away.

Once you’ve identified your 10 slowest tests or so, give them each a once-over.

Some things to consider:

    Are any of these tests duplicates? It’s easier than you might think to accidentally write the same test more than once. You can’t see that you’ve done this by reviewing a diff in a PR, so this type of duplication can often creep into your codebase over time.

    Can any of these tests be replaced with a faster variant? If you’re testing a conditional in the view, can you use a view spec instead of an integration spec? Can you stub expensive calls? Can you perform less setup? Can you hit less of the stack and still feel confident things work? (This video I recorded on integration vs. unit tests)[https://www.youtube.com/watch?v=kBOqaluDf2k1] might be helpful.

    Are all these tests still pulling their weight? Remember: slow tests act as a constant drag against your forward progress. Make sure the cost is outweighed by the benefits of keeping them around. I encourage you to be pragmatic. If a very slow test is verifying something that’s not mission-critical, it’s worth considering deleting it.
