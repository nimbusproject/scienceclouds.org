---
title: "Grids versus Clouds"
date: 2009-12-19
author: "futureplatforms"
categories:
  - "General"
  
slug: "grids-versus-clouds"
---

<section class="post_content clearfix" itemprop="articleBody">
<p>The issue of how exactly cloud computing differs from grid computing was responsible for much controversy in the last year. Here are my two cents on how Infrastructure-as-a-Service (IaaS) cloud computing and grid computing are different (also discussed in the <a href="http://www.nimbusproject.org/files/Sky_Computing.pdf">Sky Computing paper</a>)</p>
<p>At some level, both cloud computing and grid computing represent the idea of using remote resources. However, grid computing is built on the assumption that control over the manner in which resources are used stays with the site, reflecting local software and policy choices. These choices are not always useful to remote users who might need a different operating system, or login access instead of a batch scheduler interface to a site. Reconciling those choices between multiple groups of users proved to be complex, time-consuming, and expensive. Looking back, leaving complete control over the resources with the site was a pragmatic choice that enabled very fast adoption of a radically transformative technology. On the other hand, once the technology became successful, this factor made it difficult for it to scale to many user groups with different (and sometimes conflicting) requirements of what the resource should provide. </p>
<p>IaaS cloud computing represents a fundamental change of assumption: when a remote user “leases” a resource, the control of that resource is turned over to that user. This change in assumption was enabled by the availability of a free and efficient virtualization technology: the <a href="http://www.xen.org">Xen hypervisor</a>. Before virtualization, turning over the control to the user was fraught with danger: the user could easily subvert a site. But virtualization provides a way of isolating the leased resource from a site in a secure way that mitigates this danger. Virtual machines can be deployed very fast (on the order of miliseconds) – when in addition to that the overhead and the price associated with a reliable virtualization technology went down, it suddenly became viable and cost-effective to use them in order to lease resources to remote users. </p>
<p>The ability to turn the control of remote resource over to the user makes it possible to develop tools, such as <a href="http://www.nimbusproject.org">Nimbus</a>, and provide services such as <a href="http://www.amazon.com/ec2">Amazon’s EC2</a> or <a href="http://www.scienceclouds.org">Science Clouds</a>  that allow users to carve out their own custom “site” out of remote resources. At the same time, this change of assumption challenges the established notions of what it means to be a site as we continue to struggle with the new meaning and implications of domain names, site licenses, and established security practices. </p>
</section>
