---
title: "There is a New Supercomputer on the Block"
date: 2010-07-13
author: "futureplatforms"
categories:
  - "News"
  
slug: "there-is-a-new-supercomputer-on-the-block"
---

<section class="post_content clearfix" itemprop="articleBody">
<p>We all woke up to a <a href="http://www.allthingsdistributed.com/2010/07/cluster_compute_instance_amazon_ec2.html">game-changing announcement</a> today: Amazon announced Cluster Compute instances designed to support the kinds of closely coupled workloads that high performance computing (HPC) relies on. The Cluster Compute instances consist of a pair of quad-core Intel “Nehalem” processors with 23 GB of RAM, and 1690 GB of local instance storage. But by far the best part of the offering is the 10 Gbps network that connects Cluster Compute instances — essential for HPC applications.</p>
<p>The real headline though is that for the first time ever a virtual cluster could be featured on the <a href="http://www.top500.org/">Top500</a> list. Amazon published the result of the High Performance Linpack benchmark on a virtual cluster made up of 880 Cluster Compute instances (7040 cores) and measured the overall performance at 41.82 TeraFLOPS. This would place a virtual cluster made out of Cluster Compute instances in the 146th position on the Top500 list. For a sense of scale, the somewhat larger in size <a href="http://services.tacc.utexas.edu/index.php/lonestar-user-guide">TACC Lonestar cluster</a>, serving as computational resource in <a href="https://www.teragrid.org/">TeraGrid</a>, currently occupies the 123th position on this list.</p>
<p>How much does it all cost? A quick back-of-the-envelope calculation shows that at $1.60 per hour, the Cluster Compute on-demand instances cost about $14K per node per year. However, if you use reserved instances the price drops significantly. Based on 100% utilization for a 3 year reserved instance (which is more similar to buying a supercomputer for 3 years) you’d pay only $0.81 per instance ($6590 up front and $0.56 per hour), in other words, $7K per node per year – but that’s all-inclusive, no additional operating costs. This rough calculation does not include the cost of EBS and data transfer which to some extent depend on the use of the cluster — still, something to keep in mind.</p>
</section>
