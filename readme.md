# The Wargos

Eleventy version of the static web site at https://thewargos.com

[![Netlify Status](https://api.netlify.com/api/v1/badges/717d6d3e-0a16-4412-9739-5d30ca859375/deploy-status)](https://app.netlify.com/sites/thewargos/deploys)

Demo site: https://thewargos.netlify.app/

## Tasks

- [x] Home page article list
- [x] Articles Page
- [x] Categories Page
- [x] Google Analytics
- [x] About content
- [x] Clean up post content
- [x] Home content
- [x] Home sidebar
- [x] Favicon
- [x] Menu highlighting on paginated pages
- [ ] Image gallery
- [ ] Fix image links
- [ ] Search
- [ ] Most popular
- [ ] Subscribe

## Notes to Self

```liquid
{% gallery "gallery-id" %}
{% galleryImage "src/images/year/image-file-name.jpg", "Image Alt Text" %}
{% galleryImage "src/images/year/image-file-name.jpg", "Image Alt Text" %}
{% endgallery %}
```