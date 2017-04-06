---
layout: default
title: API
---

<h1>
<a id="api" class="anchor" href="#api" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>API</h1>

<p>You can extend the SEO Module functionality by using the built-in API. The SEO module will look inside the <code>admin/controller/extension/module/</code> for <code>d_seo_module_*.php</code> and if found, will call specially named methods. The result will be used to modify the output using Opencart Event Methods.</p>

<h4>
<a id="for-the-api-to-work-you-will-need" class="anchor" href="#for-the-api-to-work-you-will-need" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>For the API to work you will need</h4>

<ol>
<li>name your extension controller beginning with <code>d_seo_module_</code>
</li>
<li>Add method, that corresponds to the event you want to subscribe to.</li>
</ol>

<p>Here is an example of adding a new item to the SEO module Menu in admin panel:</p>

<div class="highlight highlight-text-html-php"><pre><span class="pl-s1"><span class="pl-k">private</span> <span class="pl-smi">$route</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature<span class="pl-pds">'</span></span>;</span>
<span class="pl-s1"><span class="pl-k">public</span> <span class="pl-k">function</span> <span class="pl-en">menu</span>(<span class="pl-smi">$menu_data</span>) {</span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>language(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">route</span>);</span>
<span class="pl-s1">    <span class="pl-k">if</span> (<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">user</span><span class="pl-k">-&gt;</span>hasPermission(<span class="pl-s"><span class="pl-pds">'</span>access<span class="pl-pds">'</span></span>, <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">route</span>)) {</span>
<span class="pl-s1">        <span class="pl-smi">$menu_data</span>[] <span class="pl-k">=</span> <span class="pl-c1">array</span>(</span>
<span class="pl-s1">            <span class="pl-s"><span class="pl-pds">'</span>name<span class="pl-pds">'</span></span>     <span class="pl-k">=&gt;</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">language</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>heading_title_main<span class="pl-pds">'</span></span>),</span>
<span class="pl-s1">            <span class="pl-s"><span class="pl-pds">'</span>href<span class="pl-pds">'</span></span>     <span class="pl-k">=&gt;</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">url</span><span class="pl-k">-&gt;</span>link(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">route</span>, <span class="pl-s"><span class="pl-pds">'</span>token=<span class="pl-pds">'</span></span> <span class="pl-k">.</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">session</span><span class="pl-k">-&gt;</span><span class="pl-smi">data</span>[<span class="pl-s"><span class="pl-pds">'</span>token<span class="pl-pds">'</span></span>], <span class="pl-c1">true</span>),</span>
<span class="pl-s1">            <span class="pl-s"><span class="pl-pds">'</span>children<span class="pl-pds">'</span></span> <span class="pl-k">=&gt;</span> <span class="pl-c1">array</span>()       </span>
<span class="pl-s1">        );</span>
<span class="pl-s1">    }</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-k">return</span> <span class="pl-smi">$menu_data</span>;</span>
<span class="pl-s1">}</span></pre></div>

<hr>
