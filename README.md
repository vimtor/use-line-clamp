# use-line-clamp

React.js hook to detect if text will clamp in X number of lines. This allows you to use lines instead of character for implementing "show more" behaviour.


[**See live demo**](https://stackblitz.com/edit/use-line-clamp?file=App.tsx)

https://user-images.githubusercontent.com/36263538/215266290-49dbc549-f710-402b-bc9e-9cc97215d829.mp4

## Install

```sh
npm install use-line-clamp

pnpm install use-line-clamp

yarn add use-line-clamp
```

## Usage

```tsx
import { useRef, useState } from "react";
import useLineClamp from "use-line-clamp";

function Example() {
  const ref = useRef<HTMLParagraphElement>(null);
  const clamps = useLineClamp(ref, { lines: 4 });
  const [visible, setVisible] = useState(false);

  return (
    <div>
      <p ref={ref} className={visible ? "" : "line-clamp-4"}>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. In consectetur
        doloremque molestiae perspiciatis aliquam voluptatem natus quod quia
        repellendus? Vero veniam quidem quae veritatis voluptas ratione
        doloremque. Quo, saepe quidem. Inventore voluptatibus ipsam totam nobis
        magni molestiae ea culpa animi?
      </p>
      {clamps && (
        <button onClick={() => setVisible(!visible)}>
          Show {visible ? "less" : "more"}
        </button>
      )}
    </div>
  );
}
```
