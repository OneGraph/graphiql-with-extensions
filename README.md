# GraphiQL with extensions

This is a meta-package meant to bring together the most popular GraphiQL plugins and make them easy to flip on and off.

The original GraphiQL package is consumable as a single React component, even without JSX. This makes it very easy to embed just about anywhere you can put JavaScript that might not have a full modern build pipeline (e.g. Rails with a sprockets setup).

Usage is easy:

```
npm install --save graphiql-with-extensions
# or
yarn add graphiql-with-extensions
```

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import GraphiQL from 'graphiql-with-extensions';
import fetch from 'isomorphic-fetch';

function graphQLFetcher(graphQLParams) {
  return fetch(window.location.origin + '/graphql', {
    method: 'post',
    headers: {'Content-Type': 'application/json'},
    body: JSON.stringify(graphQLParams),
  }).then(response => response.json());
}

ReactDOM.render(
  <GraphiQL
    fetcher={graphQLFetcher}
    // Some optional props
    // defaultQuery={''}
    // disableExplorer={false}
  />,
  document.body,
);
```

# Included extensions

Rigth now we only include the latest version of OneGraph's GraphiQL Explorer plugin. Please open an issue if you'd like to see other plugins included.

# Usage without build step

Easiest way you can use this to create one html file with customized authentication for your backend and serve it on some url. With that setup you don't
need to have npm or javascript ecosystem tools (if your backend is in different stack e.g. python, java, clojure). For minimal example of this approach see [static.html](examples/static.html)

## License

graphiql-with-extensions is licensed under the [MIT License](http://opensource.org/licenses/MIT).<br>
graphiql is licensed under the [MIT License](http://opensource.org/licenses/MIT).<br>
Documentation is licensed under [Creative Common License](http://creativecommons.org/licenses/by/4.0/).<br>

# graphiql-with-extensions
