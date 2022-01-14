
# Next.js w/ Custom Express Server example for Heroku

## How to use

```bash
git clone https://github.com/mars/heroku-nextjs-custom-server-express
cd heroku-nextjs-custom-server-express
```

Install it and run:

```bash
npm install
npm run dev
```

Then, visit [http://localhost:3000/](http://localhost:3000/) in your web browser.

Deploy it to the cloud with [Heroku](https://www.heroku.com):

⚠️ *Requires installing [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)*

```bash
heroku create
git add .
git commit -m 'Next.js app on Heroku'
git push heroku master
```

Heroku auto-detects that this is a Node.js app, and then executes:

* `npm install`
* `npm run build`
* and then launches the app `NODE_ENV=production npm start`.

👉 An example deployment of master is running at [https://nextjs-server.herokuapp.com/](https://nextjs-server.herokuapp.com/).

## The idea behind the example

*A version of [Next's example/custom-server-express](https://github.com/zeit/next.js/tree/master/examples/custom-server-express) revised to [deploy to Heroku](https://github.com/mars/heroku-nextjs).*

Most of the times the default Next server will be enough but sometimes you want to run your own server to customize routes or other kind of the app behavior. Next provides a [Custom server and routing](https://github.com/zeit/next.js#custom-server-and-routing) so you can customize as much as you want.

Because the Next.js server is just a node.js module you can combine it with any other part of the node.js ecosystem. in this case we are using express to build a custom router on top of Next.

The example shows a server that serves the component living in `pages/a.js` when the route `/b` is requested and `pages/b.js` when the route `/a` is accessed. This is obviously a non-standard routing strategy. You can see how this custom routing is being made inside `server.js`.
