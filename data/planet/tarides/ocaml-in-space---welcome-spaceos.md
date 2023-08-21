---
title: OCaml in Space - Welcome SpaceOS!
description: "Our mission is to build sustainable and secure software infrastructure
  that will not only work for decades but also positively impact the\u2026"
url: https://tarides.com/blog/2023-07-31-ocaml-in-space-welcome-spaceos
date: 2023-07-31T00:00:00-00:00
preview_image: https://tarides.com/static/2e322321de9ea2c4156fe87fad92711b/0132d/Space-satellite.jpg
featured:
authors:
- Tarides
source:
---

<p>Our mission is to build sustainable and secure software infrastructure that will not only work for decades but also positively impact the world. This includes our work on essential open-source libraries and tooling in the OCaml space, but also extends to include cutting-edge innovation through MirageOS technologies. We are investigating mission-critical IoT use cases: one of which is facilitating the deployment of secure high-performance applications in space to help data scientists write models that run on satellite-generated data. In this post, we present our solution that does just that: SpaceOS.</p>
<p>The satellite industry is transforming! As a result, an exciting commercial space industry is emerging &ndash; one that industry professionals are increasingly referring to as &lsquo;NewSpace&rsquo;.</p>
<h2 style="position:relative;"><a href="https://tarides.com/feed.xml#the-newspace-opportunity" aria-label="the newspace opportunity permalink" class="anchor before"><svg aria-hidden="true" focusable="false" height="16" version="1.1" viewbox="0 0 16 16" width="16"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>The NewSpace Opportunity</h2>
<p>For those unfamiliar with NewSpace, here is a brief overview. Historically, satellites have been owned and operated by large and powerful companies that could afford the costs inherent in their design, launch, and operation. In addition to their high cost of production, this generation of satellites rarely changes their software/hardware configuration to avoid operational risk, and consequently operates in the same way a decade after its launch.</p>
<p>The high cost and lack of software flexibility have made it difficult for smaller companies to enter the market, disincentivising the development of technologies that require the capabilities of satellites. A timely and broad example with many use cases is earth observation, including monitoring volcanic activity, forest fires, agriculture, and oil spill detection.</p>
<p>Fast forward to today. New technologies &ndash; resulting in smaller satellites and significant reductions in launch costs &ndash; as well as new business models such as shared satellites and satellites as a service, now make it possible for many smaller companies to benefit from satellite capabilities. <a href="https://ourworldindata.org/grapher/yearly-number-of-objects-launched-into-outer-space">More satellites have been launched into space in the last two years than the fifty years before</a>. Welcome to NewSpace, where multi-user and multi-mission satellites are becoming the norm!</p>
<h2 style="position:relative;"><a href="https://tarides.com/feed.xml#newspace-needs-new-software" aria-label="newspace needs new software permalink" class="anchor before"><svg aria-hidden="true" focusable="false" height="16" version="1.1" viewbox="0 0 16 16" width="16"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>NewSpace Needs New Software</h2>
<p>NewSpace requires new software capabilities. The traditional and outdated practice of launching satellites and leaving them untouched for 15-20 years is no longer effective.</p>
<p>NewSpace requires the ability to run software from multiple users on the same satellites whilst maintaining software isolation (between applications and data of different users), as well as complete separation from the flight system software. Software must also be easy to update to allow for software innovation (for instance, to use a new machine learning inference algorithm) or to enable the new concept of usage-based models (where users pay for time spent or resources used). Existing platforms are not able to satisfy these new software requirements.</p>
<p>Many satellite operators either develop their own custom software stack (including their own operating system) or use complex Cloud-native software, such as Docker and Kubernetes, to manage multi-user and multi-mission needs. Cloud-native technologies are suboptimal in this context and, in particular, are inefficient for resource-constrained onboard satellite computing systems. There is a need for an alternative solution that is secure, efficient and easy to use.</p>
<h3 style="position:relative;"><a href="https://tarides.com/feed.xml#welcome-to-spaceos" aria-label="welcome to spaceos permalink" class="anchor before"><svg aria-hidden="true" focusable="false" height="16" version="1.1" viewbox="0 0 16 16" width="16"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Welcome to SpaceOS!</h3>
<p>SpaceOS is an operating system that is secure by design, providing complete isolation between user software paired with effortless software updates.</p>
<p>Multipurpose: Currently, there is no standard OS for satellites. Launching your software on a satellite platform requires you to write your own software based on different satellite and satellite service provider specifications. SpaceOS ensures compatibility across multiple satellites and service providers, ensuring you only need to write your software once.</p>
<p>Flexible: With SpaceOS, software updates are easy. Users can choose from powerful containerisation options, or opt to run on bare metal.</p>
<p>Compact: SpaceOS is small. A recent demonstration showcased that for an earth observation application, SpaceOS was 20 times smaller when compared to the classic Kubernetes approach, also requiring less memory and processing power.</p>
<p>Secure: SpaceOS is built on stable and safe programming logic (read on for details about the memory safety of OCaml) and <a href="https://mirage.io">MirageOS</a> <a href="https://queue.acm.org/detail.cfm?id=2566628">unikernel technology</a>. The MirageOS <a href="https://hannes.nqsb.io/Posts/Pinata">Bitcoin Pinata</a> is an example of a very successful, efficient, and transparent bug bounty program. Over 3 years the pinata was exposed to 150,000 hack attacks without success. Since MirageOS-style unikernels also power the SpaceOS solution, this test is a good indication of its cybersecurity strength.</p>
<h2 style="position:relative;"><a href="https://tarides.com/feed.xml#how-is-this-huge-leap-in-os-technology-possible" aria-label="how is this huge leap in os technology possible permalink" class="anchor before"><svg aria-hidden="true" focusable="false" height="16" version="1.1" viewbox="0 0 16 16" width="16"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>How is This Huge Leap in OS Technology Possible?</h2>
<p>Adapting to rapid development in any field often necessitates a paradigm shift. The order-of-magnitude improvements that SpaceOS provides over existing alternatives are only made possible due to fundamental changes in the underlying technology.</p>
<p>How can a software platform provide the powerful OS environment required for NewSpace?
To explain, one must understand what unikernels are and how the design of a programming language directly impacts its cybersecurity vulnerability.</p>
<h3 style="position:relative;"><a href="https://tarides.com/feed.xml#unikernels-a-shift-in-os-philosophy" aria-label="unikernels a shift in os philosophy permalink" class="anchor before"><svg aria-hidden="true" focusable="false" height="16" version="1.1" viewbox="0 0 16 16" width="16"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Unikernels: A Shift in OS Philosophy</h3>
<p>Let us talk about how operating systems generally work. Most operating systems have been built with the aim of running on lots of different kinds of hardware, and supporting lots of different kinds of applications (many of which don&rsquo;t exist yet when the OS is released and installed). This means that the operating system (such as Windows, Linux, macOS etc.) is optimised for broad compatibility, and is designed and built to provide a compelling platform for any application the user might need. This could include printer drivers, Bluetooth protocols, graphics card support, file system management, a range of network protocols, or user-space components such as <code>systemd</code>, ssh, logging systems&hellip; the list goes on.</p>
<p>In theory, the standard OS can theoretically service any number of applications. In practice, support for a wide range of applications that only &ldquo;might&rdquo; be used commonly leads to a large, resource-intensive OS vulnerable to cyber attack. Typically, any one application only requires a subset of the complete OS, and all of that extra functionality results in wasted resources and increased risk.</p>
<p>SpaceOS uses a different approach based on unikernel technology, and instead of being a general-purpose OS for any application, it is specialised for one unique application. In the build phase, SpaceOS analyses the application to determine the requirements for runtime. For example, if the application doesn&rsquo;t require Bluetooth or a sound driver, these functionalities will not be included in the OS. The OS creates a highly specialised, efficient, and compact executable with a significantly smaller attack surface, specifically designed for its single use case.</p>
<p>This kind of unikernel technology is not yet widely used commercially, but recent examples of mission-critical applications include the <a href="https://galois.com/project/cyberchaff/">CyberChaff</a> joint project between the US Department of Defense (DOD) and <a href="https://galois.com/">Galois</a>, and the <a href="https://www.nitrokey.com/products/nethsm">NetHSM security module</a> from Tarides partners, <a href="https://www.nitrokey.com/">Nitrokey</a>.</p>
<h3 style="position:relative;"><a href="https://tarides.com/feed.xml#ocaml-memory-safety-by-design" aria-label="ocaml memory safety by design permalink" class="anchor before"><svg aria-hidden="true" focusable="false" height="16" version="1.1" viewbox="0 0 16 16" width="16"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>OCaml: Memory Safety by Design</h3>
<p>SpaceOS has a second &ldquo;secret&rdquo; to add to the mix: it uses a memory-safe programming language called <a href="https://tarides.com/blog/2022-11-22-six-surprising-reasons-the-ocaml-programming-language-is-good-for-business/">OCaml</a>. The Cybersecurity and Infrastructure Security Agency (CISA) published <a href="https://www.cisa.gov/sites/default/files/2023-04/principles_approaches_for_security-by-design-default_508_0.pdf">a report emphasising the importance of Secure-By-Design principles as mitigation against cyber intrusions</a>. Some widely used languages (such as C or C++) are not memory safe and, therefore, vulnerable by design. With memory-related attacks being the most common cyber attack, forming <a href="https://www.itpro.com/security/zero-day-exploit/360447/why-zero-day-exploits-are-surging-on-an-unprecedented-scale">70% of all zero-day attacks</a>, the <a href="https://www.nsa.gov/Press-Room/News-Highlights/Article/Article/3215760/nsa-releases-guidance-on-how-to-protect-against-software-memory-safety-issues/">NSA (USA National Security Agency) also recommends using memory-safe languages</a>.</p>
<p>This is why we have chosen OCaml for SpaceOS. OCaml is purposefully designed and developed with safety and performance in mind, and therefore we can confidently say that SpaceOS is &ldquo;secure by design&rdquo;.
<a href="https://tarides.com/blog/2023-07-05-zero-day-attacks-what-are-they-and-can-a-language-like-ocaml-protect-you/">Read more about how OCaml can protect you against zero-day attacks</a>.</p>
<h2 style="position:relative;"><a href="https://tarides.com/feed.xml#conclusion" aria-label="conclusion permalink" class="anchor before"><svg aria-hidden="true" focusable="false" height="16" version="1.1" viewbox="0 0 16 16" width="16"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Conclusion</h2>
<p>SpaceOS and the underlying &ldquo;secure by design&rdquo; unikernel technology is a powerful and innovative new technology for in-space IoT and edge computing (with many other potential applications for mission-critical IoT use cases). By combining the performance and safety of OCaml with the specialisation and flexibility of unikernels, we aim to revolutionise the capabilities of NewSpace.</p>
<p>No other alternative offers similar capabilities today, which explains the very strong interest and many partnership discussions we are having with companies and organisations including such as <a href="https://www.thalesgroup.com/en/global/activities/space">Thales TAS</a>, <a href="https://www.esa.int/">ESA</a>,  <a href="https://cnes.fr/en">CNES</a>, <a href="https://infiniteorbits.io/">Infinite Orbits</a>, <a href="https://www.space.org.sg/">Singapore Space Agency</a>, <a href="https://www.ohb-hellas.gr/">OHB</a>, <a href="https://www.eutelsat.com/en/home.html">Eutelsat</a>, <a href="https://www.dorbit.space/">D-Orbit</a>, and more.</p>
<p>Stay tuned to hear how SpaceOS will become the new global standard for NewSpace satellites and <a href="https://tarides.com/company/">get in touch</a> if you have any questions.</p>