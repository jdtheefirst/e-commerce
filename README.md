![Nextjs Storefront](./public/screenshot.png)

<div align="center">
  <h1>E-Commerce with Saleor Next.js Storefront</h1>
</div>

<br/>
<div align="center">
## Features

- **Next.js 14**: File-based routing, React 18, Fast Refresh, Image Optimization and more.
- **App Router**: Uses React Server Components, Data Cache, and async components.
- **TypeScript**: Strongly typed codebase and GraphQL payloads with strict mode.
- **GraphQL best practices**: Uses GraphQL Codegen and `TypedDocumentString` to reduce boilerplate and bundle size.
- **Customizable CSS**: TailwindCSS can be extended or replaced with an alternative CSS solution.
- **Tooling included**: Comes with ESLint, Prettier, Husky, Lint Staged, and Codegen preconfigured.

**Global:**

- Dynamic menu
- Hamburger menu
- SEO data

**Checkout:**

- Single page checkout (including login)
- Portable to other frameworks (doesn't use Next.js components)
- Adyen integration
- Stripe integration
- Customer address book
- Vouchers and Gift Cards

**Product catalog:**

- Categories
- Variant selection
- Product attributes
- Image optimization

**My account:**

- Order history (coming soon)
- Order completion
- Order details

## Quickstart

### 1. Create Saleor backend instance
To quickly get started with the backend, use a free developer account at [Saleor Cloud](https://cloud.saleor.io/?utm_source=storefront&utm_medium=github).

Alternatively you can [run Saleor locally using docker](https://docs.saleor.io/docs/3.x/setup/docker-compose?utm_source=storefront&utm_medium=github).

### 2. Clone storefront

#### [Option 1] Using Comand line tools

Install or update to the latest version of the [Saleor CLI](https://docs.saleor.io/docs/3.x/cli) by running the following command:

```bash
npm i -g @saleor/cli@latest
```

Clone storefront, install dependencies, and connect with the provided Saleor instance hostname

```bash
saleor storefront create --url https://{SALEOR_HOSTNAME}/graphql/
```

#### [Option 2] Manual install

Clone repository:
```bash
git clone https://github.com/saleor/storefront.git
```

Copy environment variables from `.env.example` to `.env`:

```bash
cp .env.example .env
```

Edit `.env` and set `NEXT_PUBLIC_SALEOR_API_URL` to your Saleor GraphQL endpoint URL, e.g., `https://example.saleor.cloud/graphql/`.

Then, [install `pnpm`](https://pnpm.io/installation) and run the following command to install all dependencies in the repo:

```bash
pnpm i
```


## Payments

Currently, Saleor Storefront supports payments via the [Saleor Adyen App](https://docs.saleor.io/docs/3.x/developer/app-store/apps/adyen). To install and configure the payment app go to the "Apps" section in the Saleor Dashboard (App Store is only available in Saleor Cloud).

> WARNING:
> To configure the Adyen App, you must have an account with [Adyen](https://www.adyen.com/).

> NOTE:
> Saleor Stripe App integration is a work in progress.

## Development

To start the development server, run the following:

```bash
pnpm dev
```

The app is now running at `http://localhost:3000`.

> NOTE:
> Saleor Storefront is a Next.js app. In case you are not familiar with Next.js, we recommend you to read the [Next.js documentation](https://nextjs.org/docs) (make sure you've selected "Using App Router" in the sidebar).

#### GraphQL queries and mutations:

After altering or creating new GraphQL queries in `gql` folder, you need to run the following command to generate types and javascript queries:

```bash
pnpm run generate
```

### Preview content changes instantly (Draft Mode)

Visit `http://{your-host}/api/draft` to enable cookies that disable caching to preview catalog and content changes instantly. [Learn more about the Draft Mode in Next.js docs.](https://nextjs.org/docs/app/building-your-application/configuring/draft-mode)

