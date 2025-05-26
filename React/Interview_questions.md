
# 100 React.js Interview Questions 

Basic Questions

# 1. What is React?
Answer: React is a JavaScript library created by Facebook for building user interfaces, particularly single page applications. 
It uses a virtual DOM and component-based architecture for efficient rendering.

# 2. What are the key features of React?
Answer: 
- Virtual DOM
- Component-based architecture 
- Unidirectional data flow
- JSX
- React Native support
- Rich ecosystem

# 3. What is JSX?
Answer: JSX is a syntax extension for JavaScript that allows you to write HTML-like code within JavaScript. 
It gets transformed to regular JavaScript at runtime.

# 4. What is the virtual DOM?
Answer: Virtual DOM is a lightweight copy of the actual DOM. React uses it to improve performance by minimizing direct 
manipulation of the actual DOM.

# 5. What are React components?
Answer: Components are reusable, self-contained pieces of code that return React elements. They can be either 
class-based or functional.

# 6. What is the difference between state and props?
Answer:
Props: Read-only, passed from parent to child
State: Managed within component, can be changed using setState()

# 7. What are controlled and uncontrolled components?
Answer:
Controlled: Form data controlled by React state
Uncontrolled: Form data handled by DOM itself

# 8. What are React Hooks?
Answer: Hooks are functions that allow you to use state and other React features in functional components.
Example: useState, useEffect, useContext, etc.

# 9. What is useState Hook?
Answer: useState is a Hook that allows functional components to manage state.
const [state, setState] = useState(initialValue);

# 10. What is useEffect Hook?
Answer: useEffect handles side effects in functional components like data fetching, subscriptions, or DOM manipulation.
useEffect(() => {
  effect
  return () => {
    cleanup
  }
}, [dependencies]);

Intermediate Questions

# 11. Explain React component lifecycle methods
Answer: Key lifecycle methods include:
- componentDidMount()
- componentDidUpdate()
- componentWillUnmount()
- getDerivedStateFromProps()
- shouldComponentUpdate()

# 12. What is the Context API?
Answer: Context provides a way to pass data through the component tree without manually passing props.
const MyContext = React.createContext(defaultValue);

# 13. What is Redux?
Answer: Redux is a state management library that helps manage application state in a predictable way using actions and reducers.

# 14. What are Higher-Order Components (HOC)?
Answer: HOCs are functions that take a component and return a new component with additional props or behavior.
const withAuth = (WrappedComponent) => {
  return class extends React.Component {
    Enhanced component logic
  }
}

# 15. What is React Router?
Answer: React Router is a standard routing library for React applications to handle navigation.

# 16. What are React Fragments?
Answer: Fragments let you group children elements without adding extra nodes to the DOM.
<React.Fragment>
  <ChildA />
  <ChildB />
</React.Fragment>

# 17. What is prop drilling?
Answer: Prop drilling occurs when props are passed through multiple levels of components that don't need them.

# 18. What is the useCallback Hook?
Answer: useCallback returns a memoized version of a callback to optimize performance.
const memoizedCallback = useCallback(
  () => {
    doSomething(a, b);
  },
  [a, b],
);

# 19. What is the useMemo Hook?
Answer: useMemo memoizes computed values to optimize performance.
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);

# 20. What is the useRef Hook?
Answer: useRef returns a mutable ref object that persists across re-renders.
const inputRef = useRef(null);

Advanced Questions

# 21. Explain React Fiber
Answer: React Fiber is the new reconciliation engine introduced in React 16 for better rendering performance.

# 22. What is code splitting in React?
Answer: Code splitting allows splitting code into smaller chunks for better performance.
const MyComponent = React.lazy(() => import('./MyComponent'));

# 23. What are Error Boundaries?
Answer: Error Boundaries are components that catch JavaScript errors in child components.
class ErrorBoundary extends React.Component {
  componentDidCatch(error, errorInfo) {
    Handle error
  }
}

# 24. What is Server-Side Rendering (SSR)?
Answer: SSR renders React components on the server instead of client for better SEO and performance.

# 25. What are React Portals?
Answer: Portals allow rendering children into a DOM node outside of parent hierarchy.
ReactDOM.createPortal(child, container);

# 26. Explain React's Strict Mode
Answer: StrictMode is a development tool for highlighting potential problems in an application.

# 27. What is the useReducer Hook?
Answer: useReducer manages complex state logic using reducer functions.
const [state, dispatch] = useReducer(reducer, initialState);

# 28. What are Custom Hooks?
Answer: Custom Hooks are reusable functions that contain component logic.
function useCustomHook() {
  Hook logic
}

# 29. What is React Suspense?
Answer: Suspense lets components wait for something before rendering.
<Suspense fallback={<Loading />}>
  <Component />
</Suspense>

# 30. What is Redux Middleware?
Answer: Middleware provides a third-party extension point between dispatching an action and reaching the reducer.

Performance Optimization Questions

# 31. How to prevent re-renders in React?
Answer: Use React.memo, shouldComponentUpdate, or PureComponent

# 32. What is React.memo()?
Answer: React.memo is a HOC that prevents unnecessary re-renders of functional components.
const MemoizedComponent = React.memo(Component);

# 33. Explain useLayoutEffect
Answer: useLayoutEffect fires synchronously after DOM mutations, unlike useEffect.

# 34. What is the difference between useMemo and useCallback?
Answer: useMemo memoizes values, useCallback memoizes functions.

# 35. How to optimize React performance?
Answer: 
- Use production builds
- Implement virtualization
- Use React.memo and useMemo
- Proper key usage in lists
- Code splitting

State Management Questions

# 36. Compare Redux vs Context API
Answer: Redux for complex state management, Context for simpler cases.

