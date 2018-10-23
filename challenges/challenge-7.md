# Slim down a large class

Sometimes, despite our best intentions, a few classes in our system get large and unwieldy.

Today’s exercise is to take a small step toward slimming down one of those classes.

First, use something like this to find your longest classes:

find ~/code/my_project -name "*.rb" | xargs wc -l | sort -rn | head

Then, pick one that looks like a good candidate and open it up.

Next, scan the file to look for opportunities to extract a new object.

When I do this, I’m looking for groups of methods that “clump together” in a related way.

Here are a few attributes that might identify “clumps” that may make sense to extract together:

    Several methods that take the same parameter.
    Several methods that access the same instance data.
    Several methods that include the same word in their name.

When you see several methods that possess some of the above attributes, try extracting them into a new class and see if it feels like a worthwhile improvement.

An important caveat: this refactoring might be tough to pull off in 20 minutes.

Since you’re working on a large class, you may find it has a lot of coupling that resists extraction.

Alternatively, you might not be able to find a good candidate for extraction.

In either case, here’s a fallback task: improve SOMETHING about the class, even if it’s tiny. Here are a few ideas:

    Delete a stray comment.
    Improve a name.
    Make something private if it’s only called internally.
    Improve the formatting/style of any ugly bits (got any trailing whitespace or inconsistent newlines?).
    Slim down a long method.
    Delete some unused code.

Finally, please don’t feel bad about any of the following:

    How long your classes are.
    The fact that you could only extract something small.
    The fact that you couldn’t find something good to extract.
    The fact that you couldn’t find a small thing to improve.

As always, this challenge is about showing up each day and taking a small step forward toward better code quality. Some days, you won’t improve the code itself, but your mind. Attempting each exercise will prime you to perform better on your next project or task.