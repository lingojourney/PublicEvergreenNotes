// including nested collections etc. 
Frontmatter can also be used to organize files into nested collections. In a static site generator, a collection is a group of related files that are treated as a unit. A post in a blog, for example, might be part of a "posts" collection. 

Here's an example of how you might use frontmatter to specify that a file belongs to the "posts" collection:

```
---
title: "Blog Post Title"
date: 2021-01-01
author: "Author Name"
collection: posts
---
```

In this case, the `collection` key specifies that this file is part of the "posts" collection.

Nested collections allow you to create a hierarchical structure within your site. For example, you could have a "posts" collection that contains several sub-collections for different categories of posts.

Here's an example:

```
---
title: "Blog Post Title"
date: 2021-01-01
author: "Author Name"
collection:
  name: posts
  category: news
---
```

In this case, the `collection` key has been given an object as its value. This object has two keys: `name`, which specifies the name of the collection, and `category`, which specifies the sub-collection within the "posts" collection.

Frontmatter syntax provides a flexible way to include metadata with your files and organize them into collections and sub-collections. By using frontmatter effectively, you can provide clear instructions for your static site generator and make your website easier to navigate.

## Appendix

[One result is from Reddit, where a user asks whether they should put fields in frontmatter or in body when using Obsidian and Dataview](https://www.reddit.com/r/ObsidianMD/comments/p11scx/should_i_put_fields_in_frontmatter_or_in_body/)[1](https://www.reddit.com/r/ObsidianMD/comments/p11scx/should_i_put_fields_in_frontmatter_or_in_body/). [The answer is that it depends on the use case, but generally frontmatter is more suitable for metadata that is not meant to be displayed in the note, while body is more suitable for data that is meant to be displayed or queried in the note](https://www.reddit.com/r/ObsidianMD/comments/p11scx/should_i_put_fields_in_frontmatter_or_in_body/)[1](https://www.reddit.com/r/ObsidianMD/comments/p11scx/should_i_put_fields_in_frontmatter_or_in_body/).

[Another result is also from Reddit, where a user asks how to query for indented YAML frontmatter in Obsidian and Dataview](https://www.reddit.com/r/ObsidianMD/comments/sl5buh/dataview_query_for_indented_yaml_frontmatter/)[2](https://www.reddit.com/r/ObsidianMD/comments/sl5buh/dataview_query_for_indented_yaml_frontmatter/). [The answer is that Dataview does not support nested YAML structures yet, but there is a workaround using lists instead of maps](https://www.reddit.com/r/ObsidianMD/comments/sl5buh/dataview_query_for_indented_yaml_frontmatter/)[2](https://www.reddit.com/r/ObsidianMD/comments/sl5buh/dataview_query_for_indented_yaml_frontmatter/). For example, instead of writing:

```yaml
fruit:
  red_fruit: Cherry, Strawberry
  yellow_fruit: Banana, Lemon
  green_fruit: Kiwi, Pear
```

One can write:

```yaml
fruit:
  - red_fruit: Cherry, Strawberry
  - yellow_fruit: Banana, Lemon
  - green_fruit: Kiwi, Pear
```

And then query for notes that contain Cherry in the fruit section using:

```dataview
List WHERE contains(fruit.red_fruit, "Cherry")
```

## Appendix 02
As far as I know, you cannot have tuples in Obsidian frontmatter. Tuples are a data type in Python, but Obsidian frontmatter uses YAML, which is a different language. [YAML does not have tuples, but it has other data types such as scalars, sequences, and mappings](https://www.reddit.com/r/ObsidianMD/comments/p11scx/should_i_put_fields_in_frontmatter_or_in_body/)[1](https://www.reddit.com/r/ObsidianMD/comments/p11scx/should_i_put_fields_in_frontmatter_or_in_body/).

A scalar is a single value, such as a string, a number, or a boolean. For example, this is how you can define a scalar in YAML:

```yaml
name: Alice
```

A sequence is a list of values, separated by commas and enclosed in brackets. For example, this is how you can define a sequence in YAML:

```yaml
colors: [red, green, blue]
```

A mapping is a set of key-value pairs, separated by colons and enclosed in braces. For example, this is how you can define a mapping in YAML:

```yaml
person: {name: Bob, age: 25}
```

You can also nest sequences and mappings to create more complex structures. For example, this is how you can define a nested structure in YAML:

```yaml
people:
  - {name: Carol, age: 30}
  - {name: Dave, age: 35}
```

If you want to learn more about YAML and its data types, you can check out these web pages:

- [YAML - Wikipedia]
- [Learn YAML in Y Minutes]
- [YAML Tutorial - W3Schools]

I hope this helps you with your question. 😊