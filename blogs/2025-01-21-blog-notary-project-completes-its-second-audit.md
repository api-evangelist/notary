---
title: "Blog: Notary Project Completes Its Second Audit!"
url: "https://notaryproject.dev/blog/2025/notary-project-completes-its-second-audit/"
date: "Tue, 21 Jan 2025 00:00:00 +0000"
author: ""
feed_url: "https://notaryproject.dev/blog/index.xml"
---
<blockquote>
<p>This blog post was original published on <a href="https://ostif.org/notaryproject-cryptography-audit-2025/" rel="noopener" target="_blank">OSTIF blog</a> by Helen Woeste, Communications Manager, the Open Source Technology Improvement Fund.</p>
</blockquote>
<p>OSTIF is proud to share the results of our second security audit of Notary Project. You can read the Audit Report <a href="https://github.com/notaryproject/specifications/blob/main/security/reports/audit/Quarkslab-notation-security-audit-25.pdf" rel="noopener" target="_blank">HERE</a>. Notary Project is “a set of specifications and tools intended to provide a cross-industry standard for securing software supply chains by using authentic container images and other OCI artifacts.” With the help of Quarkslab and the Cloud Native Computing Foundation (CNCF), this project continues to provide users with trusted software supply chain management.</p>
<h2 id="audit-process">Audit Process</h2>
<p>This audit of Notary Project was specifically scoped around two new cryptographic features.<br />
The audit team, Quarkslab, was chosen for their practical cryptography experience to work on this engagement.<br />
The audit report presents how Quarkslab installed and performed discovery of Notary Project tooling Notation, reviewed the code structure and quality, and analyzed the timestamping and certificate revocation.<br />
The audit team also created multiple figures to help illustrate Notation with examples of overall project functionality, flow of certificate chain verification, and a global overview of the CRL verification.</p>
<h2 id="audit-results">Audit Results</h2>
<ul>
<li>
<p><strong>11 findings with Security Impact and Recommended Fixes</strong></p>
<ul>
<li>1 Medium, 1 Low, 9 Informational</li>
<li>2 CVEs issued for audit findings:
<ul>
<li><strong>CVE-2024-56138</strong>: Notation-go timestamp signature generation lacks certificate revocation check.</li>
<li><strong>CVE-2024-51491</strong>: Notation-go process crash during CRL-based revocation check on OS using separate mount point for temp directory.</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Review and Recommendations for 2 New Cryptographic Features</strong></p>
<ul>
<li><strong>Timestamping Support</strong>
<ul>
<li>Time-Stamp Protocol Compliance</li>
<li>Time Stamp Analysis in Notation</li>
</ul>
</li>
<li><strong>Revocation Checking with Certificate Revocation List</strong>
<ul>
<li>Certificate Revocation List Compliance</li>
<li>CRL Analysis in Notation</li>
</ul>
</li>
</ul>
</li>
<li>
<p><strong>Future Security Work Recommendations</strong></p>
</li>
</ul>
<p>This was Notary Project’s third security audit and second audit in partnership with OSTIF.<br />
Practicing mature security practices, the three audits were all undertaken after implementation of new features with security impact.<br />
Notary Project’s efforts to provide secure code to users was observable to the audit team and is reflected by the reported findings and further recommendations for future security work.</p>
<p>Thank you to the individuals and groups that made this engagement possible:</p>
<ul>
<li>Notary Project maintainers and community, notably: Pritesh Bandi, Junjie Gao, Vani Rao, Shiwei Zhang, Yi Zha, Patrick Zheng, and Feynman Zhou</li>
<li>Quarkslab: Dahmun Goudarzi, Sébastien Rolland, and Ramtine Tofighi Shirazi</li>
<li>Cloud Native Computing Foundation (CNCF)</li>
</ul>
