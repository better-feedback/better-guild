# Better

## How to submit your idea

Visit [/roadmap/issues](https://github.com/better-feedback/roadmap/issues) and add a new issue.

To list an issue on your Better board, tag it as `bug` or `feature` and its status as `open`, `inProgress` or `live`.

Your issue now appears on [roadmap.betterhq.org](https://roadmap.betterhq.org/) and you can

👉 login with your NEAR or Polygon wallet

👉 vote on your favorite issue, after getting whitelisted by the team

👉 add funds to the issue to start a bounty

👉 work on a bounty and claim the bounty pool.

---

## How to set up Better for your organization

Better mirrors your [Github issues](https://github.com/better-feedback/roadmap/issues) to a [hosted website](https://roadmap.betterhq.org/), which allows your community to vote on them, fund them as bounties and claim the pooled funds for implementing them. Issues can range from feature requests, to content marketing ideas and DAO grant proposals.

Setting up your own Better project takes a few steps:

- Fork the [Better repo](https://github.com/better-feedback/roadmap)
- Host the site by creating a project on [Vercel]([url](https://vercel.com/))
    - Set your ENV variables based on `./.env.example` (Got any questions? Hit us up on [Discord](https://discord.com/invite/wwwwRFa6aj)!)

After a successful deployment, point your Vercel deployment to your custom URL: eg. feedback.yourdapp.com, roadmap.yourdapp.com, bounties.yourdapp.com

- Copy your DNS info at `https://vercel.com/[yourproject]/[yourrepo]/settings/domains`
- Add the info to your domain manager
- Send us your domain name on [Discord](https://discord.com/invite/wwwwRFa6aj), so we can whitelist your domain for github authentication!

🎊 Congratulations, you are hosting your own Better board 🎉

- When using a private repo, make sure to add our notification bot `betterhq-bot` as contributor.

---

## How to customize your Better site

Set your project name and custom footer links in this config file: `\better-app\src\config.ts`

Better mirrors each Github issue based on its tags. The default tags are `open`, `inProgress`, `live`.
If you want to set your own, edit the following files:
- `\better-app\src\config.ts`
- `src/features/issues/components/issues-list-page.tsx`
- `src/features/issues/constants.ts`
- `src/features/issues/types.ts`

You want to customize your site's UI or got feature ideas for Better? Join our [Discord](https://discord.com/invite/wwwwRFa6aj) and let us know!

---

### Dev

Checkout the repo and set the required environmental variables by copying `./.env.example` into `./.env.local`.

Next, install the dependencies:

```bash
npm install
# or
yarn install
```

Run the development server:

```bash
npm run dev
# or
yarn dev
```

---

### FAQ

<details>
  <summary>Which chains are supported?</summary>

1. NEAR testnet
2. Polygon testnet

</details>

<details>
  <summary>How to set up Guild.xyz to allow voting with NEAR wallets</summary>

1. Head to [guild.xyz](https://guild.xyz/) and create your own guild
2. Add a new role
3. Add an allowlist with the addresses that should be able to vote
     * Convert NEAR addresses to HEX format (eg [here](https://www.online-toolz.com/tools/text-hex-convertor.php))
     * Add `0x` in front of the address, and enough `0`s to fill the total string to 42
     * Eg. `0x000000003761696d656e73638e746573746e6574`
4. After saving and signing the Metamask request, the whitelisted addresses should be able to vote

</details>

<details>
  <summary>How to set up Guild.xyz to allow voting with Ethereum / Metamask</summary>

1. Head to [guild.xyz](https://guild.xyz/) and create your own guild
2. Add a new role
3. Add an allowlist with the addresses that should be able to vote
4. After saving and signing the Metamask request, the whitelisted addresses should be able to vote

</details>

<details>
  <summary>How to disable the voting whitelist</summary>

Set `NEXT_PUBLIC_USE_WHITELIST = FALSE` in your environmental variables in your Vercel settings at `https://vercel.com/[yourproject]/[yourrepo]/settings/environment-variables`.

</details>

<details>
  <summary>Can I host a Better board from a private repo?</summary>

Yes! Hosting a private repo allows you to keep issues private by default, until tagged to appear on the hosted site.

When using a private one, make sure to add our Github bot `betterhq-bot` as contributor to your repo.

</details>

<details>
  <summary>How to edit the issue labels?</summary>

  Better mirrors each Github issue based on its tags. The default tags are `open`, `inProgress`, `live`.
  If you want to set your own, edit the following files:
  - `\better-app\src\config.ts`
  - `src/features/issues/components/issues-list-page.tsx`
  - `src/features/issues/constants.ts`
  - `src/features/issues/types.ts`

</details>

<details>
  <summary>How to set custom Header text and Footer links?</summary>

Set your project name and custom footer links in this config file: `\better-app\src\config.ts`

</details>
