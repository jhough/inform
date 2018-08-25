---
layout: post
title:  "AWS Certification Preparation"
date:   2015-12-30
permalink: /writing/aws-certification-preparation/
categories:
published: true
comments: true
tags: [AWS]
---
Last week an associate who’s preparing for the Amazon Web Services Developer certification exam sent out a request to people in our company who work with AWS. He asked if any of us had obtained a certification and to share suggestions for preparing for it. The following is my email response (with titles, links, and script example added), including how to save $20 in preparation fees.

<figure>
    <img src="{{ site.baseurl }}/assets/shutterstock_123085243_plan_prepare_perform.jpg" alt="Plan, Prepare, Perform" height="267.2" width="400">
    <figcaption>YuryZap/Shutterstock</figcaption>
</figure>

<br>

`From: Jim Hough` <br>
`Date: Thursday, December 24, 2015 12:33 PM EST` <br>
`Subject: RE: AWS Group / Certification` <br>

Thomas,
 
I achieved the AWS Solutions Architect - Associate Level earlier this year. Here’s what I did:

# Classroom Training
I took the Architecting with AWS class given by Amazon. Personally expensive but an investment in my skills (and possibly tax deductable too). The class was excellent, very helpful to connect many dots. Plus a great networking opportunity.

[https://aws.amazon.com/training/course-descriptions/][course-descriptions]

[course-descriptions]: https://aws.amazon.com/training/course-descriptions/


# Hands-on Labs
In the class I learned about qwikLabs online hands-on learning company, which uses real AWS services. Also excellent. A set of instructions (which you keep) guides you through setting up a solution. They now have Exam Prep “Learning Quests” for both of the architect certifications. “A qwikLABS Learning Quest is a collection of Labs and learning materials that have been chosen to help you gain mastery of a specific topic.”

[https://qwiklabs.com/][qwiklabs]

[qwiklabs]: https://qwiklabs.com/

(It’s easy to dismiss now because you’ve just read their name twice and seen their URL, but don’t make the mistake I kept making by entering `quicklabs.com` into your web browser. You don't get a different company, which would be helpful. You get a 404 page.)


# Exam Scope
Pay attention to the scope of services that AWS specifies for the certification. Read the Exam Blueprint for the certification that you are interested in.

[https://aws.amazon.com/certification/][scope]

[scope]: https://aws.amazon.com/certification/



# Documentation
I read the AWS documentation for each of those services. **Of all the preparation methods this was the most important for me.** This is among the best documentation you will find for any computing/software anywhere. I made a list of each of the services I needed to know, I read through each, taking notes as I went. This is time consuming but it works for me and helped me connect more dots. I did the mini tutorials embedded within the documentation. I used each of the services a few times to better grasp how they work. I don’t think anyone can really get AWS until they use the services themselves. My notes served as a solid review aid.

[https://aws.amazon.com/documentation/][documentation]

[documentation]: https://aws.amazon.com/documentation/



# AWS Command Line Interface
In addition to the web console, try using the services via the AWS Command Line Interface (CLI). It's a unified tool to manage almost all the services. Writing a few BASH or PowerShell scripts gives you the ability to launch the service with specified options, examine and compare the results, and then kill it. You can change the options and repeat. For each service the [CLI Reference][cli-reference] (URL below) provides all the commands and options. Another way to connect the dots.

{% highlight bash%}
#!/bin/sh
# file: ec2_Ubuntu_Nginx_uWSGI_launch.sh
# Launch an EC2 Ubuntu instance and use the user-data option to bootstrap
# a Django application with Nginx and uWSGI.
# ami-d05e75b8: ubuntu-trusty-14.04-amd64-server-20150325, HVM, 64bit, EBS

aws ec2 run-instances \
    --no-dry-run \
    --image-id ami-d05e75b8 \
    --count 1 \
    --instance-type t2.nano \
    --key-name jimkey4 \
    --security-group-ids sg-e556bc9c \
    --subnet-id subnet-967cf6e1 \
    --associate-public-ip-address \
    --iam-instance-profile Arn=arn:aws:iam::999999999999:instance-profile/ec2-role \
    --monitoring Enabled=true \
    --user-data file://ec2_Ubuntu_Nginx_uWSGI_bootstrap.sh
{% endhighlight %}


[https://aws.amazon.com/documentation/cli/][cli-documentation]

[cli-documentation]: https://aws.amazon.com/documentation/cli/
[cli-reference]: http://docs.aws.amazon.com/cli/latest/reference/#available-services


# Videos, Slides, Audio Podcasts
The videos for most of the talks given at each year’s AWS developers conference held in October or November, called re:Invent, are available online. These are all in depth presentations about a given service or concept, many with demos. They're in high definition so you can see the code.
Some of the presenters put their slides on SlideShare. 
These same presentations are also available as audio podcasts. Even though they are without video, I've learned plenty listening to the podcasts traveling to and from work.

[https://www.youtube.com/user/AmazonWebServices][videos]

[videos]: https://www.youtube.com/user/AmazonWebServices


[http://www.slideshare.net/search/slideshow?searchfrom=header&q=AWS][slides]

[slides]: http://www.slideshare.net/search/slideshow?searchfrom=header&q=AWS


For your podcast player: [https://s3.amazonaws.com/reinvent-podcasts/AWS_reInvent2015_PodcastRSS.xml][podcasts]

[podcasts]: https://s3.amazonaws.com/reinvent-podcasts/AWS_reInvent2015_PodcastRSS.xml
(Or just search for "AWS" in your player.)



# Practice Questions
The exam questions are multiple-choice. For some questions you select one option, for other questions you select more than one option. See AWS’s own sample exam questions for an idea of the type of questions you will see. However they provide only five or ten questions.

[https://aws.amazon.com/certification/certification-prep/][questions]

[questions]: https://aws.amazon.com/certification/certification-prep/


I signed up for Cloud Academy for the month leading up to my exam. I used it after the bulk of my reading and notes. They have many AWS lessons and certification quizzes. This was more of a reinforcement and confidence builder for me rather than my primary way of learning. However it pushed me to learn a few more facts. One annoying thing. For their AWS Certified Solutions Architect - Associate prep they have practice quizzes with hundreds of questions, but about 20% of the questions were about AWS service limits. For example, `"What are the number of VPCs per region? Answer = 5."` (See [AWS Service Limits][service-limits] ). These type questions do not appear on the actual exam. The actual exam is about knowing how AWS services should be applied to solve various architectural issues. Service limit type are easy questions to create but were a waste of my time. Even so, Cloud Academy is worth at least a month.

[https://cloudacademy.com/aws-certifications-training/][cloudacademy]

[cloudacademy]: https://cloudacademy.com/aws-certifications-training/
 

Kryterion, the company that provides the test centers for the exam, also has online timed practice tests available. My test was about 15 - 20 questions, similar to the type of questions that were on the exam.
There's value in the test. But here’s a $20 savings tip: if you take the test again, they’re the same questions. That said, taking the practice test twice helped me. I failed the first practice test after having studied for a couple months. Which freaked me out. How difficult was this exam going to be?! This focused my study. I took the practice exam again a week later and passed. More study. I took the real exam two weeks after that and passed.

[https://webassessor.com/aws/][kryterion]

[kryterion]: https://webassessor.com/aws/


<br>
This wasn’t a quick process for me. But I learned a ton and thoroughly enjoyed it. All the best to you.
 
Jim

<img src="{{ site.baseurl }}/assets/Solutions-Architect-Associate.jpg" alt="AWS Logo" height="102" width="250">


[service-limits]:   http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html
