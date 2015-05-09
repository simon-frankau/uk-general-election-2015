UK General Election 2015 results data
=====================================

This repo holds 2015 general election data in a form that should be
easy to process. I looked around for easily-processed data, but
couldn't find it, so I've scraped it off the BBC website instead.

I can make no guarantees about accuracy of the original data, or my
transformation of it. Sorry!

With that out the way...

Data format
-----------

All data is one-row-per-record, with '|' as field separator. Simple,
eh?

constituencies.txt
------------------

This is the primary key for all the constituencies, using the BBC's
coding scheme.

Id|Constituency name|Region

summary.txt
-----------

The short summary of what happened in each region. The messages are
pretty much as scraped from the BBC.

Id|Description of change|Winning party

data/*
------

There is one file per constituency, each named after the BBC Id.

Party long name|Party short name|Candidate name|Number of votes|Percentage of votes|Percentage change

The percentage change is since 2010, with new parties given a previous
percentage of zero.

Why don't the percentage changes add up to 0?
---------------------------------------------

I'm not entirely certain, but it looks like it's a combination of
rounding, and the fraction from parties who aren't standing again
going away (creating a net positive change for everyone else).
