---
title: "Science Cloud 2011"
date: 2011-06-10
author: "futureplatforms"
categories:
  - "General"
slug: "science-cloud-2011"
---

<section class="post_content clearfix" itemprop="articleBody">
<p>I had the privilege of presenting <a href="http://www.cs.iit.edu/~iraicu/ScienceCloud2011/p04.pdf" title="Cumulus: Open Source Storage Cloud for  Science">Cumulus: Open Source Storage Cloud for  Science</a> at the Science Cloud 2011 workshop yesterday.  While I was focused on our open source S3 implementation ideal for the extensibility and scientific experimentation, many other interesting topics were presented. Shane Canon present a very interesting look at common misconceptions about the cloud in scientific circles.  In it he exposed some truths about what ‘on demand’ ultimately means to a data center.  He worked to illustrate where on the hype curve the cloud currently is, and what features work for science and what was missing.  Elasticity for bursty applications is a clear win but a sighted glaring gap is the lack of a shared file system.  A shared file system is an assumed service to most scientific users coming from the grid and most other HPC platforms.  This need for a shared file system struck a chord with me and it seemed to be a common theme at the workshop.  Lavanya Ramakrishnan gave a talk on <a href="http://www.cs.iit.edu/~iraicu/ScienceCloud2011/p07.pdf" title="Magellan: Experiences from a Science Cloud">Magellan: Experiences from a Science Cloud</a>.  In it she mentioned the struggles scientific users had with their applications inside of VMs.  One was the difficulty staging in data into the VM’s space.  A couple of other talks discussed the huge volumes of data created by scientific applications. All of this discussion made me wonder if a Cloud agnostic shared file system service could be created and if such a thing could solve these problems.</p>
<p>The full program is available <a href="http://www.cs.iit.edu/~iraicu/ScienceCloud2011/" title="here.">here</a>.</p>
</section>
