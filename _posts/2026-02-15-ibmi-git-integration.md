---
title: "IBMi-git-integration"
date: 2026-02-15T15:34:30-04:00
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
```ruby
  $                      
> git version            
  git version 2.47.0     
  $                      
```
• Created repositories on the IFS
```ruby
  $                      
> git init --bare my_project.git     
  $                      
```
• Converted PDM source members to stream files
```ruby
  CPYTOSTMF FROMMBR('/QSYS.LIB/MYLIB.LIB/MYFILE.FILE/MYRPG.MBR') 
  TOSTMF('/home/MYDIR/MYSRC/MYRPG.sqlrpgle')            
  STMFOPT(*REPLACE)                                             
  STMFCCSID(1208)
```
• Added them to Git
```ruby
  git add .
```
• Used git log and git checkout for version control
```ruby
  git log --oneline
    [33mdfc16ce [m [33m ( [m [1;36mHEAD [m [33m ->  [m [1;32mmaster [m [33m,  [m [1;31morigin/master [m [33m) [m Auto-update:MYRPG01-
    11-03-26 / 16:49:55 [m                                                                                                           
    [33ma0cfa20 [m Auto-update:MYRPG01-11-03-26 / 16:41:49 [m                                                                        
    [33m2ecaa0a [m Auto-update:MYRPG01-11-03-26 / 16:24:40 [m                                                                        
    [33m7871192 [m OPR026- [m                                                                                                       
    [33mb3a09fc [m OPR025- [m                                                                                                       
    [33m2de0447 [m Auto-update:MYRPG02-11-03-26 / 14:36:48 [m                                                                        
    [33m00be3b0 [m Auto-update:MYRPG03-20260310223024326226 [m                                                                       
    [33m28c4522 [m Auto-update:MYRPG03-20260310222721877714 [m                                                                       
    [33me7a9146 [m Auto-update:MYRPG03 [m                                                                                            
    [33mf053c0e [m Auto-update:MYRPG03 [m                                                                                            
    [K [?1l >$                                                                                                                      
```

PDM user option can be used to automate the process.

⸻

Success came after a few failures — and that’s the best part of the journey.


<!-- Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/ -->
