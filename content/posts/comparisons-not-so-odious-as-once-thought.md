---
title: "Comparisons: Not so Odious as Once Thought"
date: "2011-02-03T00:00:00+00:00"
author: "futureplatforms"
categories:
  - "General"
  
slug: "comparisons-not-so-odious-as-once-thought"
---

<section class="post_content clearfix" itemprop="articleBody">
<p>I often get asked if there is any published work evaluating performance and cost of scientific applications on IaaS clouds and comparing them to using clusters — and I always say LOTS! …and then can’t remember more than a few off the top of my head ;-). So I recently put together a list — included below — of various evaluation and comparison efforts I’ve been able to find. They  look all sorts of aspects of performance — from low-level benchmarks to applications of various types, from reliability to cost. They all tend to focus on somewhat different aspects of the issue and collectively paint a picture blessings and challenges of cloud computing for science.</p>
<p>My personal favorite is “Performance Analysis of High Performance Computing Applications on the Amazon Web Services Cloud Amazon Web Services Cloud” — on top of the list since, having just come out at CloudCom 2010 last December it is the most recent. The authors evaluate the <a href="http://aws.amazon.com/">AWS IaaS offering</a> based on the <a href="http://www.nersc.gov/">NERSC</a> benchmarks framework — a comprehensive set of benchmarks capturing the typical workload in a scientific datacenter. They report not only the performance characteristics of scientific applications on <a href="http://www.nimbusproject.org/files/VirtualClusters.pdf">virtual clusters</a> created in the cloud but also note the mean time between failures (MTBF) of a virtual cluster deployed on cloud resources — the consequences of which I (coincidentally) <a href="https://scienceclouds.org/blog/mohammad-and-the-mountain/">blogged about</a> around the time this paper was presented.</p>
<p>And finally, I have a favor to ask — if you know of papers evaluating various aspects of scientific applications on IaaS clouds or have favorites in the filed, or opinions on what you would like to see evaluated — please tell us about it. I will do a post of lessons learned.</p>
<p><strong>Evaluation of IaaS clouds for scientific applications:</strong></p>
<ul>
<li><a href="http://acs.lbl.gov/ACSDownloads/kjackson/papers/PID1512769.pdf">“Performance Analysis of High Performance Computing Applications on the Amazon Web Services Cloud Amazon Web Services Cloud”</a> by K. Jackson, L. Ramakrishnan, K. Muriki, S. Canon,  S. Cholia, J. Shalf, H. Wasserman and N. Wright,  CloudCom 2010</li>
<li><a href="http://www.csc.cs.colorado.edu/%7Ematthew/papers/201006-cit2010-cloudcharge-paper.pdf">“Developing a Cloud Computing Charging Model for High-Performance Computing Resources</a>“, M. Woitaszek and H. Tufo, CIT 2010</li>
<li><a href="http://dsl.cs.uchicago.edu/ScienceCloud2010/p07.pdf">“Seeking Supernovae in the Clouds: A Performance Study”</a>, K. Jackson, L. Ramakrishnan, R. Thomas and K. Runge, Science Cloud 2010</li>
<li><a href="http://bit.ly/cNRvWq">“The Impact of Virtualization on Network Performance of Amazon EC2 Data Center”</a>, G. Wang and T. E. Ng, INFOCOM 2010.</li>
<li>“Data Sharing Options for Scientific Workflows on Amazon EC2”, G. Juve, E. Deelman, K. Vahi and G. Mehta, SC 2010</li>
<li>“Scientific computing in the cloud”, J. Rehr, F. Vila, J. Gardner, L. Svec, and M. Prange, Computing in Science and Engineering, 2010.</li>
<li><a href="http://ix.cs.uoregon.edu/~raihan/HPC_with_Clouds_Raihan_Masud.pdf">“High Performance Computing with Clouds”</a>, R. Masud</li>
<li><a href="http://www.cs.utexas.edu/users/pauldj/pubs/uchpc09.pdf">“Can Cloud Computing Reach the TOP500?”</a>, Napper, J. and P. Bientinesi, Unconventional High-Performance Computing (UCHPC) 2009.</li>
<li><a href="http://ieeexplore.ieee.org/xpl/freeabs_all.jsp?arnumber=5289187&amp;tag=1&amp;abstractAccess=no&amp;userType=inst">“Using Clouds for Metagenomics”</a>, Wilkening, J.,  										  										  								    										 								  			Wilke, A.,  										  										  								    										 								 	 		Desai, N. and Meyer, F, CLUSTER 2009.</li>
<li><span><strong></strong></span><a href="http://www.nimbusproject.org/files/Hoffa-CloudComputing.pdf">“On the Use of Cloud Computing for Scientific Workflows”</a>, Hoffa, C., G. Mehta, T. Freeman, E. Deelman, K. Keahey, B. Berriman and J. Good., SWBES 2008</li>
<li><a href="http://www.st.ewi.tudelft.nl/~iosup/PDS-2008-006.pdf">“An early performance analysis of cloud computing services for scientific computing”</a>, S. Ostermann, A. Iosup, N. Yigitbasi, R. Prodan, T. Fahringer, and D. Epema,  Delft University of Technology, Tech. Rep, 2008.</li>
<li><a href="http://www.cs.wits.ac.za/~scott/papers/amazon.pdf">“Scientific computing using virtual high-performance computing: a case study using the Amazon elastic computing cloud”</a>, S. Hazelhurst, conference of the South African Institute of Computer Scientists and Information Technologists on IT research in developing countries, 2008</li>
<li><a href="http://www.csee.usf.edu/~anda/papers/AmazonS3_TR.pdf">“Amazon S3 for Science Grids: A Viable Solution?”</a>, Palankar, M., A. Onibokun, A. Iamnitchi, and M. Ripeanu, International Workshop on Data-Aware Distributed Computing, 2008.</li>
<li><a href="http://cca08.org/papers/Paper34-Chris-Hill.pdf">“Cloud  Computing for parallel Scientific HPC Applications: Feasibility of  running Coupled Atmosphere-Ocean Climate Models on Amazon’s EC2”</a>, C. Evangelinos and C. N. Hill, Cloud Computing and its Applications (CCA) Workshop, 2008</li>
<li><a href="http://www.usenix.org/publications/login/2008-10/openpdfs/walker.pdf">“Benchmarking Amazon EC2 for high-performance scientific computing”</a>, E. Walker, LOGIN: vol. 33, no. 5, 2008</li>
<li><a href="http://search.yahoo.com/r/_ylt=A0oG7lT.s0lNgKMA25RXNyoA;_ylu=X3oDMTE1cWVwcjU0BHNlYwNzcgRwb3MDMQRjb2xvA2FjMgR2dGlkA1NNRTAyMl8xNTc-/SIG=1287bpo58/EXP=1296704638/**http%3a//simson.net/clips/academic/2007.Harvard.S3.pdf">“An Evaluation of Amazon’s Grid Computing Services: EC2, S3 and SQS”</a>, S. Garfinkel, Technical Report TR-08-07, 2007</li>
</ul>
</section>
