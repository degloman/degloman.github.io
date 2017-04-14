---
layout: default
title: Catalog events
---
<h3>
<a id="product" class="anchor" href="#product" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>product</h3>

<h4>
<a id="1-viewproductcategorybefore" class="anchor" href="#1-viewproductcategorybefore" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>1. view/product/category/before</h4>

<h5>
<a id="category_data" class="anchor" href="#category_data" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>category_data()</h5>

<p><em>modify the data that will be rendered to the <code>category.tpl</code></em></p>

<ul>
<li>
<strong>method:</strong> <code>public function category_data($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array( ... )</code>
</li>
<li>
<strong>output:</strong> <code>$data = array( ... )</code>
</li>
</ul>

<h4>
<a id="2-viewtemplateproductcategoryafter" class="anchor" href="#2-viewtemplateproductcategoryafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>2. view/*/template/product/category/after</h4>

<h5>
<a id="category_html" class="anchor" href="#category_html" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>category_html()</h5>

<p><em>modify the HTML of the <code>category.tpl</code> before bowser renders it</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function category_html($output)</code>
</li>
<li>
<strong>parameters:</strong> <code>(string) $output</code>
</li>
<li>
<strong>output:</strong> <code>(string) $output</code>
</li>
</ul>

<h4>
<a id="3-viewproductproductbefore" class="anchor" href="#3-viewproductproductbefore" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>3. view/product/product/before</h4>

<h5>
<a id="product_data" class="anchor" href="#product_data" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>product_data()</h5>

<p><em>modify the data that will be rendered to the <code>product.tpl</code></em></p>

<ul>
<li>
<strong>method:</strong> <code>public function product_data($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array( ... )</code>
</li>
<li>
<strong>output:</strong> <code>$data = array( ... )</code>
</li>
</ul>

<h4>
<a id="4-viewtemplateproductproductafter" class="anchor" href="#4-viewtemplateproductproductafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>4. view/*/template/product/product/after</h4>

<h5>
<a id="product_html" class="anchor" href="#product_html" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>product_html()</h5>

<p><em>modify the HTML of the <code>product.tpl</code> before bowser renders it</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function product_html($output)</code>
</li>
<li>
<strong>parameters:</strong> <code>(string) $output</code>
</li>
<li>
<strong>output:</strong> <code>(string) $output</code>
</li>
</ul>

<h4>
<a id="5-viewproductmanufacturer_infobefore" class="anchor" href="#5-viewproductmanufacturer_infobefore" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>5. view/product/manufacturer_info/before</h4>

<h5>
<a id="manufacturer_info_data" class="anchor" href="#manufacturer_info_data" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>manufacturer_info_data()</h5>

<p><em>modify the data that will be rendered to the <code>manufacturer_info.tpl</code></em></p>

<ul>
<li>
<strong>method:</strong> <code>public function manufacturer_info_data($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array( ... )</code>
</li>
<li>
<strong>output:</strong> <code>$data = array( ... )</code>
</li>
</ul>

<h4>
<a id="6-viewtemplateproductmanufacturer_infoafter" class="anchor" href="#6-viewtemplateproductmanufacturer_infoafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>6. view/*/template/product/manufacturer_info/after</h4>

<h5>
<a id="manufacturer_info_html" class="anchor" href="#manufacturer_info_html" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>manufacturer_info_html()</h5>

<p><em>modify the HTML of the <code>manufacturer_info.tpl</code> before bowser renders it</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function manufacturer_info_html($output)</code>
</li>
<li>
<strong>parameters:</strong> <code>(string) $output</code>
</li>
<li>
<strong>output:</strong> <code>(string) $output</code>
</li>
</ul>

