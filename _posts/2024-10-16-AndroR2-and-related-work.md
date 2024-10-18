## AndroR2 and Related Work

In college, I was a part of a research group formed by Dr. Mattia Fazzini, which focused on the intersection of software engineering and machine learning. I was Dr. Fazzini's first undergraduate student, and I worked with him throughout my Master's Degree.

The theme of a lot of my work is reproducible bugs and reporting of these bugs. At the time, there was a lot of interest in the intersection of Natural Language Processing and .. everything (this is still the case, though chatGPT + LLMs have swallowed up much of this field since I graduated). Our work's focus was - it's really annoying and tedious to deal with bugs in software -- people don't like reporting bugs, they don't like reporting bugs *correctly* (i.e., accurately detailing each step to reproduce), developers don't like having to sift through github issues with missing steps to reproduce, etc etc. Can we find ways to cut down on that effort?

I'm sorry to say I didn't solve this problem with a silver bullet. But I did do some pretty cool stuff related to this question, and I'm happy to report that the work I have done on this has gone on to be used for some other pretty cool stuff.

Of primary interest is AndroR2, the database of github issues for mobile apps that contain steps to reproduce. While the final product itself is just a database, this was a pretty extensive project that took lot of moving pieces to actually finish. I built a github search API that crawled open-source android projects, found issues with steps to reproduce, and then manually reproduced them and confirmed that they were reproducible. It was a lot of manual (and automated) effort, and I'm happy to see that it's been cited a bunch.

You can find the repository of the APKs with bugs, alongside their steps to reproduce, here: https://github.com/SageSELab/AndroR2/tree/main/

Of interest is the web crawler that I built to page through github and find Android bugs. It's a pretty simple script, uses Python to call github api (it uses github search, and filters by the day, so that it never gets more than x results and hits the query limit). Github issues are stored as JSON in a mongoDB database (I just used the mongo UI + localhost, nothing fancy). It's a little bit jerry-rigged (I was coding it during covid! give me a break!) But i promise at one point it worked. Feel free to shoot me an email or something if it doesn't work and you want to take a crack at it.
