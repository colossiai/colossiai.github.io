# Github pages

## URL


https://colossiai.github.io/



# Add new category

Left sidebar navigation (_data/navigation.yml):
- Categories section with collapsible links to "Books" and "Vocabulary"
- Shows on every post and category/tag page

Category archive pages (_pages/):
- /categories/ — overview of all categories
- /categories/books/ — lists all Books posts
- /categories/vocabulary/ — lists all Vocabulary posts
- /tags/ — overview of all tags

Top nav bar now links to Categories and Tags pages.

To add a new category later, you need to:
1. Add the category name in your post's front matter (categories: - NewCategory)
2. Add an entry in _data/navigation.yml under categories.children
3. Create a new _pages/category-newcategory.md file