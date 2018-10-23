# Extract a compound conditional

Please watch the first 5 minutes of this video: https://www.youtube.com/watch?v=0rsilnpU1DU&t=13s36

The linked video is a sample of a course I created recently, and it contains my best explanation of how and why to extract compound conditionals.

Again, you only need to watch until 4:58.

For those of you that truly hate video, here’s a brief text version:

Compound conditionals look like this:

```
if foo && bar
  ...
end
```

Or

```
if foo || bar
  ...
end
```

Your language might write these slightly differently, but the essential bit is that you have a conditional whose truth depends on the truth of two components combined with a boolean logic operator.

I’ve found that extracting these compound conditionals into a named method almost always improves the code.

In abstract terms, that looks like this:

Before:

```
if foo && bar
  ...
end
```

After:

```
if higher_level_concept?
  ...
end
```

```
def higher_level_concept?
  foo && bar
end
```

And here’s a concrete example:

Before:

```
if user_created_account_today? && user_has_unconfirmed_email?
  prevent_user_from_posting
end
```

After:

```
if user_has_high_spam_risk?
  prevent_user_from_posting
end

private

def user_has_high_spam_risk?
  user_created_account_today? && user_has_unconfirmed_email?
end
```

I prefer the second version because it’s more explicit. It takes an implicit idea: “users with new accounts and unconfirmed emails are more likely to post spam” and makes it explicit in the code. This is usually a big win, since it means there is more information in the code, and less that exists only in developers’ heads.

Again, there’s even more useful info in the video https://www.youtube.com/watch?v=0rsilnpU1DU&t=13s36, and it’s only 5 minutes, so I suggest watching it.

Today’s challenge: find a compound conditional in your code (just grep for && and ||) and try extracting it into a well-named method. Try to make the new method explain a little more about what the compound conditional means at a higher level.

If the new name is a big enough improvement, consider committing/merging/opening a PR. If not, no worries. Just revert and remember this lesson next time you reach for && or ||.gg