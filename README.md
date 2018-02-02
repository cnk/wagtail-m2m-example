# Introduction

Wagtail's [modelcluster extension for
Django](https://github.com/wagtail/django-modelcluster) claims that
you can manage many to many relationships between pages and snippets
(or plain Django models). I believe that the underlying deferred
saves, etc. work on the model level - at least if you use their
ParentalManyToManyField. The [Bakery Demo
project](https://github.com/wagtail/bakerydemo/) has an example of
this in their relationship between breads and ingredients. But the
only UI for managing the relationship appears to be a FieldPanel that
wraps some version of a multiple select or checkbox widget.

I have two issues with this:

  1. I need for my mapping relationship to be ordered - so I need to
  have an explicit intermediary table that contains a sort_order column
  (by inheriting from Orderable).

  2. And I am going to have way too many items to be able to use the
  "select from this list" UI.

If you have just a one to many relationship, say via a ParentalKey,
you can use an InlinePanel to be able to add and edit the related
objects from the admin page for the parent object. I would like to be
able to map child objects to the parent, order those mappings, and
even create child objects - all from the edit interface for the parent
page.




