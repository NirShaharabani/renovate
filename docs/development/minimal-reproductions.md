# About minimal reproductions

You may be asked to provide a "minimal reproduction" repository to help the Renovate team debug bug reports or implement a feature.

This document explains why we need a minimal reproduction, why using large repositories to debug is undesirable, and how you can create a good minimal reproduction.

## What is a minimal reproduction?

The basic idea of a minimal reproduction is to use the least amount of both code and config to trigger missing or wrong behavior.
Having a minimal reproduction makes it easier for the developers to see where the bug or missing feature is, and to verify that the new code satisfies requirements.

### Why not use the production repository to debug?

You might think, why is a minimal reproduction even needed?
I already have the reproduction on my production repository and it's public.
Why not use that to debug?

A production repository uses many dependencies, and can have a large list of custom rules in the Renovate configuration file.
This makes it very hard to debug the repository, because there are many moving parts and debug statements could be triggered potentially hundreds of times.

When people have a large Renovate configuration, they tend to think the root cause is simple.
But often the bug is caused by two or more features interacting.
Reducing the config to a minimum to reproduce the bug helps discover exactly which config elements are required to interact to trigger the bug.

## Why we require a minimal reproduction

A debuggable reproduction repository is usually needed, and it makes the most sense for the issue reporter to create it.
We prefer that you use GitHub to host your reproduction, but if it requires GitLab or Bitbucket to be reproduced then creating a public repository on those instead is fine.

### "Making a reproduction repository is too much work for me"

Although we'd love to get down to zero reported bugs or feature requests remaining, there's a queue and we need to prioritize.
If a bug or feature is not important enough for you to spend your time creating a simple repository for, that's a strong indicator to the Renovate team that it should be treated as a lower priority than those issues which do have a reproduction repository.

Therefore you are free to raise bug reports or feature requests without a reproduction repository but be prepared for it to not be fixed until someone else with the same problem reproduces it, and for it to be closed unfixed if nobody else is able to do that.

### "I already described what you need in the issue itself"

If it's so simple then it shouldn't take you much time to commit it to a repo.

## How to create a good minimal reproduction

A good minimal reproduction:

- Uses the fewest number of repository files and dependencies possible
- Reduces the Renovate config to the minimum necessary
- Contains a `readme.md` file that explains current behavior and expected behavior

Sometimes you may find it easiest to start with a fork and then remove files/config until the bug no longer reproduces, but other times it may be simplest to start with an empty repository with a couple of files you copy over manually from your main repository.
