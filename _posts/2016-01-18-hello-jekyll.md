## Why A Blog?

Figured this would be the best way to share my own thoughts, with both friends and strangers alike. A self fufilling exercise in keeping track of myself.

## Why Jekyll

I wanted a lightweight system that didn't require me to pay for anything. As I'm still not 100% committed to blogging consistently. Github pages offers Jekyll, and it seems like a way to write in Markdown, have a way to keep source control, as well as serve any blog posts quickly and easily.

## How to setup

Basically, make yourself a github pages repository by naming the repository the format of:

~~~~
<username>.github.io
~~~~

Once you have a repository, lets create the Hello World of Jekyll!

Literally just create an index.html with the words Hello World. Push it to github and then navigate to:

~~~
<username>.github.io
~~~

in your address bar. And voila. You'll see your Hello World page.

This isn't the prettiest blog we have right now. But thats where themes comes in!

## Theming

Now you'll want to add a theme just to get a quick start and have a nice and beautiful looking blog without any hassle. You can always customize later. My thoughts are get it done now, or else you'll never get it done later.

So an easy way to add a theme is to use something like [lanyon](https://github.com/poole/lanyon). A simple nice theme that'll satisfy your first needs, before you go and customize everything yourself.

Go to that link, and just download all the files. Then dump all the files into your own github repository.

Normally all you would need to do now is to Serve your Jekyll blog with

~~~
jekyll serve
~~~

But you'll run into some errors as lanyon was build for Jekyll 2.5, and we are now on Jekyll 3

### Upgrading Lanyon to Jekyll 3

Theres 3 main things you need to address to convert Lanyon to Jekyll 3.

#### 1. 

~~~
 Deprecation: You appear to have pagination turned on, but you haven't included the `jekyll-paginate` gem. Ensure you have `gems: [jekyll-paginate]` in your configuration file.
~~~
You'll need to install the paginate gem by running in the command line:
~~~
gem install jekyll-paginate
~~~

Then add the jekyll-paginate into your _config.yml

~~~
gems: [jekyll-paginate]
~~~

#### 2. 

~~~
 Dependency Error: Yikes! It looks like you don't have redcarpet or one of its dependencies installed. In order to use Jekyll as currently configured, you'll need to install this gem. The full error message from Ruby is: 'cannot load such file -- redcarpet' If you run into trouble, you can find helpful resources at http://jekyllrb.com/help/!
~~~

For this issue you need to switch to Markdown in the format of Kramdown.

Install kramdown by executing in the command Line:
~~~
gem install kramdown
~~~

Change the _config.yml from redcarpet to:
~~~
kramdown:
  input: GFM
~~~


#### 3. 

~~~
Deprecation: The 'pygments' configuration option has been renamed to 'highlighter'. Please update your config file accordingly. The allowed values are 'rouge', 'pygments' or null.
~~~

Pygments is no longer supported in Jekyll 3.

I personally use rouge so just add to the _config.yml:
~~~
highlighter: rouge
~~~

## Serving Jekyll

Now that all of that is out of the way. It's time to see your new blog! And tihs time lets do it on a local machine, so you can test and customize it before showing it to the world.

In the command line type:

~~~
jekyll serve -w
~~~

Then navigate in your web browser to:
~~~
localhost:4000
~~~

Which should contain your new blog.

Make changes in your posts and see them update immediately. No more waiting for the server to load before seeing the changes you've made. This is all done through the -w command in jekyll serve.

Once your ready, you can publish the blog out there with a simple push to the git repository.

With a system like this it feels much easier to actually write about stuff, I can just write anywhere in Markdown, and publish to my blog by pushing to the git repository from anywhere with access.




