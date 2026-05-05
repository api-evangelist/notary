---
title: "Blog: Ratify Joins the Notary Project - Strengthening Software Supply Chain Security Together!"
url: "https://notaryproject.dev/blog/2025/welcome-ratify-joined-notaryproject/"
date: "Mon, 02 Jun 2025 00:00:00 +0000"
author: ""
feed_url: "https://notaryproject.dev/blog/index.xml"
---
<p><img alt="notary project welcomes ratify" src="https://notaryproject.dev/notation-ratify.svg" /></p>
<p>We’re excited to announce that <a href="https://ratify.dev/" rel="noopener" target="_blank">Ratify</a> has officially joined the Notary Project as a subproject after the <a href="https://github.com/notaryproject/.github/issues/81" rel="noopener" target="_blank">vote</a> passed in the community! 🎉 This marks a significant step forward in our shared mission to deliver <strong>secure, transparent, and trusted</strong> software supply chain for the cloud-native ecosystem.</p>
<p>The Notary Project is building a set of specifications and reference implementations to secure the integrity of container images and other OCI artifacts. With Ratify’s addition, we expand our surface to policy-based verification and extensibility, helping organizations validate signatures, SBOM, vulnerability scanning report, and other security metadata of container images in CI/CD and before deploying to Kubernetes.</p>
<h2 id="why-ratify">Why Ratify?</h2>
<p><a href="https://ratify.dev/" rel="noopener" target="_blank">Ratify</a> is an extensible verification framework for container images and other artifacts that can examine and author policies to audit existing resources in Kubernetes and CI/CD. Ratify can use and manage any number of custom verifiers for image metadata like signatures, SBOMs, vulnerability scan reports, and so on.</p>
<p>Ratify has been widely adopted by cloud providers and organizations to enforce verification of OCI artifacts across environments. As part of the Notary Project, Ratify brings:</p>
<ul>
<li>An end-to-end policy-driven verification capabilities</li>
<li>Extensible plugin support for different verifiers (e.g., Notation, Cosign, SBOM, vulnerability report, custom plugins) and various cloud providers (AWS, Azure, Alibaba Cloud, Venafi, etc.)</li>
<li>Enforcement at admission control when users deploying an untrusted application in Kubernetes</li>
<li>Cross-tool ecosystem support for Gatekeeper, Trivy, etc.</li>
</ul>
<p>These Ratify repositories have been transferred to Notary Project organization:</p>
<ul>
<li><a href="https://github.com/notaryproject/ratify" rel="noopener" target="_blank">Ratify core framework</a></li>
<li><a href="https://github.com/notaryproject/ratify-go" rel="noopener" target="_blank">Ratify Go Library</a></li>
<li><a href="https://github.com/notaryproject/ratify-verifier-go" rel="noopener" target="_blank">Ratify Verifier Go</a></li>
<li><a href="https://github.com/notaryproject/ratify-web" rel="noopener" target="_blank">Ratify Website</a></li>
<li><a href="https://github.com/notaryproject/ratify-containerd" rel="noopener" target="_blank">Ratify containerd plugin</a></li>
</ul>
<h2 id="what-this-means-for-the-community">What This Means for the Community</h2>
<p>By welcoming Ratify as an official subproject, the Notary Project now offers a broader and more opinionated solution stack for securing software supply chain:</p>
<ul>
<li>Notation enables signing of OCI artifacts in CI/CD pipelines.</li>
<li>Ratify enforces signature and other supply chain metadata verification policies in container runtime, Kubernetes, and CI/CD pipelines.</li>
</ul>
<p><img alt="notation-ratify-e2e" src="https://notaryproject.dev/notation-ratify-e2e.png" /></p>
<p>We also want to thank the contributors from Microsoft, Alibaba Cloud, and the wider community for their work on Ratify—and for their continued commitment to open governance by donating the project to Notary Project.</p>
<h2 id="what-should-ratify-users-know">What Should Ratify Users Know</h2>
<p>For Ratify users, the Helm repo of Ratify has been changed from <code>https://ratify-project.github.io/ratify</code> to <code>https://notaryproject.github.io/ratify</code>. Please refer to <a href="https://ratify.dev/docs/quick-start" rel="noopener" target="_blank">Ratify documentation</a> to use the latest repo.</p>
<h2 id="whats-next">What’s Next?</h2>
<p>The Ratify maintainers has been collaborating with Notary Project maintainers to align roadmaps, documentation, and release processes. You can expect:</p>
<ul>
<li>Continued development under the <a href="https://github.com/notaryproject" rel="noopener" target="_blank">Notary Project GitHub org</a></li>
<li>Unified communication channels in Notary Project including commmunity meetings, Slack channel, social media, etc.</li>
<li>Closer integration between Ratify and Notation.</li>
</ul>
<p>Please join us in welcoming Ratify to the community! 🙌</p>
<p>Follow us on <a href="https://github.com/notaryproject" rel="noopener" target="_blank">GitHub</a> and join us on <a href="https://cloud-native.slack.com/archives/CQUH8U287" rel="noopener" target="_blank">Slack channel</a>, and stay tuned for more updates.</p>
