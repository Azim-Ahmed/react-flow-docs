---
title: useUpdateNodeInternals
sidebar_position: 7
---

When you are **programatically changing the number or the position of handles inside a custom node** you need to notify React Flow about it with the `useUpdateNodeInternals` hook. It also updates the internal dimensions of a node. The hook returns a function that expects a `string` (node id) as a parameter.

:::caution

This hook can only be used if the component that uses it is wrapped with a [`ReactFlowProvider`](/docs/api/react-flow-provider/) or if it's a child of the `<ReactFlow />` component.

:::

### Usage

```javascript
import { useUpdateNodeInternals } from 'reactflow';

function UpdateNodeButton() {
  const updateNodeInternals = useUpdateNodeInternals();

  // you can pass a string or an array of strings to update multiple node internals
  return <button onClick={() => updateNodeInternals('node-id')}></button>;
}
```

### Typescript

The returned function has the type `UpdateNodeInternal = (nodeId: string | string[]) => void;`:

`useUpdateNodeInternals(): UpdateNodeInternals`
