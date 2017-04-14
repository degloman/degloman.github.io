---
layout: default
title: Admin Events
---

<h3>
<a id="localisation" class="anchor" href="#localisation" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>localisation</h3>

<h4>
<a id="1-modellocalisationlanguageaddlanguageafter" class="anchor" href="#1-modellocalisationlanguageaddlanguageafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>1. model/localisation/language/addLanguage/after</h4>

<h5>
<a id="language_add" class="anchor" href="#language_add" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>language_add()</h5>

<p><em>after a new language has been added, you can preform your own actions like add a new column to a table</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function language_add($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array( 'language_id' =&gt; ...);</code>
</li>
<li>
<strong>output:</strong> <code>none</code>
</li>
</ul>

<p>Exemple
<strong>admin/controller/extension/module/d_seo_module_myfeature.php</strong></p>

<div class="highlight highlight-text-html-php"><pre><span class="pl-s1"><span class="pl-k">public</span> <span class="pl-k">function</span> <span class="pl-en">language_add</span>(<span class="pl-smi">$data</span>) {</span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>model(<span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">model_extension_module_d_seo_module_myfeature</span><span class="pl-k">-&gt;</span>addLanguage(<span class="pl-smi">$data</span>);</span>
<span class="pl-s1">}</span></pre></div>

<p><strong>admin/model/extension/module/d_seo_module_myfeature.php</strong></p>

<div class="highlight highlight-text-html-php"><pre><span class="pl-s1"><span class="pl-k">public</span> <span class="pl-k">function</span> <span class="pl-en">addLanguage</span>(<span class="pl-smi">$data</span>) {</span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">db</span><span class="pl-k">-&gt;</span>query(<span class="pl-s"><span class="pl-pds">"</span><span class="pl-s1">ALTER TABLE </span><span class="pl-pds">"</span></span> <span class="pl-k">.</span> <span class="pl-c1">DB_PREFIX</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">"</span>url_redirect ADD (url_to_<span class="pl-pds">"</span></span> <span class="pl-k">.</span> (<span class="pl-k">int</span>)<span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>language_id<span class="pl-pds">'</span></span>] <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">"</span> VARCHAR(512) NOT NULL)<span class="pl-pds">"</span></span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">db</span><span class="pl-k">-&gt;</span>query(<span class="pl-s"><span class="pl-pds">"</span><span class="pl-s1"><span class="pl-k">UPDATE</span> </span><span class="pl-pds">"</span></span> <span class="pl-k">.</span> <span class="pl-c1">DB_PREFIX</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">"</span>url_redirect SET url_to_<span class="pl-pds">"</span></span> <span class="pl-k">.</span> (<span class="pl-k">int</span>)<span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>language_id<span class="pl-pds">'</span></span>] <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">"</span> = url_to_<span class="pl-pds">"</span></span> <span class="pl-k">.</span> (<span class="pl-k">int</span>)<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_language_id<span class="pl-pds">'</span></span>));</span>
<span class="pl-s1">}</span></pre></div>

<h4>
<a id="2-modellocalisationlanguagedeletelanguageafter" class="anchor" href="#2-modellocalisationlanguagedeletelanguageafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>2. model/localisation/language/deleteLanguage/after</h4>

<h5>
<a id="language_delete" class="anchor" href="#language_delete" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>language_delete()</h5>

<p><em>called when a language is deleted. Similar to <code>language_add($data)</code></em></p>

<ul>
<li>
<strong>method:</strong> <code>public function language_delete($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array( 'language_id' =&gt; ...);</code>
</li>
<li>
<strong>output:</strong> <code>none</code>
</li>
</ul>

<hr>