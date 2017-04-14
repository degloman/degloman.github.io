---
layout: default
title: Admin Events
---
<h3>
<a id="catalog" class="anchor" href="#catalog" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>catalog</h3>

<h4>
<a id="1-viewcatalogcategory_formafter" class="anchor" href="#1-viewcatalogcategory_formafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>1. view/catalog/category_form/after</h4>

<h5>
<a id="category_form_tab_general" class="anchor" href="#category_form_tab_general" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>category_form_tab_general()</h5>

<p><em>modify the HTML output of category form. You simply return an HTML of the input or anything else that you want to place into the form based on the tab</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function category_form_tab_general()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="category_form_tab_general_language" class="anchor" href="#category_form_tab_general_language" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>category_form_tab_general_language()</h5>

<p><em>You can add html to a language tab, by using the <code>$language_id</code></em></p>

<ul>
<li>
<strong>method:</strong> <code>public function category_form_tab_general_language($language_id)</code>
</li>
<li>
<strong>parameters:</strong> <code>$language_id</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="category_form_tab_data" class="anchor" href="#category_form_tab_data" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>category_form_tab_data()</h5>

<ul>
<li>
<strong>method:</strong> <code>public function category_form_tab_data()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="category_form_tab_seo" class="anchor" href="#category_form_tab_seo" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>category_form_tab_seo()</h5>

<p><em>this is a custom seo tab. It will be visible if your module adds html to it.</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function category_form_tab_seo()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="category_form_style" class="anchor" href="#category_form_style" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>category_form_style()</h5>

<p><em>This is a style input. You can use this for adding CSS to the form. Yet we recomend using he default <code>$this-&gt;document-&gt;addStyle($href, $rel = 'stylesheet', $media = 'screen')</code>;</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function category_form_style()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="category_form_script" class="anchor" href="#category_form_script" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>category_form_script()</h5>

<p><em>Add js scripts to the form</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function category_form_script()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h4>
<a id="2-modelcatalogcategoryaddcategoryafter" class="anchor" href="#2-modelcatalogcategoryaddcategoryafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>2. model/catalog/category/addCategory/after</h4>

<h5>
<a id="category_form_add" class="anchor" href="#category_form_add" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>category_form_add()</h5>

