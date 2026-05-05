---
title: "Blog: Notary Project announces a major release!"
url: "https://notaryproject.dev/blog/2023/announcing-major-release/"
date: "Tue, 22 Aug 2023 00:00:00 +0000"
author: ""
feed_url: "https://notaryproject.dev/blog/index.xml"
---
<p>The Notary Project maintainers are proud to announce a major release, including <a href="https://github.com/notaryproject/specifications/releases/tag/v1.0.0" rel="noopener" target="_blank">Notary Project specifications v1.0.0</a>, <a href="https://github.com/notaryproject/notation/releases/tag/v1.0.0" rel="noopener" target="_blank">notation v1.0.0</a>, <a href="https://github.com/notaryproject/notation-go/releases/tag/v1.0.0" rel="noopener" target="_blank">notation-go v1.0.0</a>, and <a href="https://github.com/notaryproject/notation-core-go/releases/tag/v1.0.0" rel="noopener" target="_blank">notation-core-go v1.0.0</a> which are ready for production use!</p>
<h2 id="what-is-notary-project-and-notation">What is Notary Project and Notation?</h2>
<p>As containers and cloud native artifacts become common deployment units, users want to make sure that they are authentic in their environments. The Notary Project is a set of specifications and tools intended to provide cross-industry standards for securing software supply chains through signing and verification, signature portability, and key/certificate management.</p>
<p>Notation is a sub-project of Notary Project, which consists of the <code>notation</code> CLI and two Golang libraries which implement the latest <a href="https://github.com/notaryproject/specifications/releases/tag/v1.0.0" rel="noopener" target="_blank">Notary Project specifications</a>. Notation was started in <a href="https://github.com/notaryproject/meeting-notes/blob/main/meeting-notes-2019.md#notary-v2-kickoff-meeting" rel="noopener" target="_blank">Dec 2019</a> and the code has matured through a series of minor and RC releases over the last few years; The first version of the CLI and libraries <a href="https://notaryproject.dev/blog/2021/announcing-notation-alpha1/" rel="noopener" target="_blank">v0.7.0-alpha.1</a> was released in Oct 2021. Several alpha, beta, and RC releases later, the binaries reached the final <a href="https://notaryproject.dev/blog/2023/announcing-notation-rc6/" rel="noopener" target="_blank">v1.0.0-RC.7</a> release in May 2023.</p>
<p>To learn more about the Notary Project, see the <a href="https://github.com/notaryproject/.github#notary-project-overview" rel="noopener" target="_blank">Notary Project Overview</a> and the <a href="https://notaryproject.dev/docs/faq/#notary-project-terms" rel="noopener" target="_blank">FAQ</a>.</p>
<h2 id="notable-capabilities-in-this-release">Notable Capabilities in this Release</h2>
<p>Here are some of the major capabilities and features included in this release.</p>
<h3 id="specifications">Specifications</h3>
<p><a href="https://github.com/notaryproject/specifications/releases/tag/v1.0.0" rel="noopener" target="_blank">Notary Project specifications</a> reached its major release. All specifications, requirements, scenarios, threat model, and security audit reports are available in this release. ISVs and tool developers that want to interoperate with the Notary Project signatures and tooling should use the specifications to ensure compatibility.</p>
<ul>
<li><a href="https://github.com/notaryproject/specifications/blob/v1.0.0/specs/signature-specification.md" rel="noopener" target="_blank">Notary Project OCI signature specification</a></li>
<li><a href="https://github.com/notaryproject/specifications/blob/v1.0.0/specs/signature-envelope-cose.md" rel="noopener" target="_blank">Notary Project OCI COSE signature envelope</a></li>
<li><a href="https://github.com/notaryproject/specifications/blob/v1.0.0/specs/signature-envelope-jws.md" rel="noopener" target="_blank">Notary Project OCI JWS signature envelope</a></li>
<li><a href="https://github.com/notaryproject/specifications/blob/v1.0.0/specs/signing-and-verification-workflow.md" rel="noopener" target="_blank">Notary Project OCI signing and verification workflow</a></li>
<li><a href="https://github.com/notaryproject/specifications/blob/v1.0.0/specs/signing-scheme.md" rel="noopener" target="_blank">Notary Project signing scheme</a></li>
<li><a href="https://github.com/notaryproject/specifications/blob/v1.0.0/specs/trust-store-trust-policy.md" rel="noopener" target="_blank">Notary Project Trust Store and Trust Policy</a></li>
<li><a href="https://github.com/notaryproject/specifications/blob/v1.0.0/specs/plugin-extensibility.md" rel="noopener" target="_blank">Notation Plugin specification</a></li>
</ul>
<h3 id="signing-and-verification-functionalities">Signing and verification functionalities</h3>
<p>From the software producer&rsquo;s perspective, signing a software artifact enables their consumers to detect tampering and ensure authenticity of the artifact. Signing software can also increase trust when distributing software artifacts to consumers. Notary Project provides the following core capabilities for the signing experience:</p>
<ul>
<li>Sign artifacts using signing keys stored securely in a key management system (KMS) or a signing service. See the available plugins in the section <a href="#extensibility-plugin-support-for-notation">Extensibility: plugin support for Notation</a></li>
<li>Sign artifacts as well as list and inspect signatures stored in OCI-compliant registries
<ul>
<li>Compliant with <a href="https://github.com/opencontainers/image-spec/tree/v1.0.2" rel="noopener" target="_blank"><code>image-spec v1.0.2</code></a></li>
<li>Compliant with <a href="https://github.com/opencontainers/distribution-spec/tree/v1.0.1" rel="noopener" target="_blank"><code>distribution-spec v1.0.1</code></a></li>
<li>Compatible with <a href="https://github.com/opencontainers/image-spec/tree/v1.1.0-rc4" rel="noopener" target="_blank"><code>image-spec v1.1.0-rc4</code></a></li>
<li>Compatible with <a href="https://github.com/opencontainers/distribution-spec/tree/v1.1.0-rc3" rel="noopener" target="_blank"><code>distribution-spec v1.1.0-rc3</code></a> (limited to <a href="https://github.com/opencontainers/distribution-spec/blob/v1.1.0-rc3/spec.md#referrers-tag-schema" rel="noopener" target="_blank">referrers tag schema</a>)</li>
</ul>
</li>
<li>Support two signature envelope formats
<ul>
<li><a href="https://github.com/notaryproject/notaryproject/blob/v1.0.0/specs/signature-envelope-cose.md" rel="noopener" target="_blank">COSE</a>: COSE is an efficient, binary envelope format that can be used for variety of scenarios ranging from signing traditional software to IoT workloads running on low-powered devices.</li>
<li><a href="https://github.com/notaryproject/notaryproject/blob/v1.0.0/specs/signature-envelope-jws.md" rel="noopener" target="_blank">JWS</a>: JWS is a widely used JSON-based envelope format that can be used for interoperability with existing applications and various authentication schemes including OIDC.</li>
</ul>
</li>
</ul>
<p>From the software consumer&rsquo;s perspective, verifying the signature of a signed artifact ensures its integrity and authenticity. Notary Project provides the following core capabilities for verification experience:</p>
<ul>
<li>Verify signatures using <a href="https://github.com/notaryproject/specifications/blob/v1.0.0/specs/trust-store-trust-policy.md" rel="noopener" target="_blank">trust store and trust policy</a>. This also includes fine-tuned OCI repository specific trust policies and support for various enforcement levels (e.g. <code>enforce</code>, <code>permissive</code>, <code>audit</code>) to enable a wide range of scenarios.</li>
<li><a href="https://notaryproject.dev/docs/user-guides/cli-reference/notation_policy/"><code>notation policy</code></a> command can be used to simplify the experience of importing and inspecting the trust policy.</li>
</ul>
<h3 id="experimental-features">Experimental features</h3>
<p>Experimental features are intended for testing and evaluation purposes only and should not be used in production environments. Users can enable experimental features in Notation CLI by setting the environment variable <code>NOTATION_EXPERIMENTAL</code> to 1 as shown below.</p>
<pre><code>export NOTATION_EXPERIMENTAL=1
</code></pre><p>There are two major features which are marked as experimental.</p>
<ul>
<li><a href="https://notaryproject.dev/docs/user-guides/how-to/oci-image-layout/">Signing, listing, and verifying artifacts with OCI image layout</a> before they are pushed to a registry. This enables users sign and verify artifacts stored on the local file system.</li>
<li><a href="https://github.com/opencontainers/distribution-spec/blob/v1.1.0-rc2/spec.md#enabling-the-referrers-api" rel="noopener" target="_blank">OCI distribution referrers API</a>. This allows the Notation CLI to fetch a list of signatures in an efficient and clean manner.</li>
</ul>
<h3 id="extensibility-plugin-support-for-notation">Extensibility: plugin support for Notation</h3>
<p>Notation has an <a href="https://github.com/notaryproject/specifications/blob/v1.0.0/specs/plugin-extensibility.md" rel="noopener" target="_blank">extensible design based on a plugin framework</a>. This framework provides plugin interfaces for users and vendors to implement their own integrations with key/certificate management solutions or signing services. Currently, Notation has the following plugins available.</p>
<ul>
<li><a href="https://docs.aws.amazon.com/signer/latest/developerguide/Welcome.html" rel="noopener" target="_blank">AWS Signer plugin for Notation</a></li>
<li><a href="https://learn.microsoft.com/en-us/azure/container-registry/container-registry-tutorial-sign-build-push" rel="noopener" target="_blank">Azure Key Vault for Notation</a></li>
</ul>
<h3 id="integration-with-admission-controller-for-kubernetes-usage">Integration with admission controller for Kubernetes usage</h3>
<p>To enable users to verify and secure image deployment on Kubernetes, the Notary Project maintainers worked with the <a href="https://github.com/deislabs/ratify" rel="noopener" target="_blank">Ratify</a> and <a href="https://kyverno.io/" rel="noopener" target="_blank">Kyverno</a> teams to provide solutions for verifying images signed by Notation before deploying them to Kubernetes. Users have two different options to build a complete end-to-end image integrity workflow for their environments. For more details, see:</p>
<ul>
<li><a href="https://ratify.dev/blog/sign-and-verify-image-with-notation-ratify" rel="noopener" target="_blank">Sign and verify an image with Notation, Ratify, and OPA Gatekeeper</a></li>
<li><a href="https://kyverno.io/docs/writing-policies/verify-images/notary/" rel="noopener" target="_blank">Verify CNCF Notary Project signatures with Kyverno</a></li>
</ul>
<p><img alt="e2e workflow" src="https://notaryproject.dev/e2e-workflow.png" /></p>
<h2 id="built-in-security">Built-in security</h2>
<p>As part of our commitment to security, the Notary Project maintainers engaged with CNCF to set up continuous fuzzing of the source code and completed a security audit in 2023. All vulnerabilities found during the testing and the audit were fixed before the release of the libraries and the CLI. Below are links to the security reports:</p>
<ul>
<li><a href="https://github.com/notaryproject/notaryproject/blob/main/security/reports/audit/ADA-notation-security-audit-23.pdf" rel="noopener" target="_blank">Notation Security Audit Report 2023</a></li>
<li><a href="https://github.com/notaryproject/notaryproject/tree/main/security/reports/fuzzing/ADA-fuzzing-audit-22-23.pdf" rel="noopener" target="_blank">Notary Project fuzzing audit report 22-23</a></li>
</ul>
<h2 id="whats-next">What&rsquo;s next</h2>
<p>The Notary Project maintainers are considering the following features for future milestones. Feel free to reach out on the <a href="https://app.slack.com/client/T08PSQ7BQ/CQUH8U287/" rel="noopener" target="_blank">Slack channel</a> or <a href="https://github.com/notaryproject/.github/issues" rel="noopener" target="_blank">GitHub issues</a> to ask questions, provide feedback, or share ideas.</p>
<ul>
<li>Sign and verify arbitrary blobs</li>
<li><a href="https://github.com/notaryproject/notation-action" rel="noopener" target="_blank">GitHub Actions</a> and other CI/CD integration for signing and verification</li>
<li><a href="https://github.com/notaryproject/notation-hashicorp-vault" rel="noopener" target="_blank">HashiCorp Vault plugin</a> (experimental)</li>
<li>Plugin lifecycle management</li>
<li>Timestamping support</li>
<li>Manage trust policy via CLI commands</li>
</ul>
<h2 id="acknowledgements">Acknowledgements</h2>
<p>The Notary Project release team wants to thank the entire Notary Project community for all the activity and engagement that has been vital for helping the project grow and reach this major milestone.</p>
<h2 id="try-it-now">Try it now</h2>
<p>You can follow this <a href="https://killercoda.com/notaryproject/scenario/notation" rel="noopener" target="_blank">interactive tutorial</a> to try Notation CLI v1.0.0 in an online cloud playground or follow the <a href="https://notaryproject.dev/docs/quickstart/" rel="noopener" target="_blank">quick start</a> on your computer.</p>
