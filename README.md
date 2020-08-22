## RedwoodJS Example Blog

![RedwoodJS Example Blog Screenshot](https://user-images.githubusercontent.com/300/67903394-aced3080-fb28-11e9-85bb-b5fdbb4b6c34.png)

You can view this app live at https://redwoodjs-example-blog.vercel.app/

## Table of Contents

* [Overview](#overview)
* [Getting Started](#getting-started)
  * [Installation](#installation)
  * [Enabling Image Uploads](#enabling-image-uploads)
* [Deploy to Vercel](#deployment)

## Overview

Here is a full-featured blog engine written with RedwoodJS. It includes:

* Listing all blog posts with first paragraph summaries and pagination (the homepage)
* Reading a single, full blog post
* Searching for blog posts by keyword
* Displaying all posts with a given tag
* Contact form
* Fully responsive at various viewport sizes

On the tech side:

* Data stored in a SQL database (SQLite locally)
* Image uploads and CDN via [Filestack](https://filestack.com)
* CSS styling via [TailwindCSS](https://tailwindcss.com)

## Getting Started

### Installation

Clone the repo:

    git clone https://github.com/redwoodjs/example-blog.git
    cd example-blog

Install dependencies:

    yarn install

Create a local SQLite database and seed it with a few blog posts:

    yarn redwood db up
    yarn redwood db seed

Now you should be able to start a development server:

    yarn redwood dev

Assuming everything worked, open a browser to http://localhost:8910 and you should
be seeing the homepage (similar to the screenshot above).

### Enabling Image Uploads

The blog uses an external service, [Filestack](https://filestack.com) to handle image
uploads. If you want to be able to upload images in local development you'll need to
create a free account at Filestack and copy the API key. You get 100 uploads per
month on their free account which should be plenty to test with.

Once you have logged into Filestack copy the API key shown at the top right of the dashboard:

![Filestack screenshot](https://user-images.githubusercontent.com/300/67905641-40296480-fb2f-11e9-8f86-94fd6ddbb12d.png)

If you haven't already, copy the `.env.example` file in the root of the blog to a new
file named `.env`. Edit the `FILESTACK_API_KEY` variable to be equal to the one you
just copied. Save `.env` and restart your `yarn dev` process. Now when creating a
new blog post http://localhost:8910/admin/new you should see a filepicker towards the
bottom of the form:

![New post screenshot](https://user-images.githubusercontent.com/300/67907861-9f3ea780-fb36-11e9-8bca-4e71c38d47e3.png)

# Deployment to Vercel

See the Vercel section of the [Deploy doc](https://redwoodjs.com/docs/deploy).

> **Note**: to deploy on Vercel using this repo, you must set the production deploy branch on Vercel to `vercel-deploy`

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/import/git?s=https%3A%2F%2Fgithub.com%2Fredwoodjs%2Fexample-blog.git&env=DATABASE_URL)


