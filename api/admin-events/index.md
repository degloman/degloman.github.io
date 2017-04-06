---
layout: default
title: Admin Events
---
<h2>
<a id="admin-list-of-events-and-their-methods" class="anchor" href="#admin-list-of-events-and-their-methods" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>Admin list of events and their methods</h2>

<blockquote>
<h4>
<a id="how-to-use-it" class="anchor" href="#how-to-use-it" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>How to use it?</h4>

<p>This is how you should understand the following events:</p>

<p><code>admin/view/common/column_left/before</code> is called before the <code>column_left.tpl</code> is rendered to the screen.</p>

<p>To subsribe you will need to add the method <code>public function menu($menu_data)</code> to your controller file <code>admin/controller/extension/module/d_seo_module_myfeature.php</code> with a parameter <code>$menu_data</code></p>

<p>You will populate <code>$menu_data</code> with your menu item <code>array('name' =&gt; ..., 'href' =&gt; ..., 'children' =&gt; ...)</code> and <code>return $menu_data;</code></p>
</blockquote>