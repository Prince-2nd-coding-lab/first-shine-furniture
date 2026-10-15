# Firstshinefurniture

design beautyfull website for this business

This project was built with [Lovable](https://lovable.dev).

**Live app**: https://firstshinefurniture.lovable.app

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/ff8c707d-71cf-4a5f-a7b6-7c77806a61a7).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```

## Deploy to Vercel

1. Import this GitHub repository into Vercel with the repository root as the Root Directory.
2. Use **Other** as the Framework Preset and **Node.js 22.x**. The committed `vercel.json` supplies the install and build commands; leave Output Directory unset. Nitro generates `.vercel/output` with server functions and static assets, so do not set it to `dist` or add an SPA catch-all rewrite.
3. Add these environment variables to both **Production** and **Preview**, using the existing project's public connection settings:

   | Variable | Value to supply |
   | --- | --- |
   | `VITE_SUPABASE_URL` | Existing public backend URL |
   | `VITE_SUPABASE_PUBLISHABLE_KEY` | Existing public publishable key |
   | `SUPABASE_URL` | Same externally reachable URL as `VITE_SUPABASE_URL` |
   | `SUPABASE_PUBLISHABLE_KEY` | Same publishable key as `VITE_SUPABASE_PUBLISHABLE_KEY` |

   Browser variables are embedded during the build. Server variables are needed for catalogue and other public reads. Use the public connection URL, not a Lovable-internal runtime address. No service-role key or database password is needed by the current app, and neither is available from Lovable Cloud. Never put private credentials in `VITE_*` variables.
4. Deploy. In Lovable Cloud's authentication settings, allow the exact Vercel production origin and preview origins you intend to use, including the `/admin` email-confirmation return URL used by the current sign-up page. Set the production Site URL accordingly. Avoid a wildcard for all Vercel projects.
5. Check the homepage, `/furniture`, a product detail URL, and `/projects` directly and after refresh. Then check sign-in and a test enquiry on the deployed site.

Vercel uses the existing Lovable Cloud data and storage; this configuration does not migrate or seed a second backend. Changing environment variables requires a new deployment. Deployment and authentication URL configuration are not performed by committing these files.

For a local Vercel-target build, supply the same environment variables and run `bun run build:vercel`. Normal `bun run build` keeps the Lovable target, while Vercel builds select the Vercel adapter. Do not commit generated `.vercel` output or downloaded Vercel environment files; add `.vercel/` to your local Git exclusion settings before using the Vercel CLI.
