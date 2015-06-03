---
layout: post
title:  "Android Design Support Library"
categories: android
---

### The Library

At Google I/O 2015, Google announced the release of the Design Support Library.  The design library is part of version 22.2.0 of the [Support Library](http://developer.android.com/tools/support-library/index.html).  When Google released Lollipop, they introduced [Material Design](https://developer.android.com/design/material/index.html).  The goal of the Design Support Library is to make it easier to use the new design spec while maintaining backwards compability.

#### What's New
In the Design Library, the following have been added.

- [TextInputLayout](http://developer.android.com/reference/android/support/design/widget/TextInputLayout.html)
- [FloatingActionButton](http://developer.android.com/reference/android/support/design/widget/FloatingActionButton.html)
- [Snackbar](http://developer.android.com/reference/android/support/design/widget/Snackbar.html)
- [TabLayout](http://developer.android.com/reference/android/support/design/widget/TabLayout.html)
- [NavigationView](http://developer.android.com/reference/android/support/design/widget/NavigationView.html)
- [CoordinatorLayout](http://developer.android.com/reference/android/support/design/widget/CoordinatorLayout.html)
- [AppBarLayout](http://developer.android.com/reference/android/support/design/widget/AppBarLayout.html)
- [CollapsingToolbarLayout](http://developer.android.com/reference/android/support/design/widget/CollapsingToolbarLayout.html)

### The Meat

Since there is not a lot out there on on this new library yet, I want to walk through using some of it's features.  In this post, I will focus on the CoordinatorLayout, CollapsingToolbarLayout, and AppBarLayout. I will also cover the use of the RecyclerView which was released in v21 of the support library back in October 2014.

I am going to walk you through how I implemented the Collapsing Toolbar Bar.

#### CoordinatorLayout

> CoordinatorLayout, a general purpose layout, used for building dependencies between sibling views and allowing easy scrolling reactions between components via CoordinatorLayout.Behavior. Many of the Design Library components rely on being a child of a CoordinatorLayout.

The CoordinatorLayout will a parent of everything else used.  This layout connects the CollapsingToolbarLayout to the RecyclerView which I am using in place on a ListView.

The CoordinatorLayout can be used in two different ways.

> 1. As a top-level application decor or chrome layout
> 2. As a container for a specific interaction with one or more child views.

__activity_main.xml__

```xml
<android.support.design.widget.CoordinatorLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!-- our scrolling content -->

    <!-- our collapsing toolbar -->

</android.support.design.widget.CoordinatorLayout>
```

This example uses the layout as a top-level layout and a container for a specific interaction (the collapsing toolbar).

#### The AppBarLayout and CollapsingToolbarLayout

>AppBarLayout, a container for a Toolbar and other views (such as TabLayout) for reacting to scrolling events by scrolling off the screen, becoming visible in reaction to a downward scroll, or collapsing/uncollapsing before scrolling off/onto the screen.

>CollapsingToolbarLayout for controlling how a Toolbar collapses. A toolbar may collapse by: pinning components to the top of the screen while it collapses, introducing parallax scrolling of components such as an ImageView, or adding a content scrim color when the view is partially collapsed.
