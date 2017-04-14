---
layout: default
title: information
---
<h3>
<a id="information" class="anchor" href="#information" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>information</h3>

<h4>
<a id="1-viewinformationinformationbefore" class="anchor" href="#1-viewinformationinformationbefore" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>1. view/information/information/before</h4>

<h5>
<a id="information_data" class="anchor" href="#information_data" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>information_data()</h5>

<p><em>modify the data that will be rendered to the <code>information.tpl</code></em></p>

<ul>
<li>
<strong>method:</strong> <code>public function information_data($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array( ... )</code>
</li>
<li>
<strong>output:</strong> <code>$data = array( ... )</code>
</li>
</ul>

<h4>
<a id="2-viewtemplateinformationinformationafter" class="anchor" href="#2-viewtemplateinformationinformationafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>2. view/*/template/information/information/after</h4>

<h5>
<a id="information_html" class="anchor" href="#information_html" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>information_html()</h5>

<p><em>modify the HTML of the <code>information.tpl</code> before bowser renders it</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function information_html($output)</code>
</li>
<li>
<strong>parameters:</strong> <code>(string) $output</code>
</li>
<li>
<strong>output:</strong> <code>(string) $output</code>
</li>
</ul>

