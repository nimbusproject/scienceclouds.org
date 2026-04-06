---
title: "LANTorrent in Action on FutureGrid"
date: 2013-05-09
author: "andersonj"
categories:
  - "Solutions"
  
slug: "lantorrent-in-action-on-futuregrid"
---

<section class="post_content clearfix" itemprop="articleBody">
<p>We just reduced image propagation time on <a href="https://portal.futuregrid.org">FutureGrid</a>’s <a href="https://portal.futuregrid.org/manual/sierra">Sierra cloud</a> at UCSD from hours to minutes! This magic comes courtesy of Nimbus LANTorrent.</p>
<p>We blogged about LANTorrent <a href="http://scienceclouds.org/blog/get-there-faster-with-nimbus-2-6">before</a>: it can distribute the same file among many nodes using peer-to-peer techniques. It is available in <a href="http://www.nimbusproject.org/news/#235">Nimbus since version 2.6</a> and allows users to efficiently deploy a cluster of virtual machines based on the same image. Installing and configuring LANTorrent on the Nimbus nodes (both service and hypervisor nodes) is easy; it took only a couple of hours on Sierra (all the details are explained in the <a href="http://www.nimbusproject.org/docs/current/admin/reference.html#lantorrent-config">LANTorrent Configuration section of the Nimbus documentation</a>).</p>
<p>Granted, Sierra’s configuration helped make this spectacular. Sierra is backed by an NFS server connected via Gigabit Ethernet to the cluster. To transfer virtual machines to a hypervisor node, a copy of the virtual machine image is made using scp. While copying a single virtual machine image can be done in less than one minute, deployment of large virtual clusters takes much more time because all file transfers originate from the centralized NFS server. With LANTorrent however, it is dramatically faster! Instead of forcing 100 copies of the same files through the NFS server’s single NIC, LANTorrent uses the collecting power of every receiving nodes’ NIC to transmit the data, bringing us approximately a 3x speedup! I made a graph that compares deployment time of a 4 GB virtual machine image (SCP in red, LANTorrent in blue). Faster is not all – the growth rate is where we really reap the benefits!</p>
<a href="/resources/LANTorrent-new-results.png"><img alt="LANTorrent performance on Sierra" class="alignleft size-full wp-image-1024" decoding="async" fetchpriority="high" height="463" sizes="(max-width: 757px) 100vw, 757px" src="/resources/LANTorrent-new-results.png" width="757"/></a>
</section>
