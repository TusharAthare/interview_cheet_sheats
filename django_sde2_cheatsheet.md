
# Django SDE-2 Interview Preparation Cheat Sheet

## Core Django Concepts

### Models
**Q: What are Django models?**  
A: Django models define the structure of your database using Python classes. Each model maps to a single database table.

**Q: How do you create relationships in Django models?**  
A: Use fields like `ForeignKey`, `ManyToManyField`, and `OneToOneField`.

**Q: How do you optimize queries in Django ORM?**  
A: Use `select_related` and `prefetch_related` to reduce the number of queries.

---

### Views
**Q: Difference between Function-Based Views (FBVs) and Class-Based Views (CBVs)?**  
A:  
- FBVs are simpler but less reusable.  
- CBVs provide a reusable structure and inheritance, but can be complex.

**Q: How do you customize a class-based view?**  
A: Override methods like `get_context_data` or `dispatch`.

---

### Templates
**Q: How does template inheritance work in Django?**  
A: Use `{% extends "base.html" %}` to inherit from a base template and `{% block content %}{% endblock %}` to define blocks.

**Q: How do you create a custom template filter?**  
A: Define a function and register it using `@register.filter` in a `templatetags` module.

---

### URL Routing
**Q: How do you reverse a URL in Django?**  
A: Use the `reverse` function or `{% url 'name' %}` in templates.

**Q: Difference between `path()` and `re_path()`?**  
A: `path()` uses simple string patterns; `re_path()` uses regular expressions for complex patterns.

---

### Forms
**Q: How do you handle form validation in Django?**  
A:  
- Field-level: Define `clean_<fieldname>()`.  
- Form-level: Override the `clean()` method.

**Q: How do you handle file uploads?**  
A: Use `FileField` in models and configure `MEDIA_URL` and `MEDIA_ROOT`.

---

## Advanced Django Features

### Middleware
**Q: What is middleware in Django?**  
A: Middleware is a layer that processes requests and responses globally. You can add custom middleware for tasks like logging or authentication.

**Q: How do you write custom middleware?**  
A: Define a class with methods `__init__`, `process_request`, and `process_response`.

---

### Signals
**Q: What are Django signals?**  
A: Signals allow decoupled components to notify each other of events. Example: `post_save`.

**Q: How do you prevent signal duplication?**  
A: Use `dispatch_uid` or connect signals in the `ready()` method of the app config.

---

### Django ORM
**Q: How do you use annotations in Django?**  
A: Use `annotate()` to add calculated fields to your querysets.

**Q: What is the difference between `select_related` and `prefetch_related`?**  
A:  
- `select_related`: Follows foreign keys and performs a single SQL join.  
- `prefetch_related`: Retrieves related objects in separate queries for `ManyToMany` or reverse relations.

---

### Django Admin
**Q: How do you customize the Django admin interface?**  
A: Override `ModelAdmin` methods like `list_display`, `list_filter`, or `formfield_for_foreignkey`.

---

## Django Rest Framework (DRF)
**Q: What is a serializer in DRF?**  
A: A serializer converts complex data like querysets into JSON and vice versa.

**Q: How do you implement custom authentication in DRF?**  
A: Subclass `BaseAuthentication` and override the `authenticate` method.

**Q: What are the types of pagination in DRF?**  
A: PageNumberPagination, LimitOffsetPagination, and CursorPagination.

---

## Deployment and Scaling

**Q: How do you serve static files in production?**  
A: Use `collectstatic` to gather files and serve them via a web server like Nginx.

**Q: How do you cache in Django?**  
A: Use caching backends like Redis or Memcached and configure the `CACHES` setting.

---

## Behavioral Questions

**Q: Tell me about a challenging bug you resolved in Django.**  
A: Be ready to share an example where you debugged a performance issue or fixed a tricky ORM query.

**Q: How do you ensure security in a Django application?**  
A:  
- Use CSRF tokens.  
- Escape user inputs.  
- Validate form data.  
- Avoid exposing sensitive data in templates or logs.

---

## System Design Questions

**Q: How would you design a URL shortening service?**  
A:  
1. Create a model with `original_url` and `shortened_url`.  
2. Use a hash function to generate the short URL.  
3. Set up a redirect view to handle requests to the short URL.

---

This cheat sheet covers essential topics for a Django SDE-2 interview. Practice with real-world scenarios and mock interviews to gain confidence!
