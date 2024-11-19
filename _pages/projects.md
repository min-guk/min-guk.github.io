---
layout: page
title: photos
permalink: /photos/
description: A collection of memorable photos. (While organizing photos, I realized just how much I love beige pants 😅)
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

<div class="photos">
  {% assign all_photos = site.data.photos %}
  {% for photo_set in all_photos %}
    <div class="photo-set">
      <h2 class="photo-title">{{ photo_set.title }}</h2>
      <p class="photo-description">{{ photo_set.description }}</p>
      <div class="photo-images">
        {% for photo in photo_set.photos %}
          <img src="{{ photo }}" alt="{{ photo_set.title }}" class="photo-img" onclick="toggleZoom(this, event)">
        {% endfor %}
      </div>
    </div>
  {% endfor %}
</div>

<!-- JavaScript 수정 -->
<script>
let zoomedImg = null;

function toggleZoom(img, event) {
  event.stopPropagation(); // 이벤트 버블링 방지
  
  if (zoomedImg === img) {
    // 현재 확대된 이미지를 다시 클릭한 경우
    img.classList.remove('zoomed');
    zoomedImg = null;
  } else {
    // 다른 이미지가 확대되어 있었다면 원래 크기로
    if (zoomedImg) {
      zoomedImg.classList.remove('zoomed');
    }
    // 새로운 이미지 확대
    img.classList.add('zoomed');
    zoomedImg = img;
  }
}

// 페이지 어디든 클릭하면 확대 해제
document.addEventListener('click', function() {
  if (zoomedImg) {
    zoomedImg.classList.remove('zoomed');
    zoomedImg = null;
  }
});
</script>

<!-- CSS 스타일 수정 -->
<style>
.photo-img {
  cursor: pointer;
  transition: all 0.3s ease;
}

.photo-img:hover {
  opacity: 0.7;
}

.photo-img.zoomed {
  transform: scale(2.0);
  z-index: 1000;
  position: relative;
}
</style>