# Next.js Build Hang with `getStaticPaths('blocking')` and `getStaticProps` error

This repository demonstrates a subtle bug in Next.js applications using dynamic routes, `getStaticPaths` with a `'blocking'` fallback, and `getStaticProps`.  If `getStaticProps` fails to fetch data for a specific path, the entire build process can hang.

## Reproduction

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run build`.

You'll observe that the build process hangs indefinitely due to an error within `getStaticProps` for a specific path. 

## Solution

The solution involves handling potential errors gracefully within `getStaticProps` and providing a fallback mechanism to avoid blocking the build process.  The solution is shown in `bugSolution.js`.