### Add Products to our Pipeline

<section>
	<pre><code data-trim data-noescape>
Pipelines.Add("Products",
     ReadFiles("products/*.md"),
     // Read all markdown files in the "products" directory
     FrontMatter(Yaml()),
     // Load any frontmatter and parse it as YAML markup
     Markdown(),
     // Render the markdown content
     Meta("Product", @doc.Content),
     // Move the markdown content to metadata
     Meta("ProductFile", string.Format(@"products\{0}.html", ((string)@doc["Title"]).ToLower().Replace(' ', '-'))),  // Use the product title as the filename and save it in metadata so we can use it in links later
     Merge(
         ReadFiles("products/products.cshtml")
         // Load the Razor product page template
     ),
     Razor(),
     // Compile and render the page template
     WriteFiles((string)@doc["ProductFile"])  
     // Write the product file
 );
	</code></pre>
</section>
