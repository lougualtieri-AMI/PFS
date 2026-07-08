# PFS — Personal Financial Status

A simple, private planning tool that shows how a household's money might play out
over the years ahead — before and after retirement. You open it in a web browser,
put in your numbers, and it draws a picture of where you stand, what your savings
can support, and how different choices could change the road ahead.

**Try it here:** `https://<your-username>.github.io/<repo-name>/`

Nothing is downloaded, nothing is sent anywhere, and you don't need an account.

---

## What it helps you see

- **Where you are today** — your income, your savings, your home, and what you spend.
- **What your money can support** — roughly how much you can spend each year without
  running short.
- **What could happen** — how the picture shifts if you retire earlier, spend more or
  less, move money between accounts, or plan around taxes.
- **Taxes, made visible** — it shows how much of your income falls into each tax
  bracket in a given year, so you can see the room you have before the next bracket
  kicks in. This is useful if you're thinking about moving money from a traditional
  retirement account into a Roth.
- **What you might leave behind** — an estimate of what would remain for your estate.

You don't need to understand the tax rules yourself — the tool does that part and
shows you the result in plain numbers, in either today's dollars or future dollars.

---

## How to use it

**The easy way:** click the link above. It opens right in your browser.

**To keep your own copy:** download the file `index.html` and double-click it. It
opens like a web page — no installation, no setup.

Then either:

- Pick one of the three **sample households** from the menu to see how it works, or
- Enter your own numbers to see your own picture.

That's it. Everything happens on your screen.

---

## Is my information private?

Yes. Whatever you type stays on your own device. The tool never sends your
information over the internet, and there's no login and no account. If you close the
page, it's gone unless you choose to save it. The version shared here comes with
only three made-up example households — no real personal data.

---

## Please note

PFS is a planning and learning tool. It shows you *what could happen* based on the
numbers you enter — it is **not** financial, tax, or legal advice, and it doesn't
predict the future. For decisions that matter, talk with a qualified professional.

---

## Under the hood (for the technically curious)

Everything lives in a single `index.html` file — all the layout, styling, and
calculations — with no outside code, no build step, and no dependencies. The math
runs in today's dollars internally and can be shown in future dollars with a toggle.

The calculation engine is locked and checked against a saved fingerprint on every
release, so display changes can never quietly alter the numbers. Before any new
version is accepted, it must pass an automated test run:

```
node pfs_v4_gates.js index.html   →   ✓ ALL GATES GREEN
```

Those tests re-run three reference households to the exact dollar, confirm the engine
fingerprint matches, and exercise each feature (the tax-bracket views, navigation,
and edge cases). A build isn't finished until every check passes.

Current build: `pfs_index022` · engine `v007`.

---

## License

PFS is released under the **PolyForm Noncommercial License 1.0.0** — free to use,
study, and share for personal and other noncommercial purposes. See the `LICENSE`
file for the full terms.
