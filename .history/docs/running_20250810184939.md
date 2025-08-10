The `"Could not load theme elegant"` error means `resumed` can’t find the `jsonresume-theme-elegant` package where it expects it.
This usually happens because:

1. `resumed` is looking for a theme in a specific folder relative to where you run the command.
2. The theme package name is correct, but `resumed` needs it explicitly passed as `--theme jsonresume-theme-elegant`.

Here’s the fix:

1. Make sure both are installed locally:

   ```bash
   npm install resumed jsonresume-theme-elegant
   ```

2. Run `resumed` with the theme name explicitly:

   ```bash
   npx resumed render --theme jsonresume-theme-elegant
   ```

3. Ensure you have a valid `resume.json` in `C:\Users\RhysL\Desktop\Resume`.
   Example minimal file:

   ```json
   {
     "$schema": "https://raw.githubusercontent.com/jsonresume/resume-schema/v1.0.0/schema.json",
     "basics": {
       "name": "Rhys Wells",
       "label": "Data Scientist",
       "email": "rhyslwells@outlook.com"
     }
   }
   ```

4. After running the command, you should see `resume.html` in the same folder.

---

If you want to preview in a browser directly:

```bash
npx resumed serve --theme jsonresume-theme-elegant
```

---

If you run it without `--theme jsonresume-theme-elegant`, `resumed` will try to load a theme literally called `elegant`, which is why it fails.

Do you want me to give you a **full working example** with `resume.json` so you can test this end-to-end? That way you’ll see HTML output right away.
