# Tailwind JIT Purge Failure with Client-Side Dynamic Classes

This repository demonstrates a common issue encountered when using Tailwind CSS's JIT mode with frameworks that generate dynamic class names client-side. The problem is that unused styles, dynamically added, aren't purged during the production build, leading to larger bundle sizes and slower load times.

## Bug Reproduction

1. Clone this repository.
2. Install dependencies: `npm install`
3. Run the development server: `npm run dev`
4. Observe the bundle size.  The bundle will be relatively small because unused classes are purged.
5. Run the production build: `npm run build`
6. Analyze the production bundle size.  The bundle will be significantly larger because the unused classes are not fully purged due to the client-side dynamic class generation.

## Solution

The solution involves carefully managing how dynamic classes are generated and ensuring that Tailwind can correctly identify and purge them. The solution may involve using a whitelist for specific dynamic classes, customizing your PurgeCSS configuration, or refactoring your component structure to generate fewer dynamic classes. More details are provided in `bugSolution.js`.

## Technologies Used

- Next.js (or similar framework like Nuxt.js)
- Tailwind CSS
- JavaScript