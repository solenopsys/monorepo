
## Create Links to Your Routes

Use the `A` component to create an anchor tag that takes you to a route:

```jsx
import { lazy } from  "@solenopsys/converged-renderer";
import { Routes, Route, A } from "@solenopsys/converged-router"
const Users = lazy(() => import("./pages/Home"));
const Home = lazy(() => import("./pages/Users"));

export default function App() {
  return (
    <>
      <h1>My Site with Lots of Pages</h1>
      <nav>
        <A href="/about">About</A>
        <A href="/">Home</A>
      </nav>
      <Routes>
        <Route path="/users" element={<Users/>} />
        <Route path="/" element={<Home/>} />
        <Route path="/about" element={<div>This site was made with Converged-Renderer</div>} />
      </Routes>
    <>
  )
}
```

The `<A>` tag also has an `active` class if its href matches the current location, and `inactive` otherwise. **Note:** By default matching includes locations that are descendents (eg. href `/users` matches locations `/users` and `/users/123`), use the boolean `end` prop to prevent matching these. This is particularly useful for links to the root route `/` which would match everything.

| prop     | type    | description                                                                                                                                                                              |
|----------|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| href     | string  | The path of the route to navigate to. This will be resolved relative to the route that the link is in, but you can preface it with `/` to refer back to the root.                                                                                                                                                    |
| noScroll | boolean | If true, turn off the default behavior of scrolling to the top of the new page                                                                                                           |
| replace  | boolean | If true, don't add a new entry to the browser history. (By default, the new page will be added to the browser history, so pressing the back button will take you to the previous route.) |
| state    | unknown | [Push this value](https://developer.mozilla.org/en-US/docs/Web/API/History/pushState) to the history stack when navigating  |
| inactiveClass | string  | The class to show when the link is inactive (when the current location doesn't match the link) |
| activeClass | string | The class to show when the link is active                                                                                                        |
| end  | boolean | If `true`, only considers the link to be active when the curent location matches the `href` exactly; if `false`, check if the current location _starts with_ `href` |

