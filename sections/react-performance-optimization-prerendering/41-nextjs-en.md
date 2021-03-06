# Next.js

## create-next-app

Create a new next.js app via:

```bash
npx create-next-app my-app
```

## Folder structure

- pages under _./pages_
- static assets under _./assets_
- used React components usually under _./components_

## Development server

```bash
npm run dev
```

An auto-updating server will start at _localhost:3000_

## Deployment with node.js

to build a production version:

```bash
npm run build
```

to run it:

```bash
npm run start
```

(requires node.js on the server)

## Deployment to a static server

change the _build_ script in _package.json_ to: `next build && next export`

then build the static version (to the _out_ folder) via:

```bash
npm run build
```

(see <https://nextjs.org/learn/excel/static-html-export>)

## Creating pages

Example page definition:

```js
// pages/index.js
import Link from 'next/link';

const Index = () => (
  <div>
    <Link href="/about">
      <a>About Page</a>
    </Link>
    <p>Hello Next.js</p>
  </div>
);

export default Index;
```

## Creating pages

Task: create further pages

## Route parameters

we can query parameters from URLs like these:

- `/posts/?postid=3`
- `/posts/3`

## Route parameters

Route parameters are enclosed in square brackets in the file name, e.g. `pages/posts/[id].js`

## Route parameters

Querying route parameters:

```js
import { useRouter } from 'next/router';

const Post = () => {
  const router = useRouter();
  return (
    <div>
      <h1>detail view for post {router.query.id}</h1>
    </div>
  );
};

export default Post;
```

## Data fetching in next.js

usual process for fetching data in a React app:

- React app is sent to the client
- React app renders initially with no data
- client requests additional data
- data is sent to the client

process with next.js:

- data is fetched on the server
- app is rendered on the server
- pre-rendered app and the corresponding data for making it dynamic are sent to the client

## Data fetching in next.js

Fetching data for rendering a page:

- fetch static data via `getStaticProps` (during the build)
- fetch server-side dynamic data for pre-rendering via `getServerSideProps`

For using `fetch` in node.js we can use the npm Package `isomorphic-fetch`

## Data fetching in next.js

```js
// pages/pokemon.js
export default ({ pokemon }) => {
  return (
    <ul>
      {pokemon.map((pokemon) => (
        <li key={pokemon.name}>{pokemon.name}</li>
      ))}
    </ul>
  );
};

export const getStaticProps = async () => {
  const res = await fetch(
    'https://pokeapi.co/api/v2/pokemon'
  );
  const pokemon = (await res.json()).results;
  return { props: { pokemon: pokemon } };
};
```

## Resources

The next.js website has great materials: https://nextjs.org
