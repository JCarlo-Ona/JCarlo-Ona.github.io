<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My GitHub Page</title>
  <style>
    body {
      font-family: sans-serif;
      padding: 2rem;
      background-color: #f0f0f0;
    }
    h1 {
      color: #333;
    }
    /* Styling for the blog post list */
    .blog-posts {
      margin-top: 2rem;
    }
    .blog-post-item {
      margin-bottom: 2rem;
      display: flex; /* Use flexbox for layout */
      align-items: flex-start; /* Align items to the top */
    }
    .blog-post-image {
      width: 150px; /* Adjust as needed */
      height: auto;
      margin-right: 1rem;
    }
    .blog-post-info {
      flex-grow: 1;
    }
    .blog-post-title {
      margin-bottom: 0.5rem;
    }
    .blog-post-title a {
      text-decoration: none;
      color: #333; /* Example title color */
      font-weight: bold;
      font-size: 1.2rem;
    }
    .blog-post-excerpt {
      color: #555;
      font-size: 0.9rem;
      line-height: 1.4;
    }
    .blog-post-meta {
      color: #777;
      font-size: 0.8rem;
    }
  </style>
</head>
<body>
  <h1>Hello, world! 👋</h1>
  <p>Welcome to my site hosted on GitHub Pages!</p>

  <h2>About Me</h2>
  <p>I'm building cool stuff and learning web development.</p>

  <h2>Links</h2>
  <ul>
    <li><a href="https://github.com/jcarlo-ona" target="_blank">My GitHub</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#blog">Blog Posts</a></li>
  </ul>

  <h2 id="projects">Projects</h2>
  <p>Coming soon...</p>

  <h2 id="blog">Blog Posts</h2>
  <div class="blog-posts">
    {% for post in site.posts %}
      <div class="blog-post-item">
        {% if post.image %}
          <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" class="blog-post-image">
        {% endif %}
        <div class="blog-post-info">
          <h3 class="blog-post-title">
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          </h3>
          {% if post.excerpt %}
            <p class="blog-post-excerpt">{{ post.excerpt }}</p>
          {% endif %}
          <p class="blog-post-meta">Published on: {{ post.date | date: "%Y-%m-%d" }}</p>
        </div>
      </div>
    {% endfor %}
  </div>
</body>
</html>
