# use-line-clamp

React.js hook to detect if text will clamp in X number of lines.

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