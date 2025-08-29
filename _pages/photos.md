---
title: Posts
permalink: /photos/
classes: wide
---

A few favorites. Click to view full size.

<div class="photo-grid">
  <a href="/assets/images/photos/sample1.jpg"><img src="/assets/images/photos/sample1.jpg" alt="Sample 1"></a>
  <a href="/assets/images/photos/sample2.jpg"><img src="/assets/images/photos/sample2.jpg" alt="Sample 2"></a>
  <a href="/assets/images/photos/sample3.jpg"><img src="/assets/images/photos/sample3.jpg" alt="Sample 3"></a>
  <a href="/assets/images/photos/sample4.jpg"><img src="/assets/images/photos/sample4.jpg" alt="Sample 4"></a>
</div>

<style>
.photo-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 14px;
}
.photo-grid img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: 10px;
}
</style>