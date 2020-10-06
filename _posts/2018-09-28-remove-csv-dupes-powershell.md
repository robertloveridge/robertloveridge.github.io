---
layout: post
title:  "Remove Duplicates from a CSV with PowerShell"
date:   2018-09-28
categories: development
---

New job, new tools. In my new job, I've got a Windows machine and after using Linux and Mac OS for over 10 years, the last 2 weeks have been a bit of a learning curve but I have to say, I'm damn impressed with Windows.

Something I used to do a lot in my old job was remove duplicates from CSV files. Lets say I had a CSV file of people and wanted to produce a new and duplicate free version based on the "Age" column.

Here's how I could do that with the Awk Unix command and for comparison, some PowerShell 'cmdlet'.

## Input CSV - ages.csv

```
"Name","Age"
"Robert","20"
"Rob","23"
"Robbie","20"
"Ernie","24"
"Reg","39"
```

## Unix

```
[rob@server ~/Desktop]$ awk 'seen[$2]++{print $0 > "ages.csv"; next}{print $0 > "unique-ages.csv"}' ages.csv
```

## PowerShell

```
PS /Users/rob/Desktop> Import-Csv ./ages.csv | Sort-Object "Age" -Unique | Export-Csv -Path ./unique-ages.csv
```

## Output CSV - unique-ages.csv

```
"Name","Age"
"Robert","20"
"Rob","23"
"Ernie","24"
"Reg","39"
```