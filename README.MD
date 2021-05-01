# React.js Concepts

## Introduction
React is a JavaScript library for building user interfaces. It is component-based, declarative, and designed to make it easier to create interactive, state-driven UIs. React focuses on rendering the UI efficiently by updating only the parts of the DOM that change.

## JSX
- JSX is a syntax extension for JavaScript that looks like HTML.
- It is compiled to `React.createElement()` calls.
- JSX allows writing UI markup and JavaScript expressions together.
- Examples:
  - `<div>Hello</div>`
  - `{condition && <span>Visible</span>}`

## Components
React apps are built from components.
- Functional components: plain functions that return JSX.
- Class components: ES6 classes with a `render()` method (less common in modern React).
- Components can be reused, nested, and composed.

## Props
- Props are inputs passed from parent to child components.
- They are read-only in the receiving component.
- Use props to make components configurable and reusable.
- Example: `<Button label="Submit" onClick={handleClick} />`

## State
- State is internal data that can change over time.
- In functional components, state is managed with `useState()`.
- Updating state causes the component to re-render.
- Example:
  - `const [count, setCount] = useState(0)`

## Lifecycle and Effects
- Functional components use `useEffect()` to run side effects.
- Common effect uses:
  - data fetching
  - subscriptions
  - DOM updates
- `useEffect()` can run:
  - after every render
  - only once on mount (`[]` dependency array)
  - when specific values change (`[value]`)
- Cleanup functions in `useEffect()` run before unmount or before the next effect.

## Common Hooks
- `useState()` — manage local state.
- `useEffect()` — handle side effects.
- `useContext()` — consume context values.
- `useReducer()` — manage complex state logic.
- `useMemo()` — memoize expensive results.
- `useCallback()` — memoize callback functions.
- `useRef()` — store mutable values or access DOM nodes.
- `useLayoutEffect()` — run effects synchronously after DOM updates.

## Events
- React normalizes events into a synthetic event system.
- Use camelCase event names: `onClick`, `onChange`, `onSubmit`.
- Prevent default browser behavior with `event.preventDefault()`.
- Example: `<button onClick={handleClick}>Click</button>`

## Conditional Rendering
- Render different UI based on state or props.
- Patterns include:
  - ternary expressions: `{isLoggedIn ? <Dashboard /> : <Login />}`
  - logical AND: `{hasItems && <ItemList />}`
  - early returns inside render functions.

## Lists and Keys
- Use arrays to render repeated UI.
- Provide a `key` prop to each item for efficient updates.
- Keys should be stable, unique identifiers.
- Example:
  - `{items.map(item => <Item key={item.id} data={item} />)}`

## Forms
- Controlled components: form element values come from React state.
- Use `value` and `onChange` props.
- Example:
  - `<input value={name} onChange={e => setName(e.target.value)} />`
- Uncontrolled components use refs to access DOM values.

## Context
- Context provides a way to share data without passing props through every component.
- Create context with `React.createContext()`.
- Provide values with `<Context.Provider value={...}>`.
- Consume context with `useContext(MyContext)`.

## Routing
- React Router is the most common solution for client-side routing.
- Key concepts:
  - `<BrowserRouter>` to wrap the app.
  - `<Routes>` and `<Route>` to define paths.
  - `useNavigate()` for navigation.
  - `useParams()` to read URL parameters.

## Performance
- React re-renders components when state or props change.
- Use memoization to prevent unnecessary work:
  - `React.memo()` for component memoization.
  - `useMemo()` for computed values.
  - `useCallback()` for callbacks.
- Keep state local to the smallest component that needs it.

## Reconciliation and Virtual DOM
- React uses a virtual DOM to compare tree differences.
- Reconciliation updates only changed parts of the UI.
- Keys are important so React can match elements between renders.

## Error Boundaries
- Error boundaries catch rendering errors in child components.
- They are implemented using class components with `componentDidCatch()`.
- Useful for preventing the entire app from crashing.

## Testing
- React Testing Library is commonly used for testing components.
- Test render output, user interaction, and accessibility.
- Jest is often used as the test runner.

## Styling
- Styling options include:
  - CSS files
  - CSS modules
  - styled-components or emotion
  - inline styles
  - utility-first libraries like Tailwind CSS

## Best Practices
- Keep components small and focused.
- Prefer functional components and hooks.
- Avoid mutating props and state directly.
- Lift state up only when necessary.
- Use composition instead of inheritance.
- Keep side effects in `useEffect()`.

## Advanced Concepts
- Higher-order components (HOCs) wrap components to add behavior.
- Render props pass functions as children for reusable logic.
- Portals render children into a DOM node outside the parent hierarchy.
- Suspense and `React.lazy()` support lazy loading and code splitting.
- Server-side rendering (SSR) with frameworks like Next.js.

## Learning Resources
- React official docs: https://reactjs.org
- Hooks docs: https://reactjs.org/docs/hooks-intro.html
- React Router docs: https://reactrouter.com
- React Testing Library: https://testing-library.com/docs/react-testing-library/intro
- MDN Web Docs for JavaScript and browser APIs

## Summary
React is a UI library built around declarative components. Learning React means understanding JSX, components, props, state, hooks, rendering behavior, and performance patterns. With these concepts, you can build scalable and maintainable user interfaces.
