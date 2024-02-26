# WADITRACMS

## MODELS:

```yaml
# User Model
User:
  fillable: [name, email, password]
  relations:
    - Role
    - Comment
  
# Role Model
Role:
  fillable: [name, description]
  relations:
    - User
    - Permission

# Permission Model
Permission:
  fillable: [name, description]
  relations:
    - Role

# Page Model
Page:
  fillable: [title, slug, content]
  relations:
    - User

# Category Model
Category:
  fillable: [name, slug]
  relations:
    - Post
    - Product

# Tag Model
Tag:
  fillable: [name, slug]
  relations:
    - Post
    - Product

# Post Model
Post:
  fillable: [title, slug, content]
  relations:
    - User
    - Category
    - Tag
    - Content
    - Comment

# Product Model
Product:
  fillable: [name, slug, description, price]
  relations:
    - User
    - Category
    - Tag
    - Content
    - Comment

# Content Model
Content:
  fillable: [title, type, contentable_id, contentable_type, order]
  relations:
    - Text
    - Image
    - Video

# Text Model
Text:
  fillable: [content]

# Image Model
Image:
  fillable: [path, thumbnail_path]

# Video Model
Video:
  fillable: [path, thumbnail_path]

# Comment Model
Comment:
  fillable: [content]
  relations:
    - User
    - Post
    - Product

# Menu Model
Menu:
  fillable: [location]

# Submenu Model
Submenu:
  fillable: [name, slug, page_id, parent_id, order, menu_id]
  relations:
    - Page
    - Children
    - Parent
    - Menu

# Setting Model
Setting:
  fillable: [key, value]

```