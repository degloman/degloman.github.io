---
layout: default
title: Admin Events
---
<h3>
<a id="common" class="anchor" href="#common" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>common</h3>

<h4>
<a id="1-viewcommoncolumn_leftbefore" class="anchor" href="#1-viewcommoncolumn_leftbefore" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>1. view/common/column_left/before</h4>

<h5>
<a id="menu" class="anchor" href="#menu" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>menu()</h5>

<p><em>add an item in admin to seo menu. You will recieve the menu array, only to add your own menu item and return the menu array</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function menu($menu_data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$menu_data[] = array( 'name' =&gt; ..., 'href' =&gt; ..., 'children' =&gt; ...);</code>
</li>
<li>
<strong>return:</strong> <code>$menu_data = array()</code>
</li>
</ul>

<p>Exemple</p>

<div class="highlight highlight-text-html-php"><pre><span class="pl-s1"><span class="pl-k">public</span> <span class="pl-k">function</span> <span class="pl-en">menu</span>(<span class="pl-smi">$menu_data</span>) {</span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>language(<span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-k">if</span> (<span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">user</span><span class="pl-k">-&gt;</span>hasPermission(<span class="pl-s"><span class="pl-pds">'</span>access<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature<span class="pl-pds">'</span></span>)) {</span>
<span class="pl-s1">        <span class="pl-smi">$menu_data</span>[] <span class="pl-k">=</span> <span class="pl-c1">array</span>(</span>
<span class="pl-s1">            <span class="pl-s"><span class="pl-pds">'</span>name<span class="pl-pds">'</span></span>     <span class="pl-k">=&gt;</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">language</span><span class="pl-k">-&gt;</span>get(<span class="pl-s"><span class="pl-pds">'</span>heading_title_main<span class="pl-pds">'</span></span>),</span>
<span class="pl-s1">            <span class="pl-s"><span class="pl-pds">'</span>href<span class="pl-pds">'</span></span>     <span class="pl-k">=&gt;</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">url</span><span class="pl-k">-&gt;</span>link(<span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature<span class="pl-pds">'</span></span>, <span class="pl-s"><span class="pl-pds">'</span>token=<span class="pl-pds">'</span></span> <span class="pl-k">.</span> <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">session</span><span class="pl-k">-&gt;</span><span class="pl-smi">data</span>[<span class="pl-s"><span class="pl-pds">'</span>token<span class="pl-pds">'</span></span>], <span class="pl-c1">true</span>),</span>
<span class="pl-s1">            <span class="pl-s"><span class="pl-pds">'</span>children<span class="pl-pds">'</span></span> <span class="pl-k">=&gt;</span> <span class="pl-c1">array</span>()       </span>
<span class="pl-s1">        );</span>
<span class="pl-s1">    }</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-k">return</span> <span class="pl-smi">$menu_data</span>;</span>
<span class="pl-s1">}</span></pre></div>

<hr>