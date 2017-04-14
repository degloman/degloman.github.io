---
layout: default
title: Catalog events
---
<h2>
<a id="catalog-list-of-events-and-their-methods" class="anchor" href="#catalog-list-of-events-and-their-methods" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>Catalog list of events and their methods</h2>

<blockquote>
<h4>
<a id="how-to-use-it-1" class="anchor" href="#how-to-use-it-1" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>How to use it?</h4>

<p>For the frontend you have two basic events:
-<code>data</code> (before event - here you modify the data array)</p>

<ul>
<li>
<code>html</code> (after event - here you modify the HTML).</li>
</ul>
</blockquote>

<ol>
<li>
<code>view/common/home/before</code> is called before the <code>home.tpl</code> is rendered to the screen.</li>
<li>To subsribe you will need to add the method <code>public function home_data($data)</code> to your controller file <code>catalog/controller/extension/module/d_seo_module_myfeature.php</code> with a parameter <code>$data</code>
</li>
<li> You will modify <code>$data</code> accordingly and <code>return $data;</code>
</li>
</ol>
