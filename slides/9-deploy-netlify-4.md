### Use the Netlify Node CLI

<section>
	<pre><code data-trim>
#addin "Cake.Npm"
// ...
Task("Deploy")
    .Does(() =>
    {
        // Add NETLIFY_TOKEN to your enviornment variables
        string token = EnvironmentVariable("NETLIFY_TOKEN");
        if(string.IsNullOrEmpty(token))
        {
            throw new Exception("Could not get NETLIFY_TOKEN environment variable");
        }
        // Install the Netlify CLI locally and then run the deploy command
        Npm.Install(x => x.Package("netlify-cli"));
        StartProcess(
            MakeAbsolute(File("./node_modules/.bin/netlify.cmd")), 
            "deploy -p output -s yoursite -t " + token);
    });
 	</code></pre>
 </section>