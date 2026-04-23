---
layout: page
title: Privacy Policy
permalink: /en/privacy/
lang: en
---

> 🌐 **Language:** [PT](/privacidade/) · **EN** · [ES](/es/privacidad/)

> This is a courtesy translation of the original Portuguese document. In case of any discrepancy, the [Portuguese version](https://geninho.app.br/privacidade/) prevails.

# Privacy Policy — Geninho

**Last updated:** April 21, 2026

## 1. Who we are and the purpose of this Policy
**Geninho** is an iOS educational-support app for Brazilian families, focused on school organization, AI-powered study plans, and quiz-validated session completion.

This Policy describes, in plain language, **what data we process, why we process it, who we share it with, and what rights you have** as a data subject, in accordance with the **Brazilian General Data Protection Law (LGPD, Federal Law No. 13,709/2018)** and App Store requirements.

**Data controller:**
- Responsible party: **Pablo Rodrigo (independent developer)**
- Jurisdiction: Recife/PE — Brazil
- Contact channel for privacy, LGPD, and security matters: **suporte@geninho.app.br**

Additional identification details (ID document and full address) may be provided upon a formal, well-founded request under the LGPD, through the contact channel above.

> **A note for international users:** This app is developed and operated from Brazil. Users outside Brazil are welcome; we respond to data-subject requests under applicable privacy laws in good faith, but the controlling legal framework for data processing is Brazilian law.

## 2. Principles we follow
- **Minimization:** we only collect what is necessary to operate the service.
- **Specific purpose:** every piece of data is used for a stated purpose.
- **Transparency:** this Policy lists our vendors and the types of data involved.
- **Security by default:** data in transit and at rest relies on the protections offered by the providers listed in section 6.
- **Parental control:** child profiles are created and managed only by a guardian with an account linked to the same family.

## 3. Data we process

### 3.1 Authentication data (guardian)
- email;
- display name (when provided by the identity provider);
- technical account identifiers (Firebase Auth UID, Apple Sign-In identifier, Google account ID when applicable);
- Apple's anonymous relay email, when the user chooses "Hide my email".

**Biometrics (Face ID / Touch ID)** are processed exclusively on the device by iOS. Geninho **does not receive or transmit biometric data** — only the boolean "authenticated / not authenticated" result.

### 3.2 Family and child data
- family name;
- user roles (`ownerParent`, `parent`, `child`);
- relationships between guardians and children;
- for each child: name, school year/grade, study settings (time window, duration, minimum quiz passing percentage, YouTube permission), coins, streak, and achievements.

Children **do not create accounts on their own**. Profiles are created by a guardian, who holds the relationship and is responsible for the minor's data (see section 9).

### 3.3 School and pedagogical data
- registered school(s) and periods;
- class schedule per child (subject, day, time);
- school-year plan (subjects, topics);
- exams/activities (subject, date, topics, score when entered);
- study sessions generated, whether completed or not;
- quiz results (percentage correct, attempts, question feedback);
- adaptive profile per child (best study windows, mastery by subject/topic).

### 3.4 AI-generated data
- text extracted by OCR from the images/PDFs you import (schedule, exam calendar);
- questions the child sends to **Geninho's free chat** (Premium);
- AI-generated responses;
- **automated classification** of the question (normal, direct request for answer keys, inappropriate content, suspicious) and reason, when applicable;
- questions classified as `direct_homework`, `inappropriate`, or `suspicious` are made available to the family's guardian for review (collection `flaggedQuestions`).

### 3.5 Usage and subscription data
- monthly usage counters (AI plans generated, chat questions) to enforce plan limits;
- total counters (OCR imports);
- StoreKit transaction identifier and subscription product (`com.geninho.app.premium.monthly` / `.yearly`) — **we do not receive card data**; billing is handled entirely by Apple.

### 3.6 Technical and advertising data (free plan only)
- In the free version, we display **Google AdMob** ads. Before requesting personalized ads, we ask for your consent through Apple's native **App Tracking Transparency (ATT)** prompt.
- If you **allow** tracking, AdMob may use the IDFA (Apple's advertising identifier) to show more relevant ads.
- If you **do not allow** it, AdMob shows only non-personalized ads and the IDFA is not shared.
- Geninho does **not** collect the IDFA for any purpose beyond serving ads through AdMob.

### 3.7 Notifications
The app uses **local notifications only** (study reminders, upcoming exams, achievements). We do not use push services and do not send device tokens to external servers.

## 4. Purposes and legal bases (LGPD art. 7)

| Purpose | Data used | Legal basis |
|---|---|---|
| Create and authenticate account | email, provider identifiers | Performance of a contract |
| Organize school routine | data from 3.2, 3.3 | Performance of a contract |
| Generate AI study plans and quizzes | 3.3 and 3.4 | Performance of a contract |
| Validate study session via quiz | 3.3, 3.4 | Performance of a contract |
| Enforce Free plan limits and charge Premium | 3.5 | Performance of a contract |
| Chat moderation and child safety | 3.4 | Legitimate interest + best interest of the child |
| Display ads on the free plan | 3.6 | Consent (ATT) |
| Prevent fraud and ensure security | operational logs | Legitimate interest |
| Comply with legal obligations | when required | Compliance with a legal obligation |

## 5. Image processing and AI

### 5.1 OCR
Text extraction from imported images/PDFs happens **on the device itself**, using Apple's Vision framework. Images **are not** sent to our servers or to AI providers.

### 5.2 Sending text to AI
After OCR, **only the extracted text** (not the image) may be sent to AI providers (see section 6) to structure classes, exams, and topics. We recommend reviewing the results before confirming — AI can make mistakes.

### 5.3 Chat with Geninho
Questions asked through the free chat (Premium) and the generated responses travel through the contracted AI provider. We do not use these conversations to train AI models; the providers listed in section 6 have contractual no-training clauses for API data.

### 5.4 Mandatory consent before sending data to AI providers
Before you first use any feature that relies on cloud AI (plan generation, structured OCR, quiz, chat), the app shows the **"Use of Artificial Intelligence"** screen listing:
- **What data will be sent** — text extracted from photos/PDFs, registered subjects and topics, chat questions, and pedagogical context.
- **To whom** — OpenAI, Inc. (USA), Google LLC (USA), and, when configured, Microsoft Corporation (Azure OpenAI).
- **What we guarantee** — providers are contractually barred from training models on your data; we do not send financial data, passwords, location, or personal identifiers beyond what is necessary.

The user must tap **"Accept and continue"** to unlock AI features. If they choose **"Continue without AI"**, the app keeps working with local features (schedule, exams, reminders, achievements) and cloud calls are blocked. The preference can be revisited at any time in **More → AI Preferences**. Until consent is given, **no personal data is sent to AI providers**.

## 6. Processors and vendors (who we share data with)

We share data **only with the vendors strictly necessary** to operate the service:

| Vendor | Role | Data processed | Processing location |
|---|---|---|---|
| **Google / Firebase** (Authentication, Firestore, Storage) | Authentication and database | All data in sections 3.1 to 3.5 | USA / multi-region |
| **Apple** (Sign in with Apple, StoreKit) | Login and subscription billing | Apple identifier, subscription transaction | USA |
| **Google** (Google Sign-In) | Optional login with a Google account | email, Google identifier | USA |
| **OpenAI** | Quiz generation, study plan, structured OCR, chat | Text (no images) from 3.3 and 3.4 | USA |
| **Google Gemini** | AI fallback | Same as above | USA |
| **Azure OpenAI** (when configured) | Alternative AI provider | Same as above | USA / EU |
| **Google AdMob** | Ads on the free plan | 3.6 | USA |

The vendors above act as **processors** (LGPD art. 5, VII) under Geninho's instructions. We do not sell personal data and we do not share it for third-party marketing purposes.

### International transfer
Data may be processed on servers located outside Brazil (mainly in the USA). The vendors listed above adopt contractual clauses and safeguards consistent with LGPD art. 33.

## 7. Retention and deletion
- Family, child, and study data are kept **while the account is active**.
- Usage records and plan-limit counters are kept for as long as needed to operate the Free and Premium plans.
- **Account deletion:** available in the app itself ("More" → delete account) or by email to `suporte@geninho.app.br`. After the request, personally identifiable data is removed from active systems within **30 days**, subject to legal obligations and technical limitations of backups.
- Subscription transaction records may be kept for the applicable legal term (tax/consumer law) even after the account is deleted.

## 8. Security
- HTTPS/TLS connections to all vendors.
- API credentials **never** embedded in a public repository (stored in a local `Config.xcconfig`).
- Permission separation by role (guardian vs. child).
- Authentication through well-known providers (Apple, Google, Firebase Auth).
- Optional biometrics to unlock the app on the device.
- Periodic review of dependencies and best practices.

Despite these controls, no system is 100% immune. When we identify a relevant incident that could pose a risk to data subjects, we will follow the procedures set out in the LGPD (art. 48) and notify the ANPD and affected data subjects when applicable.

## 9. Data of children and adolescents (LGPD art. 14)
- Geninho is intended for **families**, with child profiles created and operated **by the guardian**.
- The legal basis for processing minors' data is the **best interest of the child**, with specific, highlighted consent from the guardian at the time the profile is created.
- The guardian has access to: the child's profile data, school progress, chat questions, and items flagged for review.
- We do not ask for more data about the child than is necessary for the school routine and pedagogical support.
- The free chat has **automated classification** that blocks inappropriate content and flags direct answer-key requests.
- The guardian may remove the child's profile from the app at any time.

## 10. Your rights (LGPD art. 18)
You may exercise the following rights at any time:

1. confirmation that processing exists;
2. access to the data;
3. correction of incomplete, inaccurate, or outdated data;
4. anonymization, blocking, or deletion of unnecessary or excessive data;
5. data portability;
6. deletion of data processed on the basis of consent;
7. information about who we share data with;
8. information about the option not to give consent and its consequences;
9. withdrawal of consent.

**Channel to exercise your rights:** `suporte@geninho.app.br`. We will respond within **15** calendar days, as per LGPD art. 19.

If you do not receive a satisfactory response, you may contact the **National Data Protection Authority (ANPD)** at [https://www.gov.br/anpd](https://www.gov.br/anpd).

## 11. AI-generated content — limitations
- Study plans, quizzes, and chat answers are pedagogical support and **may contain errors or inaccuracies**.
- The content does not replace a teacher, school, or official course materials.
- Use the AI as a starting point; always review it with a critical eye.

## 12. Advertising and tracking
- The Free plan shows ads via Google AdMob.
- We ask for your consent to track via the iOS native prompt (App Tracking Transparency).
- Your ATT answer can be changed at any time in **Settings → Privacy & Security → Tracking**.
- The Premium plan is **completely ad-free**.

## 13. Updates to this Policy
We may revise this Policy to reflect legal, technical, or product changes. The current version is always available inside the app (**Legal Documents** screen) and in this repository. Material changes will be communicated through an appropriate channel (in-app notice or email).

## 14. Contact
- Privacy / LGPD email: **suporte@geninho.app.br**
- Data protection officer: the contact channel above handles requests under the LGPD. Since this is a small-scale operation run by an independent developer, the flexible treatment set out in ANPD Resolution CD/ANPD No. 2/2022 for small-scale processing agents applies.

---

**Quick visual summary (does not replace the full text):**
- We do not sell data.
- We use Firebase, OpenAI/Gemini/Azure, AdMob, and Apple/Google to operate.
- OCR runs on your iPhone; only the extracted text goes to the AI.
- Children do not create accounts on their own — always a guardian.
- You can delete your account and request a copy of your data at any time.
