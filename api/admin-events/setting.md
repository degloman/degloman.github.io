---
layout: default
title: Admin Events
---
<h3>
<a id="setting" class="anchor" href="#setting" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>setting</h3>

<h4>
<a id="1-viewsettingsettingafter--viewsettingstore_formafter" class="anchor" href="#1-viewsettingsettingafter--viewsettingstore_formafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>1. view/setting/setting/after &amp; view/setting/store_form/after</h4>

<h5>
<a id="setting_tab_general" class="anchor" href="#setting_tab_general" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>setting_tab_general()</h5>

<p><em>modify the output of store setting form and new store create form. You simply return an HTML of the input or anything else that you want to place into the form and tab</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function setting_tab_general()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<p>Exemple
<strong>admin/controller/extension/module/d_seo_module_myfeature.php</strong></p>

<div class="highlight highlight-text-html-php"><pre><span class="pl-s1"><span class="pl-k">public</span> <span class="pl-k">function</span> <span class="pl-en">setting_tab_general</span>() {</span>
<span class="pl-s1">    <span class="pl-c">//load models and language files</span></span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>language(<span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>model(<span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-c">//get language data</span></span>
<span class="pl-s1">    <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>entry_myfeature<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">language</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>entry_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">    <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>help_myfeature<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">language</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>help_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-c">//load config file for module d_seo_module_myfeature and fetch default config values.</span></span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>load(<span class="pl-s"><span class="pl-pds">'</span>d_seo_module_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">    <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>setting<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> (<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>d_seo_module_myfeature_setting<span class="pl-pds">'</span></span>)) ? <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>d_seo_module_myfeature_setting<span class="pl-pds">'</span></span>) : <span class="pl-c1">array</span>();</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-c">//add config_myfeature value to the $data for settings general tab</span></span>
<span class="pl-s1">    <span class="pl-k">if</span> (<span class="pl-c1">isset</span>(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">request</span><span class="pl-k">-&gt;</span><span class="pl-smi">post</span>[<span class="pl-s"><span class="pl-pds">'</span>config_myfeature<span class="pl-pds">'</span></span>])) {</span>
<span class="pl-s1">        <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>config_myfeature<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">request</span><span class="pl-k">-&gt;</span><span class="pl-smi">post</span>[<span class="pl-s"><span class="pl-pds">'</span>config_myfeature<span class="pl-pds">'</span></span>];</span>
<span class="pl-s1">    } <span class="pl-k">else</span> {</span>
<span class="pl-s1">        <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>config_myfeature<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">    }</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-c">//render the $data with the setting_tab_general_language.tpl. the HTML will be returned and added to the final HTML inside the Store Setting General tab.                       </span></span>
<span class="pl-s1">    <span class="pl-k">return</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>view(<span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature/setting_tab_general.tpl<span class="pl-pds">'</span></span>, <span class="pl-smi">$data</span>);</span>
<span class="pl-s1">}</span></pre></div>

<h5>
<a id="setting_tab_general_language" class="anchor" href="#setting_tab_general_language" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>setting_tab_general_language()</h5>

<p><em>You can add html to a language tab, by using the <code>$language_id</code></em></p>

<ul>
<li>
<strong>method:</strong> <code>public function setting_tab_general_language($language_id)</code>
</li>
<li>
<strong>parameters:</strong> <code>$language_id</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<p>Exemple
<strong>admin/controller/extension/module/d_seo_module_myfeature.php</strong></p>

<div class="highlight highlight-text-html-php"><pre><span class="pl-s1"><span class="pl-k">public</span> <span class="pl-k">function</span> <span class="pl-en">setting_tab_general_language</span>(<span class="pl-smi">$language_id</span>) {</span>
<span class="pl-s1">    <span class="pl-c">//load models and language files</span></span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>language(<span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>model(<span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-c">//get required parameters</span></span>
<span class="pl-s1">    <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>language_id<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> <span class="pl-smi">$language_id</span>;</span>
<span class="pl-s1">    <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>languages<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">model_extension_module_d_seo_module_myfeature</span><span class="pl-k">-&gt;</span>getLanguages();</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-c">//get language data</span></span>
<span class="pl-s1">    <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>entry_myfeature<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">language</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>entry_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">    <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>help_myfeature<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">language</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>help_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-c">//load config file for module d_seo_module_myfeature and fetch default config values.</span></span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>load(<span class="pl-s"><span class="pl-pds">'</span>d_seo_module_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">    <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>setting<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> (<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>d_seo_module_myfeature_setting<span class="pl-pds">'</span></span>)) ? <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>d_seo_module_myfeature_setting<span class="pl-pds">'</span></span>) : <span class="pl-c1">array</span>();</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-c">//add config_myfeature value to the $data for settings general tab</span></span>
<span class="pl-s1">    <span class="pl-k">if</span> (<span class="pl-c1">isset</span>(<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">request</span><span class="pl-k">-&gt;</span><span class="pl-smi">post</span>[<span class="pl-s"><span class="pl-pds">'</span>config_myfeature<span class="pl-pds">'</span></span>])) {</span>
<span class="pl-s1">        <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>config_myfeature<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">request</span><span class="pl-k">-&gt;</span><span class="pl-smi">post</span>[<span class="pl-s"><span class="pl-pds">'</span>config_myfeature<span class="pl-pds">'</span></span>];</span>
<span class="pl-s1">    } <span class="pl-k">elseif</span> (<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_myfeature<span class="pl-pds">'</span></span>)) {</span>
<span class="pl-s1">        <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>config_myfeature<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">    } <span class="pl-k">else</span> {</span>
<span class="pl-s1">        <span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>config_myfeature<span class="pl-pds">'</span></span>][<span class="pl-smi">$language_id</span>][<span class="pl-s"><span class="pl-pds">'</span>myfeature_title<span class="pl-pds">'</span></span>] <span class="pl-k">=</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">config</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>config_myfeature_title<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">    }</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-c">//render the $data with the setting_tab_general_language.tpl. the HTML will be returned and added to the final HTML inside the Store Setting General tab.                       </span></span>
<span class="pl-s1">    <span class="pl-k">return</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>view(<span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature/setting_tab_general_language.tpl<span class="pl-pds">'</span></span>, <span class="pl-smi">$data</span>);</span>
<span class="pl-s1">}</span></pre></div>

<h5>
<a id="setting_tab_store" class="anchor" href="#setting_tab_store" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>setting_tab_store()</h5>

<ul>
<li>
<strong>method:</strong> <code>public function setting_tab_store()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="setting_tab_local" class="anchor" href="#setting_tab_local" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>setting_tab_local()</h5>

<ul>
<li>
<strong>method:</strong> <code>public function setting_tab_local()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="setting_tab_option" class="anchor" href="#setting_tab_option" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>setting_tab_option()</h5>

<ul>
<li>
<strong>method:</strong> <code>public function setting_tab_option()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="setting_tab_seo" class="anchor" href="#setting_tab_seo" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>setting_tab_seo()</h5>

<p><em>this is a custom seo tab. It will be visible if your module adds html to it.</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function setting_tab_seo()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="setting_style" class="anchor" href="#setting_style" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>setting_style()</h5>

<p><em>This is a style input. You can use this for adding CSS to the form. Yet we recommend using he default <code>$this-&gt;document-&gt;addStyle($href, $rel = 'stylesheet', $media = 'screen')</code>;</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function setting_style()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="setting_script" class="anchor" href="#setting_script" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>setting_script()</h5>

<p><em>Add js scripts to the form</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function setting_script()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>