# no itck cnt — deployment guide

This folder is a complete, ready-to-publish static site: `index.html`, `favicon.svg`,
`robots.txt`. No build step, no server required.

## 1. Connect the enquiry form (do this first)

The form on the site needs a place to send enquiries. It's wired for
[Formspree](https://formspree.io), which is free for up to 50 submissions/month
and needs no server:

1. Go to formspree.io and create a free account.
2. Create a new form — it'll give you an endpoint like `https://formspree.io/f/abcdwxyz`.
3. Open `index.html`, search for `YOUR_FORM_ID`, and replace it with your real ID
   (just the ending part, e.g. `abcdwxyz`).

Until you do this, the form will show an error instead of the thank-you message.
(If you'd rather skip a third-party service entirely, you can instead change the
form's `action` to a `mailto:` link — simpler, but it opens the visitor's email
app instead of submitting quietly, and isn't as reliable on mobile.)

## 2. Publish it — pick one

All of these work from a terminal, are free to start, and give you a live URL
in under a minute. Run the command from inside this folder.

**Surge (simplest)**
```
npm install -g surge
surge
```
Follow the prompts (first run asks for an email + password). It'll suggest a
random `something.surge.sh` URL — you can type your own instead, or add a
custom domain later.

**Netlify**
```
npm install -g netlify-cli
netlify deploy --prod
```
First run will ask you to log in (opens a browser) and whether to create a new
site. Say yes, accept the default publish directory (`.`).

**GitHub Pages**
```
git init
git add .
git commit -m "no itck cnt — initial site"
git branch -M main
git remote add origin <your-empty-github-repo-url>
git push -u origin main
```
Then in the repo on GitHub: Settings → Pages → set source to the `main` branch.
This one needs a free GitHub account and an empty repo created first.

All three give you a free subdomain to start; each also supports pointing a
custom domain at it later if you buy one.

## 3. Before you tell anyone the URL

- **Read the host's acceptable-use policy first.** Some free static hosts
  restrict adult or companion services specifically, separate from whether the
  content is explicit. Surge, Netlify, Vercel, and GitHub Pages all publish
  theirs — worth five minutes before you commit to one, since moving hosts
  later means updating DNS again if you've attached a domain.
- **Same goes for any payment or booking tool** you connect later — mainstream
  processors often exclude this category even when it's legal locally.
- **Companion profiles are placeholders** (Isabelle, Sasha, Amara) — swap in
  real names/bios/photos before launch, or remove the section.
- **Consider a short privacy note** given the form collects names, emails and
  phone numbers for a discretion-sensitive service — not something I've
  drafted here since it's genuinely worth a lawyer's five minutes rather than
  generic boilerplate.
