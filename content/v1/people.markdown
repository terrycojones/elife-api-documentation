---
title: Users | GitHub API
---

# Users API

* TOC
{:toc}

Many of the resources on the users API provide a shortcut for getting
information about the currently authenticated user. If a request URL
does not include a `:user` parameter then the response will be for the
logged in user (and you must pass [authentication
information](/v3/#authentication) with your request).

## Get a single user

    GET /users/:user

### Response

<%= headers 200 %>
<%= json :full_user %>


## Get elife person

    GET /users/:user

### Response

<%= headers 200 %>
<%= json :elife_person %>



## Get the authenticated user

    GET /user

### Response

<%= headers 200 %>
<%= json :private_user %>


## Get the null response

    GET /null

### Response

<%= headers 418 %>
<%= json :fluidinfo_null %>


FLUIDINDO_NULL


## Update the authenticated user

    PATCH /user

### Input

name
: _Optional_ **string**

email
: _Optional_ **string** - Publicly visible email address.

blog
: _Optional_ **string**

company
: _Optional_ **string**

location
: _Optional_ **string**

hireable
: _Optional_ **boolean**

bio
: _Optional_ **string**

<%= json \
    :name     => "monalisa octocat",
    :email    => "octocat@github.com",
    :blog     => "https://github.com/blog",
    :company  => "GitHub",
    :location => "San Francisco",
    :hireable => true,
    :bio      => "There once..."
%>

### Response

<%= headers 200 %>
<%= json :private_user %>