<p><em>after a new category has been added, you can preform your own actions like update cache</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function category_form_add($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array( 'category_id' =&gt; ...);</code>
</li>
<li>
<strong>output:</strong> <code>none</code>
</li>
</ul>

<p>Example:
<strong>admin/controller/extension/module/d_seo_module_myfeature.php</strong></p>

<div class="highlight highlight-text-html-php"><pre><span class="pl-s1"><span class="pl-k">public</span> <span class="pl-k">function</span> <span class="pl-en">category_form_add</span>(<span class="pl-smi">$data</span>) {</span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>model(<span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1"></span>
<span class="pl-s1">    <span class="pl-c">//custom model method for updating category cache (it is up to you to implement it.</span></span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">model_extension_module_d_seo_module_myfeature</span><span class="pl-k">-&gt;</span>updateCategoryCache(<span class="pl-smi">$data</span>);</span>
<span class="pl-s1">}</span>
<span class="pl-s1"></span></pre></div>

<h4>
<a id="3-modelcatalogcategoryeditcategoryafter" class="anchor" href="#3-modelcatalogcategoryeditcategoryafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>3. model/catalog/category/editCategory/after</h4>

<h5>
<a id="category_form_edit" class="anchor" href="#category_form_edit" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>category_form_edit()</h5>

<p><em>after a new category has been edited, you can preform your own actions like update cache</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function category_form_edit($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array( 'category_id' =&gt; ...);</code>
</li>
<li>
<strong>output:</strong> <code>none</code>
</li>
</ul>

<h4>
<a id="4-viewcatalogproduct_formafter" class="anchor" href="#4-viewcatalogproduct_formafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>4. view/catalog/product_form/after</h4>

<h5>
<a id="product_form_tab_general" class="anchor" href="#product_form_tab_general" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>product_form_tab_general()</h5>

<p><em>modify the HTML output of category form. You simply return an HTML of the input or anything else that you want to place into the form based on the tab</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function product_form_tab_general()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="product_form_tab_general_language" class="anchor" href="#product_form_tab_general_language" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>product_form_tab_general_language()</h5>

<p><em>You can add html to a language tab, by using the <code>$language_id</code></em></p>

<ul>
<li>
<strong>method:</strong> <code>public function product_form_tab_general_language($language_id)</code>
</li>
<li>
<strong>parameters:</strong> <code>$language_id</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="product_form_tab_data" class="anchor" href="#product_form_tab_data" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>product_form_tab_data()</h5>

<ul>
<li>
<strong>method:</strong> <code>public function product_form_tab_data()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="product_form_tab_links" class="anchor" href="#product_form_tab_links" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>product_form_tab_links()</h5>

<ul>
<li>
<strong>method:</strong> <code>public function product_form_tab_links()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="product_form_tab_seo" class="anchor" href="#product_form_tab_seo" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>product_form_tab_seo()</h5>

<p><em>This is a custom seo tab. It will be visible if your module adds html to it.</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function product_form_tab_seo()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="product_form_style" class="anchor" href="#product_form_style" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>product_form_style()</h5>

<p><em>This is a style input. You can use this for adding CSS to the form. We recommended using the default <code>$this-&gt;document-&gt;addStyle($href, $rel = 'stylesheet', $media = 'screen')</code>;</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function product_form_style()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="product_form_script" class="anchor" href="#product_form_script" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>product_form_script()</h5>

<p><em>Add js scripts to the form</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function product_form_script()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h4>
<a id="5-modelcatalogproductaddproductafter" class="anchor" href="#5-modelcatalogproductaddproductafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>5. model/catalog/product/addProduct/after</h4>

<h5>
<a id="product_form_add" class="anchor" href="#product_form_add" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>product_form_add()</h5>

<p><em>after a new product has been added, you can preform your own actions like generate empty seo url</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function product_form_add($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array( 'product_id' =&gt; ... )</code>
</li>
<li>
<strong>output:</strong> <code>none</code>
</li>
</ul>

<h4>
<a id="6-modelcatalogproducteditproductafter" class="anchor" href="#6-modelcatalogproducteditproductafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>6. model/catalog/product/editProduct/after</h4>

<h5>
<a id="product_form_edit" class="anchor" href="#product_form_edit" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>product_form_edit()</h5>

<p><em>after a product has been edited, you can preform your own actions like update product url cache</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function product_form_edit($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array( 'product_id' =&gt; ... )</code>
</li>
<li>
<strong>output:</strong> <code>none</code>
</li>
</ul>

<h4>
<a id="7-viewcatalogmanufacturer_formafter" class="anchor" href="#7-viewcatalogmanufacturer_formafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>7. view/catalog/manufacturer_form/after</h4>

<h5>
<a id="manufacturer_form_tab_general" class="anchor" href="#manufacturer_form_tab_general" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>manufacturer_form_tab_general()</h5>

<p><em>modify the HTML output of category form. You simply return an HTML of the input or anything else that you want to place into the form based on the tab</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function manufacturer_form_tab_general()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="manufacturer_form_tab_general_language" class="anchor" href="#manufacturer_form_tab_general_language" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>manufacturer_form_tab_general_language()</h5>

<p><em>You can add html to a language tab, by using the <code>$language_id</code></em></p>

<ul>
<li>
<strong>method:</strong> <code>public function manufacturer_form_tab_general_language($language_id)</code>
</li>
<li>
<strong>parameters:</strong> <code>$language_id</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="manufacturer_form_tab_data" class="anchor" href="#manufacturer_form_tab_data" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>manufacturer_form_tab_data()</h5>

<ul>
<li>
<strong>method:</strong> <code>public function manufacturer_form_tab_data()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="manufacturer_form_tab_seo" class="anchor" href="#manufacturer_form_tab_seo" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>manufacturer_form_tab_seo()</h5>

<p><em>this is a custom seo tab. It will be visible if your module adds html to it.</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function manufacturer_form_tab_seo()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="manufacturer_form_style" class="anchor" href="#manufacturer_form_style" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>manufacturer_form_style()</h5>

<p><em>This is a style input. You can use this for adding CSS to the form. We recommended using the default <code>$this-&gt;document-&gt;addStyle($href, $rel = 'stylesheet', $media = 'screen')</code>;</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function manufacturer_form_style()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="manufacturer_form_script" class="anchor" href="#manufacturer_form_script" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>manufacturer_form_script()</h5>

<p><em>Add js scripts to the form</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function manufacturer_form_script()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h4>
<a id="8-modelcatalogmanufactureraddmanufacturerafter" class="anchor" href="#8-modelcatalogmanufactureraddmanufacturerafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>8. model/catalog/manufacturer/addManufacturer/after</h4>

<h5>
<a id="manufacturer_form_add" class="anchor" href="#manufacturer_form_add" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>manufacturer_form_add()</h5>

<p><em>after a new product has been added, you can preform your own actions like add manufacturer description</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function manufacturer_form_add($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array('manufacturer_id' =&gt; ... )</code>
</li>
<li>
<strong>output:</strong> <code>none</code>
</li>
</ul>

<p>Example:
<strong>controller/extension/module/d_seo_module_myfeature.php</strong></p>

<div class="highlight highlight-text-html-php"><pre><span class="pl-s1"><span class="pl-k">public</span> <span class="pl-k">function</span> <span class="pl-en">manufacturer_form_add</span>(<span class="pl-smi">$data</span>) {</span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">load</span><span class="pl-k">-&gt;</span>model(<span class="pl-s"><span class="pl-pds">'</span>extension/module/d_seo_module_myfeature<span class="pl-pds">'</span></span>);</span>
<span class="pl-s1">    <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">model_extension_module_d_seo_module_myfeature</span><span class="pl-k">-&gt;</span>addManufacturerDescription(<span class="pl-smi">$data</span>);</span>
<span class="pl-s1">}</span></pre></div>

<p><strong>model/extension/module/d_seo_module_myfeature.php</strong></p>

<div class="highlight highlight-text-html-php"><pre><span class="pl-s1"><span class="pl-k">public</span> <span class="pl-k">function</span> <span class="pl-en">addManufacturerDescription</span>(<span class="pl-smi">$data</span>) {</span>
<span class="pl-s1">    <span class="pl-k">foreach</span> (<span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>manufacturer_description<span class="pl-pds">'</span></span>] <span class="pl-k">as</span> <span class="pl-smi">$language_id</span> <span class="pl-k">=&gt;</span> <span class="pl-smi">$manufacturer_description</span>) {</span>
<span class="pl-s1">        <span class="pl-smi">$this</span><span class="pl-k">-&gt;</span><span class="pl-smi">db</span><span class="pl-k">-&gt;</span>query(<span class="pl-s"><span class="pl-pds">"</span><span class="pl-s1"><span class="pl-k">INSERT INTO</span> </span><span class="pl-pds">"</span></span> <span class="pl-k">.</span> <span class="pl-c1">DB_PREFIX</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">"</span>manufacturer_description SET manufacturer_id = '<span class="pl-pds">"</span></span> <span class="pl-k">.</span> (<span class="pl-k">int</span>)<span class="pl-smi">$data</span>[<span class="pl-s"><span class="pl-pds">'</span>manufacturer_id<span class="pl-pds">'</span></span>] <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">"</span>', language_id = '<span class="pl-pds">"</span></span> <span class="pl-k">.</span> (<span class="pl-k">int</span>)<span class="pl-smi">$language_id</span> <span class="pl-k">.</span> <span class="pl-s"><span class="pl-pds">"</span>'<span class="pl-pds">"</span></span>);</span>
<span class="pl-s1">    }</span>
<span class="pl-s1">}</span></pre></div>

<h4>
<a id="9-modelcatalogmanufacturereditmanufacturerafter" class="anchor" href="#9-modelcatalogmanufacturereditmanufacturerafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>9. model/catalog/manufacturer/editManufacturer/after</h4>

<h5>
<a id="manufacturer_form_edit" class="anchor" href="#manufacturer_form_edit" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>manufacturer_form_edit()</h5>

<p><em>after a new product has been added, you can preform your own actions like generate seo url</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function manufacturer_form_edit($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array('manufacturer_id' =&gt; ... )</code>
</li>
<li>
<strong>output:</strong> <code>none</code>
</li>
</ul>

<h4>
<a id="10-viewcataloginformation_formafter" class="anchor" href="#10-viewcataloginformation_formafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>10. view/catalog/information_form/after</h4>

<h5>
<a id="information_form_tab_general" class="anchor" href="#information_form_tab_general" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>information_form_tab_general()</h5>

<p><em>modify the HTML output of category form. You simply return an HTML of the input or anything else that you want to place into the form based on the tab</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function information_form_tab_general()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="information_form_tab_general_language" class="anchor" href="#information_form_tab_general_language" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>information_form_tab_general_language()</h5>

<p><em>You can add html to a language tab, by using the <code>$language_id</code></em></p>

<ul>
<li>
<strong>method:</strong> <code>public function information_form_tab_general_language($language_id)</code>
</li>
<li>
<strong>parameters:</strong> <code>$language_id</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="information_form_tab_data" class="anchor" href="#information_form_tab_data" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>information_form_tab_data()</h5>

<ul>
<li>
<strong>method:</strong> <code>public function information_form_tab_data()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="information_form_tab_seo" class="anchor" href="#information_form_tab_seo" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>information_form_tab_seo()</h5>

<p><em>this is a custom seo tab. It will be visible if your module adds html to it.</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function information_form_tab_seo()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="information_form_style" class="anchor" href="#information_form_style" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>information_form_style()</h5>

<p><em>This is a style input. You can use this for adding CSS to the form. We recommended using the default <code>$this-&gt;document-&gt;addStyle($href, $rel = 'stylesheet', $media = 'screen')</code>;</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function information_form_style()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h5>
<a id="information_form_script" class="anchor" href="#information_form_script" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>information_form_script()</h5>

<p><em>Add js scripts to the form</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function information_form_script()</code>
</li>
<li>
<strong>parameters:</strong> <code>none</code>
</li>
<li>
<strong>output:</strong> <code>html</code>
</li>
</ul>

<h4>
<a id="11-modelcataloginformationaddinformationafter" class="anchor" href="#11-modelcataloginformationaddinformationafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>11. model/catalog/information/addInformation/after</h4>

<h5>
<a id="information_add_after" class="anchor" href="#information_add_after" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>information_add_after()</h5>

<p><em>after a product has been edited, you can preform your own actions like update product url cache</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function information_add_after($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array( 'information_id' =&gt; ... )</code>
</li>
<li>
<strong>output:</strong> <code>none</code>
</li>
</ul>

<h4>
<a id="12-modelcataloginformationeditinformationafter" class="anchor" href="#12-modelcataloginformationeditinformationafter" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>12. model/catalog/information/editInformation/after</h4>

<h5>
<a id="information_edit_after" class="anchor" href="#information_edit_after" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>information_edit_after()</h5>

<p><em>after a product has been edited, you can preform your own actions like update product url cache</em></p>

<ul>
<li>
<strong>method:</strong> <code>public function information_edit_after($data)</code>
</li>
<li>
<strong>parameters:</strong> <code>$data = array( 'information_id' =&gt; ... )</code>
</li>
<li>
<strong>output:</strong> <code>none</code>
</li>
</ul>

<hr>
