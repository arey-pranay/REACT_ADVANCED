<p align="center">
  <a href="https://github.com/arey-pranay/REACT_ADVANCED">
    <img alt="React" src="https://img.shields.io/badge/React-advanced-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" />
  </a>
  <a href="https://github.com/arey-pranay/REACT_ADVANCED">
    <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-typed_APIs-3178C6?style=for-the-badge&logo=typescript&logoColor=white" />
  </a>
  <a href="https://www.udemy.com/course/advanced-react">
    <img alt="Course path" src="https://img.shields.io/badge/path-senior_React-61DAFB?style=for-the-badge" />
  </a>
</p>

<h1 align="center">REACT ADVANCED</h1>

<p align="center">
  A senior React lab: design patterns, hooks, clean code, API architecture,<br />
  layout systems, and TypeScript — each idea in its own folder, with a note beside the code.
</p>

<p align="center">
  <a href="#how-to-use-this-repo">How to use it</a> ·
  <a href="#curriculum">Curriculum</a> ·
  <a href="#pattern-index">Pattern index</a> ·
  <a href="#layout-system">Layout system</a> ·
  <a href="#suggested-paths">Suggested paths</a>
</p>

---

This is a curriculum of small, isolated examples. Open a folder, read the local note, then read the component. Nothing here depends on a giant app shell.

