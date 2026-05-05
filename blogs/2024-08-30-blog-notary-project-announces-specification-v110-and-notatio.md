---
title: "Blog: Notary Project announces Specification v1.1.0 and Notation v1.2.0!"
url: "https://notaryproject.dev/blog/2024/announcing-notation-v1-2/"
date: "Fri, 30 Aug 2024 00:00:00 +0000"
author: ""
feed_url: "https://notaryproject.dev/blog/index.xml"
---
<p>The Notary Project maintainers are excited to announce new releases, including <a href="https://github.com/notaryproject/specifications/releases/tag/v1.1.0" rel="noopener" target="_blank">Notary Project specifications v1.1.0</a>, <a href="https://github.com/notaryproject/notation/releases/tag/v1.2.0" rel="noopener" target="_blank">notation v1.2.0</a>, <a href="https://github.com/notaryproject/notation-go/releases/tag/v1.1.0" rel="noopener" target="_blank">notation-go v1.2.0</a>, and <a href="https://github.com/notaryproject/notation-core-go/releases/tag/v1.1.0" rel="noopener" target="_blank">notation-core-go v1.1.0</a>. These versions are now ready for production use!</p>
<h2 id="deprecation">Deprecation</h2>
<p>The experimental flag <code>--allow-referrers-api</code> used by <code>notation sign</code> and <code>notation verify</code> commands is now deprecated. See <a href="#support-oci-specification-v110">Support OCI specification v1.1.0</a> for details.</p>
<h2 id="notable-capabilities-in-this-release">Notable Capabilities in this Release</h2>
<p>Here are some of the major capabilities and features included in this release.</p>
<h3 id="notary-project-specifications">Notary Project specifications</h3>
<p>The Notary Project specifications now include support for <a href="https://www.rfc-editor.org/rfc/rfc3161" rel="noopener" target="_blank">RFC 3161</a> timestamping and introduce Notation plugin conventions in the <a href="https://github.com/notaryproject/specifications/blob/v1.1.0/specs/plugin-extensibility.md" rel="noopener" target="_blank">plugin specification</a>.</p>
<h3 id="support-oci-specification-v110">Support OCI specification v1.1.0</h3>
<p>In Feb 2024, the Open Container Initiative (OCI) community released version 1.1.0, which includes the <a href="https://github.com/opencontainers/image-spec/releases/tag/v1.1.0" rel="noopener" target="_blank">OCI image specification v1.1.0</a> and the <a href="https://github.com/opencontainers/distribution-spec/releases/tag/v1.1.0" rel="noopener" target="_blank">OCI distribution specification v1.1.0</a>. Notation now adheres to the OCI spec v1.1.0, leading to the deprecation of the experimental flag <code>--allow-referrers-api</code>. A new flag, <code>--force-referrers-tag</code> (default to <code>true</code>), has been introduced to the <code>notation sign</code> command. Using the default <code>true</code> value, the referrers tag schema is always used for storing signatures in registries. You can set the value to <code>false</code> to use the <a href="https://github.com/opencontainers/distribution-spec/blob/v1.1.0/spec.md#enabling-the-referrers-api" rel="noopener" target="_blank">referrers API</a> for signature storage if the target registry supports the referrers API (if it does not, the referrers tag fallback will be used). In contrast, the <code>notation verify/list/inspect</code> commands will attempt to use the referrers API first and automatically fall back to the <a href="https://github.com/opencontainers/distribution-spec/blob/v1.1.0/spec.md#referrers-tag-schema" rel="noopener" target="_blank">referrers tag schema</a> if the referrers API is not supported by the registry.</p>
<blockquote>
<p>[!NOTE]
We will change the default value of <code>--force-referrers-tag</code> to <code>false</code> in Notation v2.0 release, making referrers API usage as the default.</p>
</blockquote>
<h3 id="support-for-rfc-3161-compliant-timestamping">Support for RFC 3161 compliant timestamping</h3>
<p>Since this release, Notation supports RFC 3161 compliant timestamping. Digital signatures must be generated within the certificate&rsquo;s validity period, as expired certificates compromise the signature&rsquo;s trustworthiness. Timestamping extends the trust of signatures created within certificate validity, allowing successful signature verification even after certificates have expired. Notation&rsquo;s timestamping feature is built on top of the <a href="https://github.com/notaryproject/tspclient-go" rel="noopener" target="_blank">tspclient-go</a> library.</p>
<p>Learn more at the document <a href="https://notaryproject.dev/docs/user-guides/how-to/timestamping/">how to sign and verify artifacts in OCI-compliant registries with timestamping</a>.</p>
<h3 id="other-changes">Other changes</h3>
<p>Notation CLI now offers the <code>armv7</code> binary, enabling its usage in environments such as Internet of Things (IoT) or embedded systems.</p>
<h2 id="get-started-with-notation-v120">Get started with Notation v1.2.0</h2>
<p>You can follow the <a href="https://notaryproject.dev/docs/quickstart-guides/quickstart-sign-image-artifact/">quick start guide</a> to try Notation v1.2.0 for basic signing and verification workflow.</p>
<h2 id="whats-next">What&rsquo;s next</h2>
<p>The Notary Project maintainers are considering the following features for future milestones. Feel free to reach out on the <a href="https://app.slack.com/client/T08PSQ7BQ/CQUH8U287/" rel="noopener" target="_blank">Slack channel</a> or <a href="https://github.com/notaryproject/notation/issues" rel="noopener" target="_blank">GitHub issues</a> to ask questions, provide feedback, or share ideas.</p>
<ul>
<li>Revocation checking using Certificate Revocation List (CRL)</li>
<li>Sign and verify arbitrary blobs</li>
<li>Attestations</li>
</ul>
<p>And more!</p>
<h2 id="acknowledgements">Acknowledgements</h2>
<p>The Notary Project release team wants to thank the entire Notary Project community for all the activity and engagement that has been vital for helping the project grow and reach this milestone.</p>
