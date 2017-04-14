---
layout: default
title: common
---
<h3>
<a id="catalog-common" class="anchor" href="#catalog-common" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>catalog common</h3>

<h4>
<a id="1-viewcommonhomebefore" class="anchor" href="#1-viewcommonhomebefore" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>1. view/common/home/before</h4>

<h5>
<a id="home_data" class="anchor" href="#home_data" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>home_data()</h5>

<p><em>modify the data that will be rendered to the <code>home.tpl</code></em></p>

<ul>
<li>
<strong>method:</strong> <code>public function home_data($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array( ... )</code>
</li>
<li>
<strong>output:</strong> <code>$data = array( ... )</code>
</li>
</ul>

<p>Example:</p>

<div class="highlight highlight-text-html-php"><pre><span class="pl-s1"><span class="pl-k">private</span> <span class="pl-smi">$codename</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>d_seo_module_myfeature<span class="pl-pds">'</span></span>;</span>
<span class="pl-s1"><span class="pl-k">private</span> <span class="pl-smi">$route</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature<span class="pl-pds">'</span></span>;</span>
<span class="pl-s1"><span class="pl-k">private</span> <span class="pl-smi">$config_file</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>d_seo_module_myfeature<span class="pl-pds">'</span></span>;</span>
<span class="pl-s1"></span>
<span class="pl-s1"><span class="pl-k">public</span> <span class="pl-k">function</span> <span class="pl-en">home_data</span>(<span class="pl-smi">$data</span>) {</span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>model(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">route</span>);</span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>model(<span class="pl-s"><span class="pl-pds">'</span>setting/setting<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-smi">$store_id</span> <span class="pl-k">=</span> (<span class="pl-k">int</span>)<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_store_id<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">    <span class="pl-smi">$language_id</span> <span class="pl-k">=</span> (<span class="pl-k">int</span>)<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_language_id<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-c">// Get settings of d_seo_module_myfeature</span></span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>load(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config_file</span>);</span>
<span class="pl-s1">    <span class="pl-smi">$config_setting</span> <span class="pl-k">=</span> (<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">'</span>_setting<span class="pl-pds">'</span></span>)) ? <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">'</span>_setting<span class="pl-pds">'</span></span>) : <span class="pl-c1">array</span>();</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-smi">$setting</span> <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">model_setting_setting</span><span class="pl-k">-&gt;</span>getSetting(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span>, <span class="pl-smi">$store_id</span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-smi">$status</span> <span class="pl-k">=</span> <span class="pl-c1">isset</span>(<span class="pl-smi">$setting</span>[<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">'</span>_status<span class="pl-pds">'</span></span>]) ? <span class="pl-smi">$setting</span>[<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">'</span>_status<span class="pl-pds">'</span></span>] : <span class="pl-c1">false</span>;</span>
<span class="pl-s1">    <span class="pl-smi">$setting</span> <span class="pl-k">=</span> <span class="pl-c1">isset</span>(<span class="pl-smi">$setting</span>[<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">'</span>_setting<span class="pl-pds">'</span></span>]) ? <span class="pl-smi">$setting</span>[<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">'</span>_setting<span class="pl-pds">'</span></span>] : <span class="pl-c1">array</span>();</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-k">if</span> (<span class="pl-k">!</span><span class="pl-c1">empty</span>(<span class="pl-smi">$setting</span>)) {</span>
<span class="pl-s1">        <span class="pl-smi">$config_setting</span> <span class="pl-k">=</span> <span class="pl-c1">array_replace_recursive</span>(<span class="pl-smi">$config_setting</span>, <span class="pl-smi">$setting</span>);</span>
<span class="pl-s1">    }</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-smi">$setting</span> <span class="pl-k">=</span> <span class="pl-smi">$config_setting</span>;</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-c">//check for d_seo_module_myfeature_status</span></span>
<span class="pl-s1">    <span class="pl-k">if</span> (<span class="pl-smi">$status</span>) {</span>
<span class="pl-s1">        <span class="pl-k">if</span> (<span class="pl-c1">isset</span>(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">request</span><span class="pl-k">-&gt;</span><span class="pl-smi">post</span>[<span class="pl-s"><span class="pl-pds">'</span>config_description<span class="pl-pds">'</span></span>])) {</span>
<span class="pl-s1">            <span class="pl-smi">$description</span> <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">request</span><span class="pl-k">-&gt;</span><span class="pl-smi">post</span>[<span class="pl-s"><span class="pl-pds">'</span>config_description<span class="pl-pds">'</span></span>];</span>
<span class="pl-s1">            <span class="pl-smi">$meta_title</span> <span class="pl-k">=</span> <span class="pl-smi">$description</span>[<span class="pl-smi">$language_id</span>][<span class="pl-s"><span class="pl-pds">'</span>meta_title<span class="pl-pds">'</span></span>];</span>
<span class="pl-s1">            <span class="pl-smi">$meta_description</span><span class="pl-k">=</span> <span class="pl-smi">$description</span>[<span class="pl-smi">$language_id</span>][<span class="pl-s"><span class="pl-pds">'</span>meta_description<span class="pl-pds">'</span></span>];</span>
<span class="pl-s1">            <span class="pl-smi">$meta_keyword</span> <span class="pl-k">=</span> <span class="pl-smi">$description</span>[<span class="pl-smi">$language_id</span>][<span class="pl-s"><span class="pl-pds">'</span>meta_keyword<span class="pl-pds">'</span></span>];</span>
<span class="pl-s1">        } <span class="pl-k">elseif</span> (<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_description<span class="pl-pds">'</span></span>)) {</span>
<span class="pl-s1">            <span class="pl-smi">$description</span> <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_description<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">            <span class="pl-smi">$meta_title</span> <span class="pl-k">=</span> <span class="pl-smi">$description</span>[<span class="pl-smi">$language_id</span>][<span class="pl-s"><span class="pl-pds">'</span>meta_title<span class="pl-pds">'</span></span>];</span>
<span class="pl-s1">            <span class="pl-smi">$meta_description</span> <span class="pl-k">=</span> <span class="pl-smi">$description</span>[<span class="pl-smi">$language_id</span>][<span class="pl-s"><span class="pl-pds">'</span>meta_description<span class="pl-pds">'</span></span>];</span>
<span class="pl-s1">            <span class="pl-smi">$meta_keyword</span> <span class="pl-k">=</span> <span class="pl-smi">$description</span>[<span class="pl-smi">$language_id</span>][<span class="pl-s"><span class="pl-pds">'</span>meta_keyword<span class="pl-pds">'</span></span>];</span>
<span class="pl-s1">        } <span class="pl-k">else</span> {</span>
<span class="pl-s1">            <span class="pl-smi">$meta_title</span> <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_meta_title<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">            <span class="pl-smi">$meta_description</span> <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_meta_description<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">            <span class="pl-smi">$meta_keyword</span> <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_meta_keyword<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">        }</span>
<span class="pl-s1"></span>
<span class="pl-s1">        <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">document</span><span class="pl-k">-&gt;</span>setTitle(<span class="pl-smi">$meta_title</span>);</span>
<span class="pl-s1">        <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">document</span><span class="pl-k">-&gt;</span>setDescription(<span class="pl-smi">$meta_description</span>);</span>
<span class="pl-s1">        <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">document</span><span class="pl-k">-&gt;</span>setKeywords(<span class="pl-smi">$meta_keyword</span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1">        <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>header<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>controller(<span class="pl-s"><span class="pl-pds">'</span>common/header<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">    }</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-k">return</span> <span class="pl-smi">$data</span>;</span>
<span class="pl-s1">}</span></pre></div>

<h4>
<a id="2-viewtemplatecommonhomeafter" class="anchor" href="#2-viewtemplatecommonhomeafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>2. view/*/template/common/home/after</h4>

<h5>
<a id="home_html" class="anchor" href="#home_html" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>home_html()</h5>

<p><em>modify the HTML of the <code>home.tpl</code> before bowser renders it</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function home_html($output)</code>
</li>
<li>
<strong>parameters:</strong> <code>(string) $output</code>
</li>
<li>
<strong>output:</strong> <code>(string) $output</code>
</li>
</ul>

<p>Example:</p>

<div class="highlight highlight-text-html-php"><pre><span class="pl-s1"><span class="pl-k">private</span> <span class="pl-smi">$codename</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>d_seo_module_myfeature<span class="pl-pds">'</span></span>;</span>
<span class="pl-s1"><span class="pl-k">private</span> <span class="pl-smi">$route</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature<span class="pl-pds">'</span></span>;</span>
<span class="pl-s1"><span class="pl-k">private</span> <span class="pl-smi">$config_file</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>d_seo_module_myfeature<span class="pl-pds">'</span></span>;</span>
<span class="pl-s1"></span>
<span class="pl-s1"><span class="pl-k">public</span> <span class="pl-k">function</span> <span class="pl-en">home_html</span>(<span class="pl-smi">$html</span>) {</span>
<span class="pl-s1">        <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>model(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">route</span>);</span>
<span class="pl-s1">        <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>model(<span class="pl-s"><span class="pl-pds">'</span>setting/setting<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1">        <span class="pl-smi">$store_id</span> <span class="pl-k">=</span> (<span class="pl-k">int</span>)<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_store_id<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">        <span class="pl-smi">$language_id</span> <span class="pl-k">=</span> (<span class="pl-k">int</span>)<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_language_id<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1">        <span class="pl-c">// Setting</span></span>
<span class="pl-s1">        <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>load(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config_file</span>);</span>
<span class="pl-s1">        <span class="pl-smi">$config_setting</span> <span class="pl-k">=</span> (<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">'</span>_setting<span class="pl-pds">'</span></span>)) ? <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">'</span>_setting<span class="pl-pds">'</span></span>) : <span class="pl-c1">array</span>();</span>
<span class="pl-s1"></span>
<span class="pl-s1">        <span class="pl-smi">$setting</span> <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">model_setting_setting</span><span class="pl-k">-&gt;</span>getSetting(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span>, <span class="pl-smi">$store_id</span>);</span>
<span class="pl-s1">        <span class="pl-smi">$status</span> <span class="pl-k">=</span> <span class="pl-c1">isset</span>(<span class="pl-smi">$setting</span>[<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">'</span>_status<span class="pl-pds">'</span></span>]) ? <span class="pl-smi">$setting</span>[<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">'</span>_status<span class="pl-pds">'</span></span>] : <span class="pl-c1">false</span>;</span>
<span class="pl-s1">        <span class="pl-smi">$setting</span> <span class="pl-k">=</span> <span class="pl-c1">isset</span>(<span class="pl-smi">$setting</span>[<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">'</span>_setting<span class="pl-pds">'</span></span>]) ? <span class="pl-smi">$setting</span>[<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">codename</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">'</span>_setting<span class="pl-pds">'</span></span>] : <span class="pl-c1">array</span>();</span>
<span class="pl-s1"></span>
<span class="pl-s1">        <span class="pl-k">if</span> (<span class="pl-k">!</span><span class="pl-c1">empty</span>(<span class="pl-smi">$setting</span>)) {</span>
<span class="pl-s1">            <span class="pl-smi">$config_setting</span> <span class="pl-k">=</span> <span class="pl-c1">array_replace_recursive</span>(<span class="pl-smi">$config_setting</span>, <span class="pl-smi">$setting</span>);</span>
<span class="pl-s1">        }</span>
<span class="pl-s1"></span>
<span class="pl-s1">        <span class="pl-smi">$setting</span> <span class="pl-k">=</span> <span class="pl-smi">$config_setting</span>;</span>
<span class="pl-s1"></span>
<span class="pl-s1">        <span class="pl-k">if</span> (<span class="pl-smi">$status</span>) {</span>
<span class="pl-s1">            <span class="pl-k">if</span> (<span class="pl-c1">isset</span>(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">request</span><span class="pl-k">-&gt;</span><span class="pl-smi">post</span>[<span class="pl-s"><span class="pl-pds">'</span>config_description<span class="pl-pds">'</span></span>])) {</span>
<span class="pl-s1">                <span class="pl-smi">$description</span> <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">request</span><span class="pl-k">-&gt;</span><span class="pl-smi">post</span>[<span class="pl-s"><span class="pl-pds">'</span>config_description<span class="pl-pds">'</span></span>];</span>
<span class="pl-s1">                <span class="pl-smi">$meta_robots</span> <span class="pl-k">=</span> <span class="pl-smi">$description</span>[<span class="pl-smi">$language_id</span>][<span class="pl-s"><span class="pl-pds">'</span>meta_robots<span class="pl-pds">'</span></span>];</span>
<span class="pl-s1">            } <span class="pl-k">elseif</span> (<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_description<span class="pl-pds">'</span></span>)) {</span>
<span class="pl-s1">                <span class="pl-smi">$description</span> <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_description<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">                <span class="pl-smi">$meta_robots</span> <span class="pl-k">=</span> <span class="pl-smi">$description</span>[<span class="pl-smi">$language_id</span>][<span class="pl-s"><span class="pl-pds">'</span>meta_robots<span class="pl-pds">'</span></span>];</span>
<span class="pl-s1">            } <span class="pl-k">else</span> {</span>
<span class="pl-s1">                <span class="pl-smi">$meta_robots</span> <span class="pl-k">=</span> <span class="pl-s"><span class="pl-pds">'</span>index,follow<span class="pl-pds">'</span></span>;</span>
<span class="pl-s1">            }</span>
<span class="pl-s1"></span>
<span class="pl-s1">            <span class="pl-smi">$html_dom</span> <span class="pl-k">=</span> <span class="pl-k">new</span> <span class="pl-c1">d_simple_html_dom</span>();</span>
<span class="pl-s1">            <span class="pl-smi">$html_dom</span><span class="pl-k">-&gt;</span>load(<span class="pl-smi">$html</span>, <span class="pl-smi">$lowercase</span><span class="pl-k">=</span><span class="pl-c1">true</span>, <span class="pl-smi">$stripRN</span><span class="pl-k">=</span><span class="pl-c1">false</span>, <span class="pl-smi">$defaultBRText</span><span class="pl-k">=</span><span class="pl-c1">DEFAULT_BR_TEXT</span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1">            <span class="pl-smi">$html_dom</span><span class="pl-k">-&gt;</span>find(<span class="pl-s"><span class="pl-pds">'</span>head<span class="pl-pds">'</span></span>, <span class="pl-c1">0</span>)<span class="pl-k">-&gt;</span><span class="pl-smi">innertext</span> <span class="pl-k">.=</span> <span class="pl-s"><span class="pl-pds">'</span>&lt;meta name="robots" content="<span class="pl-pds">'</span></span> <span class="pl-k">.</span> <span class="pl-smi">$meta_robots</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">'</span>" /&gt;<span class="pl-pds">'</span></span>;</span>
<span class="pl-s1"></span>
<span class="pl-s1">            <span class="pl-k">return</span> <span class="pl-smi">$html_dom</span>;</span>
<span class="pl-s1">        }</span>
<span class="pl-s1"></span>
<span class="pl-s1">        <span class="pl-k">return</span> <span class="pl-smi">$html</span>;</span>
<span class="pl-s1">    }</span></pre></div>

<hr>
