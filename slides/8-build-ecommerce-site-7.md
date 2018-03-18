### products.cshtml

<section>
	<pre><code data-trim>
<h2>@Metadata["Name"]</h2>
<div class="product-details">
    <img src="@Metadata["Image"]" width="150px" class="thumbnail"/>
    <div class="product-description">
        <p>
            @Html.Raw(Metadata["Product"])
        </p>
        <button class="snipcart-add-item"
                data-item-name="@Metadata["Name"]"
                data-item-description="@Metadata["Description"]"
                data-item-id="@Metadata["Sku"]"
                data-item-image="@Metadata["Image"]"
                data-item-price="@Metadata["Price"]">
            Buy it for @Metadata["Price"] $
        </button>
    </div>
</div>
 	</code></pre>
 </section>