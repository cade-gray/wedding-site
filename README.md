# Wedding Website

I built this for mine and my partner's wedding. View the site [here](https://wedding.cadegray.dev 'Our wedding website')
This can be used as a template for other couple's future wedding websites if desired (with at least some sort of credit).
The app is built using SvelteKit and implements the static adaptor, so this can be deployed as a SPA with static files.
It interacts with an API that I built using ExpressJS which interacts with a MySQL DB on PlanetScale.
I have it deployed on my person digital ocean droplet on a nginx server block.
SVG's are also a heavily used in here for the design aspect such as the logos and the background. All was done using Figma and a Wacom tablet.
A video explaining the process of building this will be made in the future and posted on my youtube channel.

## Developing

Install the dependencies with npm install and then use the below commands to start the dev server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a build folder for the wedding site run the below command:

```bash
npm run build
```
