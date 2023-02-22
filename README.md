# DEMO

- go to https://react-18-hydration-bug.onrender.com
- open it on safari mobile on an iPhone preferably. Seems to happen in mobile firefox, i believe they all use the same rendering engine.
- use the develop menu on safari on a mac to view the dev console.
- see the hydration error message
- refresh a few times if you do not see it

```
[Error] Warning: Text content did not match. Server: "this has a br and then a phone number: " Client: "this has a br and then a phone number: 1-800-GAMBLER. hydration cant handle this :("
section
ul
div
Index
RemixRoute@http://192.168.4.136:3000/build/_shared/chunk-5LP52SDM.js:4170:5
RenderedRoute@http://192.168.4.136:3000/build/_shared/chunk-5LP52SDM.js:2605:11
Outlet@http://192.168.4.136:3000/build/_shared/chunk-5LP52SDM.js:2765:25
body
html
App
RemixRoute@http://192.168.4.136:3000/build/_shared/chunk-5LP52SDM.js:4170:5
RenderedRoute@http://192.168.4.136:3000/build/_shared/chunk-5LP52SDM.js:2605:11
RenderErrorBoundary@http://192.168.4.136:3000/build/_shared/chunk-5LP52SDM.js:2952:14
Routes@http://192.168.4.136:3000/build/_shared/chunk-5LP52SDM.js:2827:12
Router@http://192.168.4.136:3000/build/_shared/chunk-5LP52SDM.js:2778:12
RouterProvider@http://192.168.4.136:3000/build/_shared/chunk-5LP52SDM.js:2725:11
RemixErrorBoundary@http://192.168.4.136:3000/build/_shared/chunk-5LP52SDM.js:3798:10
RemixBrowser@http://192.168.4.136:3000/build/_shared/chunk-5LP52SDM.js:5106:55
	printWarning (entry.client-RJ24HZSS.js:524)
	error (entry.client-RJ24HZSS.js:508)
	checkForUnmatchedText (entry.client-RJ24HZSS.js:7063)
	didNotMatchHydratedTextInstance (entry.client-RJ24HZSS.js:8332)
	prepareToHydrateHostTextInstance (entry.client-RJ24HZSS.js:9200)
	completeWork (entry.client-RJ24HZSS.js:15851)
	completeUnitOfWork (entry.client-RJ24HZSS.js:18719)
	performUnitOfWork (entry.client-RJ24HZSS.js:18704)
	workLoopConcurrent (entry.client-RJ24HZSS.js:18687)
	renderRootConcurrent (entry.client-RJ24HZSS.js:18662)
	performConcurrentWorkOnRoot (entry.client-RJ24HZSS.js:18178)
	performConcurrentWorkOnRoot
	workLoop (entry.client-RJ24HZSS.js:200)
	flushWork (entry.client-RJ24HZSS.js:179)
	performWorkUntilDeadline (entry.client-RJ24HZSS.js:387)
```

## Development

From your terminal:

```sh
npm run dev
```

This starts your app in development mode, rebuilding assets on file changes.

## Deployment

First, build your app for production:

```sh
npm run build
```

Then run the app in production mode:

```sh
npm start
```

Now you'll need to pick a host to deploy it to.

### DIY

If you're familiar with deploying node applications, the built-in Remix app server is production-ready.

Make sure to deploy the output of `remix build`

- `build/`
- `public/build/`

### Using a Template

When you ran `npx create-remix@latest` there were a few choices for hosting. You can run that again to create a new project, then copy over your `app/` folder to the new project that's pre-configured for your target server.

```sh
cd ..
# create a new project, and pick a pre-configured host
npx create-remix@latest
cd my-new-remix-app
# remove the new project's app (not the old one!)
rm -rf app
# copy your app over
cp -R ../my-old-remix-app/app app
```
