Laravel is great, I've been using it for the past couple of months and love it. Typically, I have never really been a fan of PHP but Laravel has changed my opinion on the language.

Part of what makes Laravel such a brilliant framework is the amount of helpful methods that it provides that are built into the framework. Most of these methods make commons tasks in web development very simple. Creating slugs is a common task which I'm sure most developers wish they could just write one line of code and it would be done for them, well using Laravel's `slug()` method this can be achieved easily.

# Set the scene

So, we've got a blog that allows the user of the blog, to create a blog post by filling in a simple form. A typical blog post consists of a title, description and the blog content. The issue is here that the title can have spaces in, and thats a problem for browsers when generating URLs. We need to create a slug of our title that removes the spaces and replaces them with hyphens, this is what browsers like! Additionally, using a slug is better for SEO but we won't go into that right now.

To use the slug method we only need to add `use Str;` at the top of our controller, where we include any Facades, etc.

Now, let's make us a slug! To start we're going to validate the title, description and content of our form and store them in a variable:

```
$validated = request()->validate([
    'title' => 'required',
    'description' => 'required',
    'content' => 'required'
]);
```

To create a slug:

```
$slug = Str::slug($validated['title'], '-');
```

Here we are passing `validated` to the `slug()` method and then accessing the 'title' value and then telling the method to method to replace the spaces with hyphens. And storing the result in a variable named slug.

To see the value of `$slug` simply do `dd($slug);` and reload the page and you will see your slug!
