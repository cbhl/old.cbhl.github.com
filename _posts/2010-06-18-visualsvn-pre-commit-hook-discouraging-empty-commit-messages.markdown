---
author: cbhl
date: '2010-06-18 18:30:43'
layout: post
slug: visualsvn-pre-commit-hook-discouraging-empty-commit-messages
status: publish
title: 'VisualSVN Pre-Commit Hook: Discouraging Empty Commit Messages'
wordpress_id: '74'
categories:
- Programming
---

While I'm waiting for someone to get around to configure Team Foundation
Server so that we can finally migrate from Visual SourceSafe, I decided
that I would set up VisualSVN Server on my personal machine for the
small projects that I'm working on. One of the things that bugs me is
how easy it is to accidentally make an empty commit message with
AnkhSVN, so I went around the internet and adapted scripts I found to
create the following pre-commit hook: [text]@echo off :: :: Stops
commits that have empty log messages. :: @echo off setlocal rem
Subversion sends through the path to the repository and transaction id
set REPOS=%1 set TXN=%2 set SVNLOOK="C:\\Program Files\\VisualSVN
Server\\bin\\svnlook.exe" REM Make sure that the log message contains
some text. FOR /F "usebackq delims==" %%g IN (\`%SVNLOOK% log -t %TXN%
%REPOS% FINDSTR /R /C:......\`) DO goto NORMAL\_EXIT :ERROR\_TOO\_SHORT
echo Your commit has been blocked because your log message was too 1\>&2
echo short. Please write a log message describing the purpose of your
1\>&2 echo changes and then try committing again. Thanks! 1\>&2 goto
ERROR\_EXIT :ERROR\_EXIT exit /b 1 REM All checks passed, so allow the
commit. :NORMAL\_EXIT exit 0[/text] Sources:
-   [http://www.anujgakhar.com/2008/02/14/how-to-force-comments-on-svn-commit/](http://www.anujgakhar.com/2008/02/14/how-to-force-comments-on-svn-commit/)
-   [http://stackoverflow.com/questions/247888/how-to-require-commit-messages-in-visualsvn-server](http://www.anujgakhar.com/2008/02/14/how-to-force-comments-on-svn-commit/)

Of course, a technical solution like this is useless if people like to
type commit messages like "." or "asdf". But if people working on the
code know what they're doing, little reminders like this can help
prevent accidents. :)
