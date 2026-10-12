# Next.js App Router Production Verification Checklist

## Security & Boundary Checks
- [ ] No server secret keys or database connection pools imported into client components.
- [ ] All sensitive data access files contain `import "server-only"`.
- [ ] Every Server Action verifies authentication and session validity before database queries.
- [ ] Every Server Action input is strictly sanitized and schema-validated (e.g. Zod).
- [ ] No unhashed passwords, access tokens, or tenant IDs leaked in server action return values.

## Performance & Rendering
- [ ] Root layouts and layout trees do not use `"use client"`.
- [ ] Client components are isolated leaves at the bottom of the tree.
- [ ] Data queries run concurrently via `Promise.all` or independent Suspense boundaries (zero waterfall queries).
- [ ] Images leverage `next/image` with explicit width/height and responsive sizing.
- [ ] Appropriate `revalidatePath` or `revalidateTag` calls are triggered after mutations.
