---
title: "Blog: Notary Project announces Notation v1.3.0 and tspclient-go v1.0.0!"
url: "https://notaryproject.dev/blog/2025/announcing-notation-v1-3/"
date: "Fri, 17 Jan 2025 00:00:00 +0000"
author: ""
feed_url: "https://notaryproject.dev/blog/index.xml"
---
<p>The Notary Project maintainers are thrilled to announce the latest releases, including <a href="https://github.com/notaryproject/notation/releases/tag/v1.3.0" rel="noopener" target="_blank">notation v1.3.0</a>, <a href="https://github.com/notaryproject/notation-go/releases/tag/v1.3.0" rel="noopener" target="_blank">notation-go v1.3.0</a>, <a href="https://github.com/notaryproject/notation-core-go/releases/tag/v1.2.0" rel="noopener" target="_blank">notation-core-go v1.2.0</a> and <a href="https://github.com/notaryproject/tspclient-go/releases/tag/v1.0.0" rel="noopener" target="_blank">tspclient-go v1.0.0</a>!</p>
<p>These new versions are production ready and have successfully completed a comprehensive <a href="https://www.cncf.io/blog/2025/01/21/notary-project-completes-its-second-audit/" rel="noopener" target="_blank">security audit</a>. Check out the <a href="https://github.com/notaryproject/specifications/tree/main/security/reports/audit/Quarkslab-notation-security-audit-25.pdf" rel="noopener" target="_blank">security audit report</a> for more details. Our commitment to providing secure and high-quality signing and verification tools for our users has never been stronger!</p>
<h2 id="notable-capabilities-in-these-releases">Notable Capabilities in these Releases</h2>
<p>Here are the major capabilities and features included in these releases.</p>
<h3 id="the-first-major-release-of-tspclient-go-library">The first major release of <code>tspclient-go</code> library</h3>
<p>Looking for a robust implementation of <a href="https://datatracker.ietf.org/doc/html/rfc3161" rel="noopener" target="_blank">RFC 3161</a> Timestamp Protocol Client in Go? The library <a href="https://github.com/notaryproject/tspclient-go" rel="noopener" target="_blank">tspclient-go</a> is the answer. Here is why:</p>
<ul>
<li><strong>RFC 3161 Compliance</strong>: Adheres to the specification RFC 3161 for timestamping clients. Supports timestamping with popular public TSAs like DigiCert and GlobalSign.</li>
<li><strong>Secure</strong>: Implements secure communication protocols, ensuring the integrity and authenticity of timestamps.</li>
<li><strong>Minimal Dependencies</strong>: Uses only standard Go libraries. Less dependencies, more secure.</li>
<li><strong>High Test Coverage</strong>: Boasts up to 95% test coverage.</li>
<li><strong>Security Audited</strong>: Passed a comprehensive security audit with no advisories, ensuring a high quality bar.</li>
<li><strong>Ease of Use</strong>: Seamlessly integrates into Go applications with a straightforward API.</li>
</ul>
<p>Notary Project&rsquo;s <a href="https://notaryproject.dev/docs/user-guides/how-to/timestamping/">timestamping feature</a> is built on this library.</p>
<h3 id="certificate-revocation-checking-using-certificate-revocation-list-crl">Certificate Revocation checking using Certificate Revocation List (CRL)</h3>
<p>Certificate revocation checking enhances security by ensuring that compromised or expired certificates are not used, thereby maintaining the integrity and trustworthiness of digital signatures. It also helps organizations comply with security standards and regulations. With this release, Notation implements the <a href="https://github.com/notaryproject/specifications/blob/v1.1.0/specs/trust-store-trust-policy.md#crls" rel="noopener" target="_blank">Notary Project CRL specification</a> with CRL cache support. Notation now supports two certificate revocation checking methods: Online Certificate Status Protocol (OCSP) and CRL. OCSP is preferred, but if unavailable, CRLs are used as a fallback. For more details on CRL cache directories, visit <a href="https://notaryproject.dev/docs/user-guides/how-to/directory-structure">this link</a>.</p>
<p>By default, Notary Project trust policies enforce revocation checking, so users do not need to configure it. For more details on fine-tuning revocation settings, visit <a href="https://github.com/notaryproject/specifications/blob/v1.1.0/specs/trust-store-trust-policy.md#trust-policy-properties" rel="noopener" target="_blank">this link</a>.</p>
<h2 id="get-started-with-notation-v130">Get started with Notation v1.3.0</h2>
<p>You can follow the <a href="https://notaryproject.dev/docs/quickstart-guides/quickstart-sign-image-artifact/">quick start guide</a> to try Notation v1.3.0 for basic signing and verification workflow.</p>
<h2 id="whats-next">What&rsquo;s next</h2>
<p>The Notary Project maintainers are considering the following features for future milestones. Feel free to reach out on the <a href="https://app.slack.com/client/T08PSQ7BQ/CQUH8U287/" rel="noopener" target="_blank">Slack channel</a> or <a href="https://github.com/notaryproject/notation/issues" rel="noopener" target="_blank">GitHub issues</a> to ask questions, provide feedback, or share ideas.</p>
<ul>
<li>Sign and verify arbitrary blobs</li>
<li>Attestations</li>
</ul>
<p>And more!</p>
<h2 id="acknowledgements">Acknowledgements</h2>
<p>The Notary Project release team wants to thank the entire Notary Project community for all the activity and engagement that has been vital for helping the project grow and reach this milestone.</p>
<p>We are especially grateful to the CNCF for funding the security audit, the OSTIF for arranging it, and Quarkslab for conducting and releasing the audit report.</p>
