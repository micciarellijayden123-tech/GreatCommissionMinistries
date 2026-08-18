# Great Commission Ministries — Website

A single-page site built around Matthew 28:19–20, with three downloadable
discipleship guides.

## Folder structure

```
GreatCommissionMinistries2819/
├── index.html
├── README.md
├── how-to-make-disciples.pdf
├── how-to-obey-gods-word.pdf
└── how-to-teach-gods-word.pdf
```

Keep `index.html` and the `resources/` folder together — the download
buttons on the page use relative links like `resources/how-to-make-disciples.pdf`,
so they'll break if the folder is moved or renamed.

## Opening it in VS Code

1. Unzip this folder wherever you keep projects.
2. In VS Code: **File → Open Folder…** and select `gcm-site`.
3. To preview it, either:
   - double-click `index.html` in the VS Code file explorer, then open it in
     a browser, or
   - install the **Live Server** extension (by Ritwick Dey) and click
     "Go Live" at the bottom right — this gives you auto-reload while you edit.

## Editing

Everything — layout, colors, copy — lives in `index.html`. Useful places to look:

- `:root { ... }` near the top of the `<style>` block — all the colors as CSS variables.
- Section by section, the page goes: nav → hero → verse → the four-step
  commission → resources (PDF downloads) → email signup → footer.
- Placeholder to update: the contact email `GreatCommissionMinistries@gmail.com`, the
  phone number `(000) 000-0000`, and the `<form>` elements in the "connect"
  and "reach" sections — right now the email signup and prayer request form
  just update a button label on submit (nothing is actually sent or saved).
  To make these live, wire them to a real service:
  - Email signup → Mailchimp, ConvertKit, or a simple backend endpoint.
  - Prayer request form → a form backend like Formspree/Netlify Forms, or a
    small serverless function that emails/stores submissions. Since these
    requests may be sensitive, make sure wherever they land is private and
    only accessible to your prayer team.

## Deploying

This is a static site — no build step. Drop the whole `gcm-site` folder onto
any static host (Netlify, Vercel, GitHub Pages, Cloudflare Pages) or a plain
web server, and it works as-is.
