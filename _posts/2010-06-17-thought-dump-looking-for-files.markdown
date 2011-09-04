---
author: cbhl
date: '2010-06-17 00:23:35'
layout: post
slug: thought-dump-looking-for-files
status: publish
title: 'Thought Dump: Looking for files...'
wordpress_id: '60'
categories:
- Thought Dump
---

[bash]find -iname '\*.jpg' | xargs -L 1 -d '\\n' dirname | sort | uniq;
find -iname '\*.wmv' -o -iname '\*.mov' -o -iname '\*.avi' -o -iname
'\*.mp4' -o -iname '\*.flv' -o -iname '\*.m4v' | xargs -L 1 -d '\\n'
dirname | sort | uniq; for dir in \~/Videos \~/Downloads/Videos
/stuff/anime; do for ext in 'wmv' 'mov' 'avi' 'mp4' 'flv' 'm4v'; do find
$dir -iname "\*.$ext" -exec bash -c 'HandBrakeCLI -i "{}" -o
"iPadVideoOutput/\`basename "{}" .'$ext'\`.m4v" -Z AppleTV' \\;; done;
done;[/bash] **Update:** Added support for highlighting; added example
directories since the *<placeholders\>* were being formatted wrong.
