---
title: "Blog: Announcing Notation v2.0.0-alpha.1 to enable signing and verification of any arbitrary blob files!"
url: "https://notaryproject.dev/blog/2025/announcing-notation-v2-0-alpha/"
date: "Tue, 18 Mar 2025 00:00:00 +0000"
author: ""
feed_url: "https://notaryproject.dev/blog/index.xml"
---
<p><img alt="blog cover" src="https://notaryproject.dev/v2.0-alpha.svg" /></p>
<p>We are thrilled to announce the release of <a href="https://github.com/notaryproject/notation/releases/tag/v2.0.0-alpha.1" rel="noopener" target="_blank">Notation v2.0.0-alpha.1</a>, marking a significant milestone in our commitment to enhancing artifact signing and verification. This alpha release also introduces several improvements designed to provide a more versatile and efficient experience for our users.</p>
<h2 id="key-highlights">Key Highlights</h2>
<h3 id="breaking-changes">Breaking Changes</h3>
<p>In <code>notation v1.x</code>, the <code>notation sign</code> command defaults to storing signatures using the <a href="https://github.com/opencontainers/distribution-spec/blob/v1.1.1/spec.md#referrers-tag-schema" rel="noopener" target="_blank">OCI referrers tag schema</a> for maximum compatibility. As of this release, the default behavior has changed to use the <a href="https://github.com/opencontainers/distribution-spec/blob/v1.1.1/spec.md#listing-referrers" rel="noopener" target="_blank">OCI referrers API</a> since most of the popular registries are compliant with OCI v1.1. However, users can still opt for the referrers tag schema using <code>--force-referrers-tag true</code> if needed.</p>
<h3 id="expanded-support-for-signing-any-arbitrary-blob-files">Expanded support for signing any arbitrary blob files</h3>
<p>In addition to container images and OCI artifacts, Notation now enables signing and verification of arbitrary blob files. This enhancement broadens the scope of artifacts you can securely manage, offering greater flexibility in your workflows. The new <code>notation blob</code> command, along with its subcommands (sign, verify, policy, and inspect), facilitates these operations. It enables users to sign and verify arbitrary files such as SBOMs, GitHub release assets, tarballs, and other archive files.</p>