# 37. What is Redux Thunk?
Answer: Middleware for handling asynchronous actions in Redux.

# 38. What is Redux Saga?
Answer: Middleware for managing side effects in Redux applications.

# 39. Explain Redux reducers
Answer: Pure functions that specify how state updates in response to actions.

# 40. What is Redux DevTools?
Answer: Browser extension for debugging Redux applications.

Testing Questions

# 41. What testing libraries do you use with React?
Answer: Jest, React Testing Library, Enzyme

# 42. How to test React components?
Answer: Using React Testing Library:
render(<Component />);
expect(screen.getByText('Hello')).toBeInTheDocument();

# 43. What is snapshot testing?
Answer: Captures component output and compares it to stored reference.

# 44. How to test custom hooks?
Answer: Using @testing-library/react-hooks:
const { result } = renderHook(() => useCustomHook());

# 45. How to test Redux connected components?
Answer: Using Provider wrapper and mock store.

Architecture and Patterns

# 46. Explain Flux architecture
Answer: Unidirectional data flow pattern that inspired Redux.

# 47. What are React design patterns?
Answer: Container/Presentational, HOC, Render Props, Custom Hooks

# 48. What is the Container pattern?
Answer: Separates data fetching from presentation components.

# 49. What are Render Props?
Answer: Pattern where a component's prop is a function that returns elements.

# 50. What is the Provider pattern?
Answer: Makes data available to multiple nested components.

Security Questions

# 51. How to handle XSS in React?
Answer: React automatically escapes values in JSX.

# 52. What is CSRF protection in React?
Answer: Include CSRF tokens in API requests.

# 53. How to secure React applications?
Answer: Use HTTPS, sanitize inputs, implement authentication.

# 54. What are security best practices?
Answer: Regular updates, dependency audits, proper error handling.

# 55. How to handle sensitive data?
Answer: Never store in state, use secure storage methods.

Deployment Questions

# 56. How to deploy React applications?
Answer: Using platforms like Netlify, Vercel, AWS, or traditional hosting.

# 57. What is code splitting?
Answer: Splitting bundle into smaller chunks for better loading.

# 58. How to optimize bundle size?
Answer: Tree shaking, code splitting, lazy loading.

# 59. What is lazy loading?
Answer: Loading components only when needed.

# 60. What are environment variables in React?
Answer: Configuration values set during build/runtime.

Advanced Concepts

# 61. What are React Hooks rules?
Answer: Only call at top level, only call from React functions.

# 62. What is the useImperativeHandle Hook?
Answer: Customizes instance value exposed to parent components.

# 63. What is the useDebugValue Hook?
Answer: Displays label for custom hooks in React DevTools.

# 64. What are React concurrent features?
Answer: New features for better user experience and responsiveness.

# 65. What is Suspense for data fetching?
Answer: Declarative way to handle loading states.

State Management Deep Dive

# 66. What is Redux Toolkit?
Answer: Official toolset for efficient Redux development.

# 67. What is MobX?
Answer: Alternative state management library using observables.

# 68. What is Recoil?
Answer: Facebook's experimental state management library.

# 69. What is Zustand?
Answer: Lightweight state management solution.

# 70. Compare different state management solutions
Answer: Based on complexity, team size, and requirements.

Performance Deep Dive

# 71. What causes React re-renders?
Answer: Props changes, state updates, context changes.

# 72. How to debug performance issues?
Answer: React DevTools Profiler, Performance monitoring.

# 73. What is tree shaking?
Answer: Removing unused code from bundle.

# 74. What is code splitting best practices?
Answer: Split by route, component, or functionality.

# 75. How to implement infinite scrolling?
Answer: Using Intersection Observer and pagination.

Testing Deep Dive

# 76. What is Test Driven Development in React?
Answer: Writing tests before implementing features.

# 77. How to mock API calls in tests?
Answer: Using Jest mock functions or MSW.

# 78. What is integration testing?
Answer: Testing multiple components together.

# 79. What is end-to-end testing?
Answer: Testing complete user flows.

# 80. How to test error boundaries?
Answer: Simulating errors in child components.

Architecture Deep Dive

# 81. What is micro-frontend architecture?
Answer: Breaking application into smaller, independent apps.

# 82. What is module federation?
Answer: Sharing code between multiple applications.

# 83. What is server-side rendering architecture?
Answer: Rendering React on server for initial load.

# 84. What is JAMstack?
Answer: JavaScript, APIs, and Markup architecture.

# 85. What is isomorphic React?
Answer: Code that runs both on client and server.

Advanced Patterns

# 86. What is the Compound Component pattern?
Answer: Components that work together for complex functionality.

# 87. What is the State Reducer pattern?
Answer: Giving control of state updates to users.

# 88. What is the Control Props pattern?
Answer: Controlling component state through props.

# 89. What is the Props Getter pattern?
Answer: Providing props with additional functionality.

# 90. What is the State Initializer pattern?
Answer: Providing initial state and reset functionality.

React Ecosystem

# 91. What is Next.js?
Answer: React framework for production applications.

# 92. What is Gatsby?
Answer: Static site generator for React.

# 93. What is React Native?
Answer: Framework for building native mobile apps.

# 94. What is Material-UI?
Answer: Popular React UI component library.

# 95. What is Styled-components?
Answer: CSS-in-JS library for React.

Future of React

# 96. What is React Server Components?
Answer: New way to build React apps with server-side rendering.

# 97. What is React Forget?
Answer: Upcoming compiler optimization feature.

# 98. What is React Flight?
Answer: New streaming server renderer.

# 99. What are React hooks improvements?
Answer: Upcoming changes to hooks system.

# 100. What is the future of React?
Answer: Server components, concurrent features, improved performance.