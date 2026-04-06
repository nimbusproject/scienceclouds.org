---
title: "EC2’s boot from EBS capability"
date: "2009-12-04"
author: "futureplatforms"
categories:
  - "News"
  
slug: "ec2s-boot-from-ebs-capability"
---

<section class="post_content clearfix" itemprop="articleBody">
<p>Amazon AWS recently <a href="http://aws.amazon.com/about-aws/whats-new/2009/12/03/amazon-ec2-instances-now-can-boot-from-amazon-ebs/">announced</a> that EC2 instances can be configured to launch from <a href="http://aws.amazon.com/ebs/">EBS</a> volumes instead of bundled disk images.</p>
<p>Science users launching heterogeneous clusters can possibly take advantage of this in order to streamline the bundling of images.  Those clusters often share a base image layout.  Because these AMIs can now reference any number of EBS volumes in their external description including for the root disk, you can now work on customizing each partition and “mix and match” root disks and partitions more easily to make a cohesive cluster.  That’s more convenient than maintaining such a partition organization separately and bundling images for each cluster node type, which is traditionally time consuming.</p>
<p>Another change is that the AMI can be above 10GB (up to 1TB) when launched in this manner: some clusters we have seen are pushing that limit even without any data sets!</p>
<p>There is an added cost involved in using EBS which must be taken into account.  And EBS is charged by both disk size and number of I/O operations, so this may not be useful in a lot of cases.</p>
</section>