The notes follow the [Advanced React](https://www.udemy.com/course/advanced-react) course path. The writing and examples in this repository are the study record.

## How to use this repo

1. Pick a module from the [curriculum](#curriculum). Numbers run from foundations to TypeScript.
2. Open the lesson folder. Most lessons ship a `readme.md` next to the component: what the pattern is, why it exists, and the smallest code that shows it.
3. Treat each example as a reference you can lift. Layout, data loading, and presentation stay in separate pieces on purpose.

There is no install step for the notes. JSX and TSX files are snippets meant to be read, or dropped into a React app you already have.

## Curriculum

| | Module | You leave with |
|---|---|---|
| 01 | [Design Patterns](#01--design-patterns) | Components that compose, load data, and share logic without inheritance |
| 02 | [Advanced Concepts and Hooks](#02--advanced-concepts-and-hooks) | Portals, errors, keys, effects, concurrent rendering, and async routing |
| 03 | [Clean Code](#03--clean-code) | Props that match the DOM, context that rerenders less, effects that stay honest |
| 04 | [API Layering](#04--api-layering) | A request lifecycle you can draw, then TanStack Query on top of it |
| 05 | [Performance](#05--performance-optimization) | Smaller bundles, fewer wasted renders, calmer event handlers |
| 06 | [Spacing Patterns](#06--spacing-patterns) | A design system made of layout primitives, not one-off CSS |
| 07 | [TypeScript](#07--typescript) | Props, state, refs, reducers, context, generics, and polymorphic APIs |
| 08 | [Bonus](#09--bonus) | Wrappers, polymorphic components, and clickable cards done accessibly |

---

## 01 — Design Patterns

Composition first. Each pattern answers one question: who owns layout, who owns data, and who owns behavior.

### Layout

| Lesson | Idea |
|---|---|
| [Split Screen](<01. Design Patterns/01. Layout Components/01. Split Screen>) | A layout component splits the viewport and lets the parent decide both sides. |
| [List Items](<01. Design Patterns/01. Layout Components/02. List Items>) | One list shell, many item shapes — authors and books, large and small. |
| [Modals](<01. Design Patterns/01. Layout Components/03. Modals>) | The modal owns the frame. The caller owns the content. |

### Data and control

| Lesson | Idea |
|---|---|
| [Resource Loader](<01. Design Patterns/02. Container Components/01. ResourceLoader>) | A container fetches. The child only renders. |
| [DataSource + render pattern](<01. Design Patterns/02. Container Components/02. ResourceLoader adv. (DataSource and RenderPattern used)>) | The same loader, generalized with a data source and a render function. |
| [Controlled and uncontrolled forms](<01. Design Patterns/03. Controlled and Uncontrolled Components/01. Forms>) | React state as the source of truth, or the DOM with a ref. |
| [Controlled and uncontrolled modals](<01. Design Patterns/03. Controlled and Uncontrolled Components/02. Modals>) | The parent can own `isOpen`, or the modal can own it. |
| [Controlled and uncontrolled flows](<01. Design Patterns/03. Controlled and Uncontrolled Components/03. Flows>) | Multi-step flows with the same choice: outside state, or inside. |

### Sharing logic

| Lesson | Idea |
|---|---|
| [HOCs](<01. Design Patterns/04. Higher Order Components>) | A function that takes a component and returns a component. Named in camelCase, because you call it, you do not mount it. |
| [Logging wrapper](<01. Design Patterns/04. Higher Order Components/01. LoggingWrapper>) | Cross-cutting behavior (prop checks) wrapped around a component. |
| [Data loader HOC](<01. Design Patterns/04. Higher Order Components/02. DataLoader>) | `includeUser` injects fetched data as props. |
| [Data updater HOC](<01. Design Patterns/04. Higher Order Components/03. DataUpdater>) | The wrapper also hands back a way to change the resource. |
| [User form HOC](<01. Design Patterns/04. Higher Order Components/04. UserForm>) | Form behavior extracted so the view stays thin. |
| [Generalized resource HOC](<01. Design Patterns/04. Higher Order Components/05. EnhancementAndGeneralization>) | The same idea, no longer hard-coded to users. |
| [Custom hooks](<01. Design Patterns/05. Custom Hooks/01. GenericDataFetcherHook>) | The modern version of the loaders above: `useDataSource` and `useResource`, no wrapper in the tree. |

### Functional style

| Lesson | Idea |
|---|---|
| [Recursive components](<01. Design Patterns/06. Functional Programming/01. Recursive components>) | A component renders itself until the tree runs out. |
| [Composition](<01. Design Patterns/06. Functional Programming/02. Composition Components>) | Specialized components built by combining smaller ones. |
| [Partial application](<01. Design Patterns/06. Functional Programming/03. Partial(ly Applied) Components>) | Pre-fill props once, get a narrower component back. |
| [Compound components](<01. Design Patterns/07. Compound Components>) | `Card.Header`, `Card.Body` — related pieces that share state through context, composed by the caller. |
| [Observer / event bus](<01. Design Patterns/08. Observer Pattern>) | `mitt` lets distant components talk with events when they are not parent and child. |

---

## 02 — Advanced Concepts and Hooks

The APIs that show up once an app is real: things that escape the tree, survive bad children, and stay responsive while work is in flight.

| Lesson | Idea |
|---|---|
| [Portals](<02. Advanced Concepts and Hooks/01. React Portals>) | Render into another DOM node with `createPortal`, while staying in the React tree. |
| [Error boundaries](<02. Advanced Concepts and Hooks/02. Error Boundaries>) | Catch render errors in a subtree and show a fallback. |
| [Keys](<02. Advanced Concepts and Hooks/03. Keys in React>) | Identity. Keys decide whether React reuses a component or resets it. |
| [Event listeners](<02. Advanced Concepts and Hooks/04. Event Listeners>) | Subscribe in an effect, and unsubscribe on the way out. |
| [`useLayoutEffect`](<02. Advanced Concepts and Hooks/05. useLayoutEffect()>) | Read and write layout before the browser paints. |
| [`useId`](<02. Advanced Concepts and Hooks/06. useId()>) | Stable ids for labels and accessibility, safe under SSR. |
| [`useCallback` as a ref](<02. Advanced Concepts and Hooks/07. useCallback as Ref>) | A callback ref when you need setup the moment a node mounts. |
| [`useDeferredValue`](<02. Advanced Concepts and Hooks/08. useDeferredValue()>) | Keep typing snappy while a heavy child catches up. |
| [`useTransition`](<02. Advanced Concepts and Hooks/09. useTransition()>) | Mark an update as non-urgent and show pending UI while it runs. |
| [Async React Router](<02. Advanced Concepts and Hooks/10. Async React Router>) | `lazy` + `Suspense` for code, `defer` + `Await` for data. The two waits stay independent. |

---

## 03 — Clean Code

| Lesson | Idea |
|---|---|
| [Element props](<03. Clean Code/01. Element Props Usage>) | Spread DOM props, name the ones that are yours, and stop inventing a second API for `className` and `onClick`. |
| [Context that scales](<03. Clean Code/02. Optimizing Context API>) | Split state and dispatch so a cart button does not rerender the whole tree. |
| [`useEffect`, properly](<03. Clean Code/useEffect().md>) | A long note on effects: synchronization, dependencies, and the cases that are not effects. |

---

## 04 — API Layering

Two notes, in the order you should read them.

| Note | Idea |
|---|---|
| [API states and fetching](<04. API Layering/readme.md>) | `idle → loading → success \| error`. Where the request lives, and how the UI represents each state. |
| [TanStack Query](<04. API Layering/tanstack-query(react-query).md>) | The same lifecycle, with cache, mutations, cancellation, pagination, infinite scroll, and optimistic updates. Query is the client. Express is still the API. |

---

## 05 — Performance Optimization

| Note | Idea |
|---|---|
| [Code splitting, lazy, Suspense](<05. Performance Optimization/01. Code Splitting, lazy loading, dynamic and suspense.md>) | Splitting decides *how* JS is cut. Lazy decides *when* it loads. Suspense decides what to show while it is not ready. |
| [`memo`, `useCallback`, `useMemo`](<05. Performance Optimization/02. memo() and useCallback to prevent re-renders.md>) | A rerender is normal. The work to remove is the subtree that did not need to run. |
| [Throttle and debounce](<05. Performance Optimization/03. Throttle and Debounce.md>) | Scroll, resize, and input fire too often. These two decide *when* the handler is allowed to run. |

---

## 06 — Spacing Patterns

A layout system in React. Each primitive answers one question: **what relationship do these children have?**

Styled components hold the CSS. Props hold the exceptions. Call sites read like a sketch of the page.

| Primitive | Relationship | Folder |
|---|---|---|
| Layers | Things stacked in the same box, one on top of another | [layers](<06. Spacing Patterns (Design System)/1-layers-pattern>) |
| Split | Left and right, sharing a row | [split](<06. Spacing Patterns (Design System)/2-split-pattern>) |
| Columns | Equal vertical bands | [columns](<06. Spacing Patterns (Design System)/3-column-pattern>) |
| Grid | Rows and columns together | [grid](<06. Spacing Patterns (Design System)/4-grid-pattern>) |
| Inline bundle | A row that wraps as a group | [inline bundle](<06. Spacing Patterns (Design System)/5-inline-bundle>) |
| Inline | Icon, text, badge — items in a line | [inline](<06. Spacing Patterns (Design System)/6-inline-pattern>) |
| Pad | Space inside a box | [pad](<06. Spacing Patterns (Design System)/7-pad-pattern>) |
| Center | Content in the middle of its parent | [center](<06. Spacing Patterns (Design System)/8-center-pattern>) |
| Media wrapper | A frame that keeps a ratio | [media wrapper](<06. Spacing Patterns (Design System)/9-media-wrapper-pattern>) |
| Cover | A centered subject with space above and below | [cover](<06. Spacing Patterns (Design System)/10-cover-pattern>) |

Shared spacing tokens live in [`common/spaces.js`](<06. Spacing Patterns (Design System)/common/spaces.js>).

Read [the layout note](<06. Spacing Patterns (Design System)/readme.md>) for the primitives, and [theory](<06. Spacing Patterns (Design System)/theory.md>) for why the spacing scale exists. Then look at the assembled pages:

- [Final project](<06. Spacing Patterns (Design System)/final-project>) — sidebar, menu, content, built only from the primitives
- [Second pass](<06. Spacing Patterns (Design System)/11-final-project>)
- [Modal project](<06. Spacing Patterns (Design System)/12-modal-project>)

```jsx
<Stack gap="1rem">
  <Split>
    <Title />
    <Actions />
  </Split>
</Stack>
```

---

## 07 — TypeScript

Regular notes first, then the React-specific type problems.

### Regular

| Note | Idea |
|---|---|
| [Intro and props](<07. TypeScript - Regular/1. Intro and Props.md>) | Props, children, callbacks, events, and variants. The skill is describing the API, not memorizing syntax. |
| [Depth and detailing](<07. TypeScript - Regular/2. Depth and Detailing.md>) | Narrower types, and the details that make a component API hard to misuse. |

### Advanced

| Note | Idea |
|---|---|
| [`useState` types](<08. Typescript - Advanced/01. types with useState().md>) | What you store, and what `setState` is allowed to receive. |
| [Refs and custom hooks](<08. Typescript - Advanced/02. Refs and CustomsHooks Types.md>) | `RefObject` versus callback refs, and the return type of a hook. |
| [`useReducer`](<08. Typescript - Advanced/03. useReducer() dispatch, actions, and template literals with types.md>) | Actions as a union, dispatch that only accepts those actions, template-literal types where they help. |
| [Context](<08. Typescript - Advanced/04. types with context API.md>) | A typed provider, and a hook that refuses to run outside it. |
| [Utilities](<08. Typescript - Advanced/05. Typescript utilities.md>) | `Partial`, `Pick`, `Omit`, `Record`, and the rest of the toolbox. |
| [Generics and overloads](<08. Typescript - Advanced/06. Generics, Type Helpers, Interfaces, Hooks & Function Overload.md>) | Hooks and helpers that keep the caller's type all the way through. |
| [HOCs](<08. Typescript - Advanced/07. HOCs and TS.md>) | Wrapping a component without losing its props. |
| [Render props and hooks](<08. Typescript - Advanced/08. Render Props and Custom Hooks.md>) | The same data-loading ideas from module 01, with the types filled in. |
| [Prop composition](<08. Typescript - Advanced/09. Prop Composition.md>) | Building a props type out of smaller ones, including the underlying element. |

---

## 09 — Bonus

| Note | Idea |
|---|---|
| [Wrapper components](<09. Bonus/01. Wrapper Components.md>) | A shell that owns chrome. The child still owns its own job. |
| [Polymorphic components](<09. Bonus/02. Polymorphic Components.md>) | One `Text` that can render as `h1`, `p`, or `span`, with the right props for whichever element you pick. |
| [Clickable cards](<09. Bonus/03. Divs should generally not be clickable.md>) | Navigation is a link. An action is a button. CSS stretches that element across the card. |

---

## Pattern index

A one-line map when you already know the name.

| You want… | Open |
|---|---|
| Layout separated from content | [Split Screen](<01. Design Patterns/01. Layout Components/01. Split Screen>) |
| The same list for different data | [List Items](<01. Design Patterns/01. Layout Components/02. List Items>) |
| Fetching kept out of the view | [Resource Loader](<01. Design Patterns/02. Container Components/01. ResourceLoader>) or [custom hooks](<01. Design Patterns/05. Custom Hooks/01. GenericDataFetcherHook>) |
| React state vs the DOM | [Forms](<01. Design Patterns/03. Controlled and Uncontrolled Components/01. Forms>) |
| Behavior wrapped around a component | [HOCs](<01. Design Patterns/04. Higher Order Components>) |
| A component API that reads like HTML | [Compound components](<01. Design Patterns/07. Compound Components>) |
| Two components that should not know each other | [Event bus](<01. Design Patterns/08. Observer Pattern>) |
| UI outside the parent DOM node | [Portals](<02. Advanced Concepts and Hooks/01. React Portals>) |
| A crash contained to one subtree | [Error boundaries](<02. Advanced Concepts and Hooks/02. Error Boundaries>) |
| Typing that stays fast while a list is slow | [`useDeferredValue`](<02. Advanced Concepts and Hooks/08. useDeferredValue()>) |
| Code and data loading, separately | [Async React Router](<02. Advanced Concepts and Hooks/10. Async React Router>) |
| Server state with a cache | [TanStack Query](<04. API Layering/tanstack-query(react-query).md>) |
| A page built from spacing primitives | [Layout system](<06. Spacing Patterns (Design System)/readme.md>) |
| A component that renders as any element | [Polymorphic components](<09. Bonus/02. Polymorphic Components.md>) |

## Suggested paths

**A weekend, in order.** Design patterns → hooks → clean code. Stop at compound components and `useTransition` if time runs out. Those two repay a slow read.

**An interview week.** Pattern index first. Then controlled vs uncontrolled, custom hooks, context splitting, keys, error boundaries, and the performance notes. Explain each one out loud before opening the next folder.

**A design-system week.** Module 06 from layers through cover, then the final project. After that, polymorphic components and prop composition, so the primitives have a typed public API.

**Already comfortable with patterns.** Start at [TypeScript — regular](<07. TypeScript - Regular/1. Intro and Props.md>) and read straight through module 08. The earlier folders are the untyped versions of the same ideas.

## Topics in this repo

`react` · `design patterns` · `compound components` · `higher-order components` · `custom hooks` · `render props` · `context` · `portals` · `error boundaries` · `concurrent rendering` · `react router` · `tanstack query` · `styled-components` · `design systems` · `typescript`

---

<p align="center">
  Notes and examples by <a href="https://github.com/arey-pranay">arey-pranay</a>
</p>
