### home.cshtml

<section>
	<pre><code data-trim>
          <div class="row">
            @foreach(var doc in Documents["Products"])
            {
              <a href="@doc["ProductFile"]">
                <div class="col-lg-4 col-md-6 mb-4">
                  <div class="card h-100">
                    <a href="#"><img src="@doc["Image"]" width="150px" class="thumbnail"/></a>
                    <div class="card-body">
                      <h4 class="card-title">
                        <a href="#"><p>@doc["Title"]</p></a>
                      </h4>
                      <h5>$@doc["Price"]</h5>
                      <p class="card-text">@doc["Description"]</p>
                    </div>
                    <div class="card-footer">
                      <small class="text-muted">&#9733; &#9733; &#9733; &#9733; &#9734;</small>
                    </div>
                  </div>
                </div>
              </a>
            }
          </div><!-- /.row -->
 	</code></pre>
 </section>