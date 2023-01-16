# Redirecting Users

## Snippet

This is an example on how to redirect the user back to the homepage.

```jsx
// 404.tsx

import type { NextPage } from "next";
import Link from "next/link";
import { useEffect } from "react";
import { useRouter } from "next/router";

const NotFound: NextPage = () => {
  const router = useRouter();

  useEffect(() => {
    setTimeout(() => {
      router.push("/");
    }, 3000);
  }, []);

  return (
    <>
      <div>
        <h1>Page not found</h1>
        <p>
          Uh oh, we can't seem to find the page that you're looking for. Try
          going back to the <Link href="/">homepage</Link> or wait in a few
          seconds.
        </p>
      </div>
    </>
  );
};

export default NotFound;
```
