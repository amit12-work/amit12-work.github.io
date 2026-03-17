---
title: "2026-02-15-ibmi-git-integration"
date: 2016-02-15T15:34:30-04:00
categories:
  - blog
tags:
  - Jekyll
  - update
---

🚀 Git on IBM i – Small Step, Real Modernisation

I never thought I needed anything beyond the History Utility on the AS/400 for version control.

But with all the talk around modernisation and AI, I asked myself:

What practical improvement can we make on IBM i that truly helps the team?

So, I explored Git on IBM i.

My first attempts — connecting AS/400 to GitHub and using IBM Rational Developer for i plugins — didn’t work due to technical and permission limitations.

The breakthrough?

Creating a repository directly in the IFS on IBM i — no third-party dependency.

⸻

✅ What I Implemented

• Installed Git on IBM i
• Created repositories in the IFS
• Converted PDM source members to stream files
• Added them to Git
• Used git log and git checkout for version control

Some steps are still manual — automation coming soon.

```ruby
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
```
⸻

🔄 What’s Next?

Now that Git is working on IBM i, the real journey begins:

• Automating source conversion from PDM to IFS
• Defining a standard branching strategy
• Connecting to external Git platforms (when permissions allow)
• Driving team adoption

⸻

Modernisation doesn’t always start with AI.

Sometimes it starts with better version control — and the willingness to experiment.

Success came after a few failures — and that’s the best part of the journey.

<!-- Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/ -->
