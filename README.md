## Next.js App Router Course - Starter

This is the starter template for the Next.js App Router Course. It contains the starting code for the dashboard application.

For more information, see the [course curriculum](https://nextjs.org/learn) on the Next.js Website.

# Next.js Fundamentals of Use (New Learn from Site)

## This time it will make a Dashboard

- A public home page.
- A login page.
- Dashboard pages that are protected by authentication.
- The ability for users to add, edit, and delete invoices.

## Overview

- Styling: The different ways to style your application in Next.js.
- Optimizations: How to optimize images, links, and fonts.
- Routing: How to create nested layouts and pages using file-system routing.
- Data Fetching: How to set up a database on Vercel, and best practices for fetching and streaming.
- Search and Pagination: How to implement search and pagination using URL Search Params.
- Mutating Data: How to mutate data using React Server Actions, and revalidate the Next.js cache.
- Error Handling: How to handle general and 404 not found errors.
- Form Validation and Accessibility: How to do server-side form validation and tips for improving accessibility.
- Authentication: How to add authentication to your application using NextAuth.js and Middleware.
- Metadata: How to add metadata and prepare your application for social sharing.

## How does the Folder Structure of Next.js works
- */app*: Contains all the **Routes**, **Components** and **Logic** to your application;
    - */app/lib*: Contains the **Functions** of application, utility and data fetching functions;
    - */app/ui*: Contains all **UI** components for your application, ex.:Cards, tables and forms;
- */public*: Contains all static **Assets**, ex.: images;
- */scripts*: Contains **Seeding Script**, will be used to populate database

## Putting stylesheet
You can make a global CSS file in *app/ui* and import it to components;
    (It is a good practice to add in top-level component)
In this example the project uses Tailwind framework;
You can also use the **clsx** to make conditionally styles;

## Adding Custom Fonts and Images
Next.js have an optimization of fonts because some custom ones have to be fetched from the internet and sometimes, the browser have a Layout Shift with other fonts before the custom ones appear. The next/font module downloads the font files at *build time* and hosts as a static asset;

Next.js also have an Image Optimazation with an Image component, that resizes the image file size to send a smaller file to client, lazy loads images by default, serves them into modern formats and prevents the layout shift when loading page;