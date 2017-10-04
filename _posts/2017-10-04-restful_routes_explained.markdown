---
layout: post
title:      "RESTful Routes Explained"
date:       2017-10-04 14:40:26 +0000
permalink:  restful_routes_explained
---


The concept of RESTful routes can be a little confusing at first, but quickly becomes second nature with a little practice.  This post explores what a route is, the rationale behind the RESTful routing pattern, and serves as a quick reference on the topic.

**What is a route?**

Whenever a person clicks on a link and visits a web page, the browser sends an HTTP request to a specific URL of an application.  Routes are the piece of an application that connect that HTTP request to the appropriate page and methods so that the correct information is returned.  For example, if you visit a website with "/dogs" in the URL, you would expect the page to load a list of dogs.  Routes are the key to making sure the website displays the appropriate data.

**What are RESTful Routes?**

RESTful routing is simply a pattern for naming your URLs as well as the correct HTTP verb to use in each situation.  Without this type of convention, one developer may use the URL "/all-the-dogs", while another uses "/display-dogs", and another uses "/dogs-list".  RESTful routing standardizes the naming conventions so that developers can more easily understand other web applications, and makes URLs simpler for the end user as well.

There are 7 RESTful routes, listed in the table below and then explained:

<table>
<thead>
<tr>
<th><strong>URL</strong></th>
<th><strong>HTTP Verb</strong></th>
<th><strong>Action</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>/dogs</td>
<td>GET</td>
<td>index</td>
</tr>
<tr>
<td>/dogs/new</td>
<td>GET</td>
<td>new</td>
</tr>
<tr>
<td>/dogs</td>
<td>POST</td>
<td>create</td>
</tr>
<tr>
<td>/dogs/:id</td>
<td>GET</td>
<td>show</td>
</tr>
<tr>
<td>/dogs/:id/edit</td>
<td>GET</td>
<td>edit</td>
</tr>
<tr>
<td>/dogs/:id</td>
<td>PATCH/PUT</td>
<td>update</td>
</tr>
<tr>
<td>/dogs/:id</td>
<td>DELETE</td>
<td>destroy</td>
</tr></tbody></table>


**INDEX**

This route is responsible for listing all of a specific type of element in the database (in this case dogs).

**NEW**

The new route displays a form that a user fills out to with the intention of creating a new dog.  Notice that the "New" route is a GET request, so this route does not actually modify the database by itself.  That part comes next.

**CREATE***

The "Create" route uses the "POST" method to take the data the user submitted in the form (in the "New" route), and create a new record in the database.

**SHOW**

When you visit the "Index" route, you see a list of all dogs.  When you visit the "Show" route, on the other hand, you see all the details about *one specific* dog.  

**EDIT**

The "Edit" route is similar to the "New" route in that it displays a form for the user to fill out.  However, in this case the form already contains information about an existing database record that the user is editing.

**UPDATE**

The "Update" route takes the data the user entered in the form displayed by the "Edit" route and actually modifies the record in the databse.

**DESTROY/DELETE**

As you can probably guess, the "Destroy" or "Delete" route is responsible for removing a given record from the database.

