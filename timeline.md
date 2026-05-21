Here is what I know so far 

```powershell
Get-Date -Format "yyyy-MM-dd-HH-mm-ss"

# Create the file with the new headers
"CommitHash,ParentHashes,Timestamp,Subject" > "D:\kus\diary\assets\archived\2026-05-21\commits.csv"

Get-Date -Format "yyyy-MM-dd-HH-mm-ss"

# Append the expanded git log data
git log --all --pretty=format:'"%H","%P","%cI","%s"' >> "D:\kus\diary\assets\archived\2026-05-21\commits.csv"

Get-Date -Format "yyyy-MM-dd-HH-mm-ss"

```

and the result was this

```csv
CommitHash,ParentHashes,Timestamp,Subject
"b0c09bf37529a03deb416a1cb72c60ac37e33030","9ffab94c88361e898cab781ddc0c5a870851986d","2026-05-21T13:18:23-04:00","add timestamp 2026-05-21-13-16-30 (#4)"
"a4925fdfdec1a6606d83f680d967380b0453380f","9ffab94c88361e898cab781ddc0c5a870851986d","2026-05-21T13:17:39-04:00","add timestamp 2026-05-21-13-16-30"
"1cea263f3f80b1a276734f5ac804fb6c5652d1a3","9fa34333f7ee3e59a16ac364b09a3ec05779449d","2026-05-21T13:15:16-04:00","add timestamp 2026-05-21-13-12-43 (#2) (#3)"
"9ffab94c88361e898cab781ddc0c5a870851986d","9fa34333f7ee3e59a16ac364b09a3ec05779449d","2026-05-21T13:14:11-04:00","add timestamp 2026-05-21-13-12-43 (#2)"
"bda9a56215354ebb55c6f71cb71e81b9a1a089b2","9fa34333f7ee3e59a16ac364b09a3ec05779449d","2026-05-21T13:13:27-04:00","add timestamp 2026-05-21-13-12-43"
"4add2d74481540a7a596006f15c3594a2d43ce58","9fa34333f7ee3e59a16ac364b09a3ec05779449d","2026-04-04T10:05:11-04:00","rename in branch 2"
"2c1c29d7589bf907e2ba632a6e10683fa089fe58","9fa34333f7ee3e59a16ac364b09a3ec05779449d","2026-04-04T10:04:38-04:00","change in branch 1"
"9fa34333f7ee3e59a16ac364b09a3ec05779449d","","2026-04-04T10:03:42-04:00","add initial commit"
```

what I did today: 

1. I started with the main branch
1. I created a new development branch 
1. I created a new release-1 branch 
1. I created a new feat/kushal/{timestamp} branch
1. I used the github ui to squash and merge this feat branch into release-1
1. I used the github ui to squash and merge this release-1 branch into development branch 
1. I then got the latest of release-1 branch onto my local. 
1. I created a new feat/kushal/{timestamp} branch
1. I used the github ui to squash and merge this feat branch into release-1
1. Now when I tried to merge this release-1 branch into development branch, I see two commits -- 
    one for my new commit, and one for the old commit that is already merged 

why? 
