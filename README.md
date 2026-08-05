# Job Application Form

A semantic, unstyled, fully accessible multi-page job application form built with pure HTML. No CSS frameworks, no JavaScript dependencies — markup only.

**Author:** Jan Dexter Diaz  
**Course:** Fullstack Development — Lab Activity 1

---

## Table of Contents

- [Overview](#overview)
- [Project Structure](#project-structure)
- [Page Breakdown](#page-breakdown)
  - [Page 1: Personal Information](#page-1-personal-information)
  - [Page 2: Position Details](#page-2-position-details)
  - [Page 3: Experience](#page-3-experience)
  - [Page 4: Education & Skills](#page-4-education--skills)
- [Accessibility Features](#accessibility-features)
- [Validation](#validation)
- [File Uploads](#file-uploads)
- [Navigation](#navigation)
- [How to Use](#how-to-use)
- [Limitations](#limitations)
- [License](#license)

---

## Overview

This project is a 4-page job application form designed for **any industry** — not limited to tech roles. It demonstrates proper use of semantic HTML5 elements, native browser validation, and accessibility best practices without relying on any CSS or JavaScript frameworks.

---

## Project Structure

```
LabActivity1-Diaz-JobApplicationForm/
├── personal-information.html   (Page 1)
├── position.html               (Page 2)
├── experience.html             (Page 3)
├── education-skills.html       (Page 4)
└── README.md
```

---

## Page Breakdown

### Page 1: Personal Information

**File:** `personal-information.html`

Collects the applicant's basic identity and contact details.

| Section | Fields |
|---------|--------|
| Contact Details | First Name, Last Name, Email, Phone Number, Street Address, City, State/Province, ZIP/Postal Code, Country |
| Additional Information | Date of Birth, Citizenship Status, Communication Preference (Email/Phone/Both) |

---

### Page 2: Position Details

**File:** `position.html`

Collects job-specific preferences and requirements.

| Section | Fields |
|---------|--------|
| Position Information | Position Title, Department, Employment Type, Preferred Start Date, Currency + Salary (grouped), Work Location Preference, Preferred Work Hours Per Week, Visa Sponsorship (Yes/No/Not applicable - I am a citizen/permanent resident), Referral Source |
| Additional Requirements | Cover Letter (textarea), Availability (checkboxes: immediate, travel, relocation) |

---

### Page 3: Experience

**File:** `experience.html`

Collects work history and supporting documents.

| Section | Fields |
|---------|--------|
| Current/Most Recent Position | Job Title, Company, Industry, Start Date, End Date, Key Responsibilities |
| Previous Position | Job Title, Company, Industry, Start Date, End Date, Key Responsibilities (all optional) |
| Experience Summary | Total Years of Experience (dropdown), Professional Achievements, Reason for Leaving |
| Supporting Documents | Resume/CV (file upload, required), Reference Letter (file upload), Work Samples URL, Work Samples File Upload |

---

### Page 4: Education & Skills

**File:** `education-skills.html`

Collects educational background, professional skills, and final agreements.

| Section | Fields |
|---------|--------|
| Highest Level of Education | Education Level, Institution, Field of Study, Graduation Date, GPA |
| Professional Certifications | Certifications (textarea), Certification Documents (file upload) |
| Professional Skills | Primary Skills (textarea), Skill Areas (checkboxes: Administration, Finance, Marketing, Sales, IT, Engineering, Healthcare, Education, Legal, Creative, Project Management, Skilled Trades, Other) |
| Key Competencies | Key Strengths (textarea), Top Competencies (checkboxes: Teamwork, Leadership, Communication, Problem-Solving, Time Management, Adaptability, Creativity, Attention to Detail, Customer Focus, Critical Thinking) |
| Languages Spoken | Up to 3 languages, each with a fluency level (Native, Fluent, Advanced, Intermediate, Basic) |
| Application Agreement | Certify information is true (required), Agree to background check (required), Agree to future contact (optional) |

---

## Accessibility & SEO Features

### Accessibility

This form follows WCAG guidelines and accessible form design patterns:

- **Landmarks:** Every page uses `<header>`, `<nav>`, `<main>`, and `<footer>` for screen reader navigation.
- **Heading hierarchy:** One `<h1>` per page ("Job Application Form"), with `<h2>` for section headings. No skipped heading levels.
- **Labels:** Every form control has an associated `<label>` with a matching `for`/`id` pairing.
- **Required indicators:** Required fields use both `required` attribute, `aria-required="true"`, and a visible asterisk with `aria-label="required"`.
- **Fieldset/Legend:** Related controls (radio buttons, checkboxes, grouped fields) are wrapped in `<fieldset>` with descriptive `<legend>` elements.
- **Descriptive hints:** Complex fields use `aria-describedby` linked to `<small>` hint text (e.g., phone format, file size limits).
- **Navigation:** An ordered list (`<ol>`) with `aria-label="Application progress"` indicates the multi-step progress, with the current step shown in bold.

### SEO Optimization

All pages include:
- **Meta description:** Page-specific descriptions for search engine snippets
- **Open Graph tags:** Social media sharing optimization (`og:title`, `og:description`, `og:type`)

---

## Validation

All validation is native HTML — no JavaScript required:

| Validation Type | Implementation |
|-----------------|---------------|
| Required fields | `required` attribute |
| Email format | `type="email"` |
| Phone format | `type="tel"` + `pattern="[0-9\-\(\)\s\+]+"` |
| Date fields | `type="date"` |
| Numeric fields | `type="number"` with optional `min`/`max` |
| URL format | `type="url"` |
| GPA range | `min="0"` `max="4"` `step="0.01"` |
| Work hours | `min="1"` `max="80"` |
| File types | `accept` attribute on file inputs |
| Agreements | Required checkboxes before submission |

---

## File Uploads

| Field | Page | Accepted Formats | Required |
|-------|------|-----------------|----------|
| Resume/CV | Experience | PDF, DOC, DOCX | Yes |
| Reference Letter | Experience | PDF, DOC, DOCX | No |
| Work Samples (file) | Experience | PDF, JPG, PNG, ZIP | No |
| Certification Documents | Education & Skills | PDF, JPG, PNG | No |

All file uploads indicate a **maximum file size of 5 MB** (note: enforcing this limit requires server-side or JavaScript validation; the HTML communicates the restriction to users).

---

## Navigation

- Each page displays a progress indicator showing all 4 steps.
- The current step is highlighted with `<strong>`.
- Other steps are clickable `<a>` links for non-linear navigation.
- **Next** buttons use `<button type="submit">` with `formaction` to advance while triggering validation.
- **Back** buttons use `<button type="button">` to navigate without validation.
- The final page has a **Submit Application** button (`<button type="submit">`).

---

## How to Use

1. Open `personal-information.html` in any web browser.
2. Fill in the required fields and click "Next" to advance.
3. Use the navigation links at the top to jump between pages.
4. On the final page, agree to the terms and click "Submit Application."

No build tools, servers, or dependencies required — just open the HTML files directly.

---

## Limitations

- **No styling:** The form is unstyled by design. Add your own CSS to customize appearance.
- **No JavaScript:** Dynamic behaviors (conditional fields, real-time validation feedback, file size enforcement, address autocomplete) are not included.
- **No server-side processing:** The `action="/submit-application"` is a placeholder. A backend is needed to process submissions.
- **File size limits:** Communicated via text hints only. Actual enforcement requires JS or server validation.
- **Multi-page state:** Form data is not persisted between pages (would require JS `localStorage`, cookies, or server sessions).

---

## License

&copy; 2026 Jan Dexter Diaz. All rights reserved.