<h3 id="compliant-with-oci-v11-standard">Compliant with OCI v1.1 Standard</h3>
<p>Aligning with the latest OCI specifications v1.1, Notation v2.0.0-alpha.1 adopts the OCI Referrers API for storing signatures by default. This shift ensures seamless integration with OCI v1.1-compliant registries, enhancing compatibility, portability, and adherence to industry standards. Unlike traditional method of storing signature separately as an additional tag <code>sha-xxx</code> using Referrers Tag Schema, referrers API allow signatures to be linked to the signed artifact in the registry. The Referrers API also provides a structured way to query signatures (and other related metadata) for a given artifact. Instead of listing all blobs in a registry, tools can directly fetch only the relevant signatures using the referrers API, improving signing and verification efficiency.</p>
<p>For registries requiring the previous referrers tag schema, users can still opt-in using the <code>--force-referrers-tag</code> flag during the signing process. Notation will fallback to Referrers Tag Schema if the registry doesn&rsquo;t support Referrers API.</p>
<p>The Notary Project signature is now a referrer of the subject image signed by <code>notation</code>. Refer to this <a href="https://oras.land/docs/concepts/reftypes#listing-referrers" rel="noopener" target="_blank">conceptual doc</a> for more details.</p>
<p>See a sample signature using the Referrers API below:</p>
<pre><code>$ notation list ghcr.io/ratify-project/ratify@sha256:5b7efcef535eff574e064b2c0682b8a86abbeff03569a7ec78e9110fff1d8730
ghcr.io/ratify-project/ratify@sha256:5b7efcef535eff574e064b2c0682b8a86abbeff03569a7ec78e9110fff1d8730
└── application/vnd.cncf.notary.signature
└── sha256:d3c2a0b8a30aec45558f97da8577d633e5cc09bd0bf8c622896c890bf7828752
</code></pre><p>Notary Project signature manifest:</p>
<div class="highlight"><pre><code class="language-json"><span style="color: #000; font-weight: bold;">{</span>
<span style="color: #a40000;">schemaVersion:</span> <span style="color: #a40000;">2,</span>
<span style="color: #a40000;">mediaType:</span> <span style="color: #204a87; font-weight: bold;">"application/vnd.oci.image.manifest.v1+json"</span><span style="color: #000; font-weight: bold;">,</span>
<span style="color: #a40000;">config:</span> <span style="color: #a40000;">{</span>
<span style="color: #a40000;">mediaType:</span> <span style="color: #204a87; font-weight: bold;">"application/vnd.cncf.notary.signature"</span><span style="color: #000; font-weight: bold;">,</span>
<span style="color: #a40000;">digest:</span> <span style="color: #204a87; font-weight: bold;">"sha256:44136fa355b3678a1146ad16f7e8649e94fb4fc21fe77e8310c060f61caaff8a"</span><span style="color: #000; font-weight: bold;">,</span>
<span style="color: #a40000;">size:</span> <span style="color: #a40000;">2,</span>
<span style="color: #000; font-weight: bold;">}</span><span style="color: #a40000;">,</span>
<span style="color: #a40000;">layers:</span> <span style="color: #000; font-weight: bold;">[</span>
<span style="color: #000; font-weight: bold;">{</span>
<span style="color: #a40000;">mediaType:</span> <span style="color: #204a87; font-weight: bold;">"application/cose"</span><span style="color: #000; font-weight: bold;">,</span>
<span style="color: #a40000;">digest:</span> <span style="color: #204a87; font-weight: bold;">"sha256:a9dfe9f9a8c19c164642630454e0e1bf2ec0df9e385e8f4be2dda5ee322a2cb7"</span><span style="color: #000; font-weight: bold;">,</span>
<span style="color: #a40000;">size:</span> <span style="color: #a40000;">2378,</span>
<span style="color: #000; font-weight: bold;">},</span>
<span style="color: #000; font-weight: bold;">]</span><span style="color: #a40000;">,</span>
<span style="color: #a40000;">subject:</span> <span style="color: #000; font-weight: bold;">{</span>
<span style="color: #a40000;">mediaType:</span> <span style="color: #204a87; font-weight: bold;">"application/vnd.oci.image.index.v1+json"</span><span style="color: #000; font-weight: bold;">,</span>
<span style="color: #a40000;">digest:</span> <span style="color: #204a87; font-weight: bold;">"sha256:5b7efcef535eff574e064b2c0682b8a86abbeff03569a7ec78e9110fff1d8730"</span><span style="color: #000; font-weight: bold;">,</span>
<span style="color: #a40000;">size:</span> <span style="color: #a40000;">2385,</span>
<span style="color: #000; font-weight: bold;">}</span><span style="color: #a40000;">,</span>
<span style="color: #a40000;">annotations:</span> <span style="color: #000; font-weight: bold;">{</span>
<span style="color: #204a87; font-weight: bold;">"io.cncf.notary.x509chain.thumbprint#S256"</span><span style="color: #000; font-weight: bold;">:</span> <span style="color: #4e9a06;">"[\"2d71bdf96b97ee0189350a583164b7f278a9fcbb1908bc1de115e6f70d860014\"]"</span><span style="color: #000; font-weight: bold;">,</span>
<span style="color: #204a87; font-weight: bold;">"org.opencontainers.image.created"</span><span style="color: #000; font-weight: bold;">:</span> <span style="color: #4e9a06;">"2025-01-30T23:39:00Z"</span><span style="color: #000; font-weight: bold;">,</span>
<span style="color: #000; font-weight: bold;">}</span><span style="color: #a40000;">,</span>
<span style="color: #a40000;">}</span>
</code></pre></div><h3 id="delta-crl-support">Delta CRL Support</h3>
<p>To optimize security and performance, this release introduces support for Delta <a href="https://en.wikipedia.org/wiki/Certificate_revocation_list" rel="noopener" target="_blank">Certificate Revocation Lists (CRLs)</a>. Delta CRLs allow Notation to process only the changes since the last CRL update, resulting in faster and more efficient revocation checks. This enhancement reduces bandwidth usage and accelerates the verification process, ensuring up-to-date validation of certificates.</p>
<h2 id="getting-started-with-notation-v200-alpha1">Getting Started with Notation v2.0.0-alpha.1</h2>
<p>We encourage you to explore these new features and enhancements by downloading <a href="https://github.com/notaryproject/notation/releases/tag/v2.0.0-alpha.1" rel="noopener" target="_blank">Notation v2.0.0-alpha.1</a> from our GitHub releases page. You can also follow the <a href="https://notaryproject.dev/docs/user-guides/installation/cli">installation guidance</a> for detailed instruction. As this is an alpha release, we welcome your feedback to help us refine and improve the maturity. Please report any issues or suggestions on our GitHub issues page.</p>
<p>Thank you for your continued support and contributions to the Notary Project. Together, we&rsquo;re advancing the security and integrity of software supply chains.</p>
<h2 id="join-us-at-kubecon-eu-in-london">Join us at KubeCon EU in London</h2>
<p>Join two sessions at KubeCon EU in London to explore the challenges, lessons learned, and benefits of using the Notary Project. Dive deep into its mission and strategy, security audit, new use cases, and roadmap.</p>
<ul>
<li><a href="https://sched.co/1td1W" rel="noopener" target="_blank">Notary Project: The Key To Secure Software Supply Chain - Yi Zha, Microsoft &amp; Guillaume Gill, OrangeLogic</a>: April 4, 2025 13:45 - 14:15 BST, ICC Capital Suite 14-16, Level 3</li>
<li><a href="https://sched.co/1tcut" rel="noopener" target="_blank">Project Lightning Talk: Notary Project: Securing Binary Artifacts with Fine-grained Control - Yi Zha, Maintainer</a>: April 1, 2025 10:13 - 10:18 BST, Platinum Suite, Level 3</li>
</ul>
<p>Meet the Notary Project maintainers and ask us anything at our kiosk (18A) located at Level 1, Hall Entrance N8-N9. We&rsquo;ll be there every afternoon from April 2 to April 4!</p>
