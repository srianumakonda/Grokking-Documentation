Bloom filters + HyperLogLog
=====

The main problem is that **you want to go through a large list to figure out whether an element is in a large set.**

The fastest way to do this could be with a has; you have 2 columns: {website_name: checked_or_not}. So, if I wanted to check if I already saw ` srianumakonda.com<http://srianumakonda.com>`_, then I can just look it up in the hash.

Remember that the average lookup time is **O(1).** 

What's the problem though: **these hash tables are HUGE. It's a space problem.**

Bloom filters are essentially probabilistic data structures. Although false positives might be possible, false negatives are NOT.

The main benefit here is that Bloom filters take up **very little space to operate it at.** Tables have to store every single URL by Google while it's ok to be wrong in these scenarios.

**HyperLogLog is also quite similar.** You can approximate the number of unique elements in a set (ex. Amazon wants to count the # of unique elements that users looked at today) **with a fraction of the memory.**


