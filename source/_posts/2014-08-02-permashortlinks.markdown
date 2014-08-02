---
layout: post
title: "permashortlinks"
date: 2014-08-02 10:44:44 +0100
comments: true
categories: [IndieWeb]
redirect_from: /s/9.htm
---

Just for fun, I did a permashortlinks engine for Octopress \o/

<!-- more -->

Add `jekyll-redirect-from` to your gemfile. Add it to your

```bash _config.yml
gems:
  - jekyll-redirect-from
```

Modify a bit your Rakefile:
```bash diff Rakefile
diff --git a/Rakefile b/Rakefile
index 9fb3783..8c01394 100644
--- a/Rakefile
+++ b/Rakefile
@@ -107,6 +107,9 @@ task :new_post, :title do |t, args|
   if File.exist?(filename)
     abort("rake aborted!") if ask("#{filename} already exists. Do you want to overwrite?", ['y', 'n']) == 'n'
   end
+  redirect = Dir.glob("public/s/*").sort_by{|s| s[/\d+/].to_i }.last
+  redirect_number = /public\/s\/(\d+)\.htm/.match(redirect)[1].to_i + 1
+  redirect.gsub!(/\d+/, redirect_number.to_s).gsub!(/public/, "")
   puts "Creating new post: #{filename}"
   open(filename, 'w') do |post|
     post.puts "---"
@@ -115,6 +118,7 @@ task :new_post, :title do |t, args|
     post.puts "date: #{Time.now.strftime('%Y-%m-%d %H:%M:%S %z')}"
     post.puts "comments: true"
     post.puts "categories: "
+    post.puts "redirect_from: #{redirect}"
     post.puts "---"
   end
 end
```

Add a `redirect_from` field to your older posts

And that's it. Now, when you create a post, and it will have automatically a shortlink.
In my case, this article has the following permashortlink: [www.pierre-o.fr/s/9.htm](www.pierre-o.fr/s/9.htm)