# Tailwind Bug?

To repro:

1. Start the CLI tool:

```bash
npx @tailwindcss/cli -i ./src/input.css -o ./src/output.css --watch
```

2. Open the page

```bash
open src/index.html
```

3. Notice that the button is Red for light mode, Blue for dark mode.

--- NOW

1. open up `src/input.css`
2. remove the `.my-class` definition
3. go back to browser... and notice that the button isn't red anymore (but it is blue for dark mode)

---

W/out that class definition, the root `--critical` variable is missing.
