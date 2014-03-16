---
layout: post
title: uploading local project to GitHub
categories: [git test]
---


If you have been working on a project and now want to upload it to a new GitHub-repository, you have to do the following:

1. create a new repo at GitHub: GitHub provides you with the ssh-address
1. go into your project directory ```cd <project>```
2. If you want a readme-file ```touch README.md```
3. initialize your repository ```git init```
4. add your working files ```git add README.md``` and all you want in your repo
1. if you have empty directories and want them to show up in the repo, put a file in there: ```touch src/main/java/.gitkeep```
5. commit ```git commit -m "project xyz ..."```
6. add a remote ```git remote add origin git@github.com:<username>```
7. push it up ```git push -u origin master```

and you are ready!




