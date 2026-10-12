# Architectural Rules: Next.js App Router

1. **State Management**: Prefer server state URL search parameters (`useSearchParams` or page props) over in-memory React state for filter, sort, and pagination state.
2. **Form Submissions**: Use progressive enhancement with Server Actions or `useActionState` and `useFormStatus` from `react-dom`.
3. **Optimistic Updates**: For instant UI feedback, wrap client state modifications in `useOptimistic` tied to the Server Action execution promise.
4. **Error Boundaries**: Every dynamic sub-route should define an `error.tsx` client component with error reporting and retry (`reset()`) handlers.
