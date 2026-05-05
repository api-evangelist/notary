---
title: "Blog: Notary Project announces Notation v1.1.0!"
url: "https://notaryproject.dev/blog/2024/announcing-notation-v1-1/"
date: "Thu, 08 Feb 2024 00:00:00 +0000"
author: ""
feed_url: "https://notaryproject.dev/blog/index.xml"
---
<p>The Notary Project maintainers are proud to announce new releases for its sub-projects, including <a href="https://github.com/notaryproject/specifications/releases/tag/v1.1.0" rel="noopener" target="_blank">Notary Project specifications v1.1.0</a>, <a href="https://github.com/notaryproject/notation/releases/tag/v1.1.0" rel="noopener" target="_blank">notation v1.1.0</a>, <a href="https://github.com/notaryproject/notation-go/releases/tag/v1.1.0" rel="noopener" target="_blank">notation-go v1.1.0</a>, and <a href="https://github.com/notaryproject/notation-core-go/releases/tag/v1.0.2" rel="noopener" target="_blank">notation-core-go v1.0.2</a>, <a href="https://github.com/notaryproject/notation-action/releases/tag/v1.0.1" rel="noopener" target="_blank">Notation GitHub Actions v1.0.1</a> which are ready for production use!</p>
<p>Meanwhile, a new library <a href="https://github.com/notaryproject/notation-plugin-framework-go" rel="noopener" target="_blank">notation-plugin-framework-go
</a> released the first release v1.0.0. It contains framework required to create notation plugins as per <a href="https://github.com/notaryproject/specifications/blob/v1.1.0/specs/plugin-extensibility.md" rel="noopener" target="_blank">Notation Plugin specification</a>.</p>
<h2 id="notable-capabilities-in-this-release">Notable Capabilities in this Release</h2>
<p>Here are some of the major capabilities and features included in this release.</p>
<h3 id="easier-plugin-management-functionalities">Easier plugin management functionalities</h3>
<p>Notation has an <a href="https://github.com/notaryproject/specifications/blob/v1.1.0/specs/plugin-extensibility.md" rel="noopener" target="_blank">extensible design based on a plugin framework</a>. This framework provides plugin interfaces for users and vendors to implement their own integration with key/certificate management solutions or signing services.</p>
<p>In this release, Notation offers Notation plugin management capabilities to simplify the plugin user experience.</p>
<ul>
<li>Added new command <code>notation plugin install</code>. Users are now able to install a notation plugin directly from a URL or from their file system. Supported plugin installation formats are <code>.zip</code>, <code>.tar.gz</code>, and single plugin executable file. See an example usage below:</li>
</ul>
<div class="highlight"><pre><code class="language-bash">$ notation plugin install --file &lt;file_path&gt;
</code></pre></div><div class="highlight"><pre><code class="language-bash">$ notation plugin install --sha256sum &lt;digest&gt; --url &lt;HTTPS_URL&gt;
</code></pre></div><ul>
<li>Added new command <code>notation plugin uninstall</code>. Users are now able to uninstall a notation plugin by providing the plugin name. See an example usage below:</li>
</ul>
<div class="highlight"><pre><code class="language-bash">notation plugin uninstall &lt;plugin_name&gt;
</code></pre></div><p>The following plugins have been well tested with Notation plugin commands by Notary Project maintainers:</p>
<ul>
<li><a href="https://docs.aws.amazon.com/signer/latest/developerguide/Welcome.html" rel="noopener" target="_blank">AWS Signer plugin for Notation</a></li>
<li><a href="https://learn.microsoft.com/en-us/azure/container-registry/container-registry-tutorial-sign-build-push" rel="noopener" target="_blank">Azure Key Vault for Notation</a></li>
<li><a href="https://github.com/Venafi/notation-venafi-csp" rel="noopener" target="_blank">Venafi CodeSign Protect Signing Plugin for Notation</a></li>
</ul>
<h3 id="specifications">Specifications</h3>
<p>For plugin vendors who want to package and distribute a Notation plugin, <a href="https://github.com/notaryproject/specifications/blob/v1.1.0/specs/plugin-extensibility.md" rel="noopener" target="_blank">Notation Plugin specification</a> defines the plugin conventions to ensure plugins are delivered in a consistent format and compatible with <code>notation plugin</code> management commands.</p>
<h3 id="get-started-with-notation-v110">Get started with Notation v1.1.0</h3>
<p>You can follow this <a href="https://notaryproject.dev/docs/quickstart/" rel="noopener" target="_blank">quick start</a> to try Notation v1.1.0 on your terminal.</p>
<p>The default Notation CLI setup action in Notation GitHub Actions has also been updated to v1.1.0. It enables users to install Notation and its plugin, sign and verify OCI artifacts in GitHub Actions workflow with ease.</p>
<p>To get started with Notation v1.1.0 in a CI/CD workflow, you can find the Notation GitHub Actions in the <a href="https://github.com/marketplace/actions/notation-actions" rel="noopener" target="_blank">Marketplace</a>.</p>
<h2 id="whats-next">What&rsquo;s next</h2>
<p>The Notary Project maintainers are considering the following features for future milestones. Feel free to reach out on the <a href="https://app.slack.com/client/T08PSQ7BQ/CQUH8U287/" rel="noopener" target="_blank">Slack channel</a> or <a href="https://github.com/notaryproject/notation/issues" rel="noopener" target="_blank">GitHub issues</a> to ask questions, provide feedback, or share ideas.</p>
<ul>
<li>Sign and verify arbitrary blobs</li>
<li>Timestamping support</li>
<li>Improve error messages and verbose logs</li>
</ul>
<p>And more!</p>
<h2 id="acknowledgements">Acknowledgements</h2>
<p>The Notary Project release team wants to thank the entire Notary Project community for all the activity and engagement that has been vital for helping the project grow and reach this major milestone.</p>
