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
- You can make a global CSS file in *app/ui* and import it to components;
    - (It is a good practice to add in top-level component)
- In this example the project uses Tailwind framework;
- You can also use the **clsx** to make conditionally styles;

## Adding Custom Fonts and Images
- Next.js have an optimization of fonts because some custom ones have to be fetched from the internet and sometimes, the browser have a Layout Shift with other fonts before the custom ones appear. The next/font module downloads the font files at *build time* and hosts as a static asset;

- Next.js also have an Image Optimazation with an Image component, that resizes the image file size to send a smaller file to client, lazy loads images by default, serves them into modern formats and prevents the layout shift when loading page;

## Creating new Pages
- Nested **Routes** Next.js uses file-system routes as URL Segment;
- The file *page.tsx* serves as a way to export React components, in other words, to show the page of another route you must include in the directory the file *page.tsx*;
- So in reality, to access a page *http://localhost:3000/dashboard/customers*. You have to create a folder called *dashboard* and inside it another folder called *customers*, and a *page.tsx* in both of them;
- Even making a new *Layout.tsx* file in dashboard, there is a *RootLayout* function that its purpose is to share the UI across multiple pages;

## How to change Pages
- Navigating throught the <a> tag causes the app to refresh, due to that, Next.js made a <Link /> component to change the pages without the need to the page be refreshed;
- This happens because when there is a <Link> component, Next.js automatically prefetches the code for it;
- Next.js provides a *hook* called usePathname() to check the pattern of the links;

## Database Implementation
- Using Vercel Hobby plan, we deploy the project into Vercel's workspace, with this, we can create a Postgres Database in Vercel;
- In the folder *scripts* there is a *seed.js* that creates tables and populates it;
- You can use SQL queries in the Vercel's page of the project;

## Fetch Data
- Some approaches to fetching data are:
    - APIs, ORMs, SQL Queries, etc.
- In the API Layer you can use in case of using 3rd party services or if you are fetching data for a client, so to keep secret of the server, you create an API to not have server exposed;
- With Database Queries, you use for a full-stack application and use Relational Database or an ORM like Prisma, a case for using this, is when creating API endpoints or query the database directly to the app, risking leakage;
- When using await function, you make a waterfall requests, a sequential way of fetching, using *Promise.all()* or *Promise.allSettled()* make the requests working paralleled;

## Static and Dynamic Rendering
