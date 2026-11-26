# Flora Chao — Product Architecture

**Version:** 1.0
**Status:** Draft
**Product Type:** Personal portfolio
**Platforms:** Web
**Primary Users:** Anyone who wants a clear picture of Flora’s studies and her public communication attachment

**Related:** [technical_architecture.md](technical_architecture.md) · [sprint.md](sprint.md)

---

# 1. Product overview

Flora Chao’s portfolio is a one-page site. It says who she is, what she studies, and what she did on attachment.

The page is built around this idea:

> **Give a visitor Flora’s name, her program, and the work named in her recommendation letter, then a way to write to her.**

A visitor can:

- Read her name and program on the first screen
- See that she is a 4th-year Corporate Communication and Management student at Jomo Kenyatta University of Agriculture and Technology, expected to graduate in June 2027
- Read the about paragraph as it was written
- Scan the focus areas named in that paragraph
- Read the Nairobi City County attachment and the nine areas of work named in the recommendation letter
- Email her at Chaokiteria@gmail.com

The copy comes only from details that were provided. The page does not invent projects, social accounts, or a public hosting URL.

---

# 2. What the first screen answers

The hero answers who she is before the visitor scrolls.

```text
Name            Flora Chao
University      Jomo Kenyatta University of Agriculture and Technology
Role            4th-year Corporate Communication and Management student
Lead            Looking to apply strong organizational and interpersonal
                skills in a fast-paced communications team
Facts           JKUAT
                Corporate Communication and Management
                4th year
                Graduation June 2027
                Attachment: Nairobi City County, 1 July–31 August 2026
```

---

# 3. Page modules

```text
Flora Chao portfolio
│
├── Site chrome
│     ├── Wordmark
│     ├── Section navigation
│     └── Theme (light, dark, system)
├── Hero
├── About
├── Focus
├── Experience
├── Selected work
├── Contact
└── Footer
```

### Chrome

Skip link, sticky header, and anchor links: About, Focus, Experience, Work, Contact. The theme control offers light, dark, and system.

### About

The about copy is the paragraph that was provided, plus the description of her as a fast learner with strong focus and people skills, who delivers hands-on communication and stays optimistic and positive. It is not a second copy of the hero.

### Focus

The named areas:

```text
Strategic communication
Internal communications
Event coordination
Organizational skills
Interpersonal skills
```

### Experience

One entry: attachment in the Department of Public Communication, Nairobi City County, from 1 July to 31 August 2026, in the Inclusivity, Public Participation and Customer Services sector.

### Selected work

One card for the recommendation letter dated 2 September 2026. Reference NCCG/PC/ADAS/44/2026, signed by CHRP-K Simon Macharia, Assistant Director, Administration Services. The letter describes her as a fast learner who worked cordially with the team and showed a high level of concentration on the assignments she was given.

The nine areas named in that letter:

```text
Assisting in compiling communication materials for public awareness
Drafting press releases, public notices, and official announcements
Monitoring print, electronic, and online media coverage
Preparing media reports and press summaries
Creating digital content such as posters, graphics, and public awareness messages
Participating in public participation forums
Assisting in communication between county departments
Guiding members of the public to relevant departments
Photocopying, scanning, and printing official documents
```

The national ID number printed on the letter is not on the page and is not recorded in these notes.

### Contact

A mailto link to Chaokiteria@gmail.com. Social links are a labeled placeholder until she provides them.

### Footer

Her name, JKUAT, and expected graduation in June 2027.

---

# 4. Visitor path

```text
Open the page
      ↓
Read her name, program, and graduation
      ↓
Read about, focus, and the attachment
      ↓
Write to Chaokiteria@gmail.com
```

There is no account, no contact form, and no file upload. Choosing the email address opens a new message in the visitor’s mail program.

---

# 5. Navigation

```text
Header
│
├── About
├── Focus
├── Experience
├── Work
└── Contact

Page (one document)
│
├── hero
├── #about
├── #focus
├── #experience
├── #work
└── #contact
```

The site is a single page. There are no project routes.

---

# 6. What stays empty

These stay empty until real details are provided. Do not invent them.

```text
Contact social links
A public URL for this site
```

The social-link gap is marked on the page and with an HTML comment directly above it. The email is already shown.

---

# 7. What this product is not

```text
Not a SaaS
Not a multi-page app
Not an authenticated site
Not a blog
Not a contact form
Not a copy of another person’s portfolio
```

The product is one honest page: studies, attachment, and an email address.

---

# 8. Success

The page succeeds when a visitor can do this without a PDF:

```text
Read who Flora is
      ↓
See the attachment and the nine areas of work
      ↓
Email her
```
