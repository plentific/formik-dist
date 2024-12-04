# formik-dist

## Why does this repo exist

This repo contains the built files of the `Formik` package so we can easily point to it from the Dashboard repo.

## A bit more explanations

The original `Formik` repo uses a monorepo structure meaning that we can't easily point to it from our `package.json` dependencies.

There are tools that exist to circumvent that (like `gitpkg.vercel.app` pointing to it with `"formik": "https://gitpkg.vercel.app/plentific/formik/packages/formik?c7e7cf6e829f6b9d79cdacfd2fba66771c48b28b"`) but they are deemed unsafe as any code could be introduced on the `gitpkg.vercel.app` server.

## How to update Formik

1. Make sure our file changes are up to date with the original Formik repo on [that PR](https://github.com/jaredpalmer/formik/pull/3976)
2. Make sure the `main` branch of the fork is up to date with our Formik changes using [that PR](https://github.com/plentific/formik/pull/5)
3. Clone [the fork repo](https://github.com/plentific/formik) locally
4. Make sure you are on the `main` branch
5. Install all the necessary dependency with `yarn` (Formik uses `yarn` at the time of writing this)
6. Build the `Formik` packages locally using `yarn build`
7. Copy the `dist` folder from `packages/formik` into this repo
8. Create a PR to merge this repo's file update to `master`
9. Point the dashboard's `Formik` dependency to the new commit
