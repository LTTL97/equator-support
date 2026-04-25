# Equator: Expense Tracker — Privacy Policy & Terms of Service

**Last Updated: April 25, 2026**

Welcome to Equator: Expense Tracker (the "App"). This document governs your use of the App and outlines our privacy practices. By downloading, accessing, or using the App, you agree to be bound by these terms. If you do not agree, do not use the App.

The App is developed and published by **Low Timothy**, an individual developer based in Singapore, operating under the brand name "Lowlabs" ("we," "us," or "our"). The App is distributed through the Apple App Store in all regions except the European Union and mainland China.

---

## 1. Privacy Policy

We have designed the App with strict privacy principles. With the sole exception of the AI Chat feature described below, your financial data is stored exclusively on your device and is never transmitted to our servers. This section explains each data flow in detail so you can make informed decisions about your use of the App.

### 1.1 Local Storage

All financial data you enter into the App — including transactions, accounts, categories, budgets, portfolios, and notes — is stored entirely locally on your device using Apple's native database frameworks. We do not host this data on our servers, and we have no ability to view, access, modify, or share it.

### 1.2 No Account System

The App does not require you to create an account, register, or sign in. We do not collect your email address, name, password, or any other sign-up information. All your data lives on your device and, at your option, in your personal iCloud Drive. This design choice means we have no user database, no login system, and no ability to identify individual users across sessions or devices.

A consequence of this design is that we do not hold your email address, which means we cannot proactively contact you (for example, to notify you of updates to this policy or security incidents). Notifications that we are required to deliver will be communicated through in-app notices, updates to this policy page, or announcements on the App's App Store listing.

### 1.3 iCloud Backup and Restore

The App provides an optional backup feature that allows you to save and restore JSON snapshot files to your personal Apple iCloud Drive. These backups are initiated by you and stored in your private iCloud container. We do not have access to your iCloud account or its contents.

Separately, your device's operating system may automatically back up local app data to iCloud based on your personal iOS settings. We do not control iCloud; securing your Apple ID and managing your iCloud storage is your responsibility. To remove your data from iCloud, you may delete backups from within the App or directly from your iCloud Drive.

### 1.4 On-Device Intelligence

The App uses Apple's on-device machine learning frameworks to provide convenience features such as automatic transaction categorisation. All such processing occurs entirely on your device. No data is transmitted to us or any third party as part of this processing.

### 1.5 Direct Third-Party API Calls (Stock and Currency Data)

To provide market and currency information, the App makes network requests directly from your device to third-party data providers, including market data providers (for current asset prices and asset lookups) and public foreign exchange rate providers. Price data is refreshed on a delayed basis at a fixed interval.

These requests are made directly from your device to the third-party servers and do **not** transit our infrastructure. Standard internet protocols require that your device's IP address, along with the queried data (such as ticker symbols or currency codes), be transmitted to these providers to fulfil the request. We do not log this traffic and we do not link it to any of your personal or financial data.

Your use of these third-party services is governed by their respective terms and privacy policies.

### 1.6 In-App Purchases

The App offers three tiers of access:

- **Free** — the default tier on installation. Includes up to 3 accounts, 3 budget categories, 3 recurring transaction groups, and up to 5 AI Chat requests per day. CSV export and iCloud backup are disabled. Portfolio tracking is limited to 1 active ticker with price refreshes every 24 hours.
- **Equator Pro** — a one-time purchase of SGD 3.98 (or equivalent in your local currency). Includes everything in Free, plus: unlimited accounts, unlimited budget categories, unlimited recurring transaction groups, iCloud backup with configurable frequency, and CSV export for transaction history and portfolio. This purchase does not expire and is not a subscription. AI Chat and portfolio-related limits remain the same as Free.
- **Equator Premium** — a monthly subscription of SGD 3.98 (or equivalent in your local currency). Includes everything in Pro, plus: a higher AI Chat daily limit (200 requests per day), unlimited portfolio tickers, and faster portfolio price refreshes (every 10 minutes instead of every 24 hours).

All purchases are processed by Apple, not by us. We do not receive, store, or have access to your payment card details, billing address, Apple ID password, or any other financial information related to your purchase. Apple provides us only with anonymised transaction records and, in the case of Premium, subscription status information. StoreKit 2 verifies entitlements locally on your device; our server does not perform receipt validation.

**Subscription management:** Your Premium subscription renews automatically at the start of each monthly period at the then-current price displayed in the App Store, unless you cancel through Apple's subscription management at least 24 hours before the current period ends. You can view, manage, or cancel your subscription at any time through your device's Settings → [Your Name] → Subscriptions. We cannot cancel or modify your subscription on your behalf.

**Refunds:** All refund requests are handled by Apple in accordance with the Apple Media Services Terms and Conditions. To request a refund, visit [reportaproblem.apple.com](https://reportaproblem.apple.com). We do not have the ability to issue refunds directly.

**Family Sharing:** Family Sharing is not currently enabled for Equator Pro or Equator Premium.

### 1.7 AI Chat Feature

The AI Chat feature ("Eqqie AI Assistant") is available to all users of the App, subject to daily usage limits that vary by tier (see "Rate limiting" below). Because this is the only feature of the App that transmits your financial data off-device, we describe its data flow in detail below.

**When AI Chat is used:** Each time you send a message, the App packages your recent financial data and transmits it to our server hosted on Railway, which then forwards the request to Google's Gemini API. Google returns a response to our server, and our server relays it back to the App. No data from this process is written to disk on our server.

**Transport security:** All communication between the App and our server, and between our server and Google's Gemini API, is encrypted in transit using TLS (HTTPS). The App does not process requests over unencrypted connections.

**Data fields transmitted:** The following data is sent with each AI Chat request. Transactions, accounts, and budgets cover the current calendar month and the five preceding calendar months (up to six months of history). Portfolio data and context information are not subject to this time window and are sent as currently held in the App.

- *Transactions:* date, type (expense, income, refund, or transfer), category and subcategory, note field (which may include merchant names you have entered), amount, currency, home-currency equivalent, source and destination account names, and recurring or instalment tags.
- *Accounts:* account name, account type (e.g., savings, credit card), currency, native balance, home-currency equivalent, multi-currency wallet balances, and credit card cycle information (amount owed, current cycle spend, due date).
- *Budgets:* category, subcategory, budgeted amount, amount spent, and percentage used.
- *Portfolio assets:* ticker, asset name, quantity held, average cost, currency, invested amount, current market price, market value, profit/loss, sector, and the five most recent investment transactions per asset (which may include transactions older than six months).
- *Context:* your home currency, today's date, current exchange rates for your currencies and 17 major world currencies, and the list of category and subcategory names you have configured.

**Data fields NOT transmitted:** location data, raw account identifiers, your name, your email address, your Apple ID, or any other identifying information about you as an individual.

**Message history:** Chat history is stored locally on your device in the App's documents directory. With each AI Chat request, the App sends the most recent 20 messages of the current conversation so Google's model can maintain context. Our server does not store this history; it is stateless between requests.

**Server-side logging:** Our server logs only the following operational information: the Gemini model name used for each request, Gemini API error status codes, third-party market data fetch failures, and generic error events. We do not log the content of your messages, your financial data, your IP address, or your device identifier. Our hosting provider, Railway, may record standard HTTP access logs (timestamp, request path, status code, source IP) as part of its platform; we do not control the retention of these platform-level logs.

**Google's handling of your data:** Our server uses the paid tier of the Google Gemini API. Under Google's Gemini API Additional Terms of Service for paid API usage, your data is not used to train or improve Google's models. Google may retain API request logs for up to 55 days for abuse monitoring and debugging purposes, after which they are automatically purged. These logs cannot be individually deleted on request before the retention period expires. Your use of the AI Chat feature is subject to Google's privacy policy and the Gemini API terms.

**Pseudonymity of requests to Google:** Our server does not forward your device identifier, your IP address, or any Apple-specific identifier to Google. From Google's perspective, all AI Chat requests from the App appear as requests from a single developer account, with no information that would allow Google to distinguish one user from another or link any request back to a specific individual. As a result, even we cannot retrieve a specific user's request from Google's logs. Please note that if you have entered personally identifying information into your own transaction notes (for example, names of people or places), that information will be included in the data sent to Google as part of the transaction context.

**Rate limiting:** To enforce daily usage limits, our server maintains an in-memory count of requests keyed to your device's Apple-issued vendor identifier (`identifierForVendor`), transmitted in the `X-Device-ID` request header. This identifier is assigned by Apple and is scoped to our developer account; it resets if you delete the App. The counter is held in volatile process memory only, with no disk, database, or persistent storage. Our server is configured to shut down when idle and restart on demand when a new request arrives, which means the counter is erased frequently during periods of low activity; it is also erased on every deployment. The daily limit is 5 requests for Free and Pro users and 200 requests for Premium users.

**International data transfers:** Our server infrastructure is hosted by Railway in the United States, and Google's Gemini API processes requests in Google's global data centres. By using the AI Chat feature, you acknowledge that your data will be transmitted to and processed in jurisdictions outside Singapore. We rely on the contractual protections provided by Railway and Google to maintain a comparable standard of data protection to that required under Singapore's Personal Data Protection Act.

### 1.8 Data Controller and Role

For all features of the App **other than** AI Chat, your data remains on your device and we do not act as a data controller or data processor in respect of it.

For the **AI Chat feature specifically**, we act as a **data controller** under applicable data protection laws in respect of the data described in Section 1.7. Google, as the operator of the Gemini API, acts as our data processor for the purpose of generating responses. Our lawful basis for processing is the performance of the service you have requested by using the AI Chat feature.

### 1.9 Your Data Rights

You retain direct control over your information at all times. For the AI Chat feature, a small amount of data transits our server as described in Section 1.7, but is not persistently stored.

- **Right to erasure (local data):** To delete all local data, delete the App from your device. This permanently removes all financial records, chat history, and settings stored on the device.
- **Right to erasure (iCloud backups):** Delete any backups from within the App's Data & Backup settings, or directly from your iCloud Drive.
- **Right to erasure (Google's logs):** Because our server does not transmit any identifier that would allow Google to link a request to a specific user (as described in Section 1.7), we have no technical mechanism to identify which log entries in Google's system belong to any particular individual, and no mechanism to request deletion of individual entries before Google's automatic purge. Google's automatic 55-day retention applies equally to all requests. The only way to ensure no data is subject to Google's retention is to not use the AI Chat feature.
- **Right of access, rectification, and portability:** All your data is directly viewable and editable within the App, and exportable via the CSV and JSON export features.
- **Contact for data rights requests:** lowlabs.dev@gmail.com.

**Retention summary:** Local data on your device and iCloud backups are retained until you delete them. Our server does not persistently retain any of your financial data. The rate-limit counter is erased on server idle or restart, typically frequently during periods of low activity. Google's API logs containing AI Chat data are retained by Google for up to 55 days and then automatically purged. Support email correspondence is retained indefinitely unless you request deletion.

### 1.10 Analytics and Tracking

We do not operate any third-party analytics, crash reporting, or tracking services. The App does not contain Firebase, Sentry, Crashlytics, or any equivalent SDK. The only analytics or crash data that may be transmitted is through Apple's standard iOS analytics system (Settings → Privacy & Security → Analytics & Improvements → Share with App Developers), which you opt into at the operating system level and which you may disable at any time.

We do not track your general usage behaviour. The sole exception is the per-device AI Chat request counter described in Section 1.7, which exists solely to enforce rate limits and is not used for any other purpose.

**No tracking identifiers:** We do not use Apple's Advertising Identifier (IDFA), and we do not request permission to track you across apps and websites. The App does not present an App Tracking Transparency prompt because it has no need to do so.

### 1.11 Children's Privacy

The App is not directed to children under the age of 13, or the equivalent minimum age in your jurisdiction. We do not knowingly collect any data from children. If you are under this age, you are not permitted to use the App. The US Children's Online Privacy Protection Act (COPPA) applies a minimum age of 13; other jurisdictions may apply different thresholds.

### 1.12 Singapore Personal Data Protection Act (PDPA)

As the developer operates in Singapore, the Personal Data Protection Act 2012 (PDPA) applies to our processing of personal data in connection with the AI Chat feature. For the purposes of the PDPA, Low Timothy serves as the Data Protection Officer and may be contacted at lowlabs.dev@gmail.com. In the event of a data breach that is likely to result in significant harm to affected individuals or that affects 500 or more individuals, we will notify the Personal Data Protection Commission as required by law. Because we do not collect user email addresses or any other direct contact details, we will notify affected users through in-app notices and announcements on the App's App Store listing.

### 1.13 Changes to This Policy

We may modify this Privacy Policy from time to time. If we make material changes to how we handle your data, we will notify you within the App and, where legally required, obtain your acknowledgement via an in-app prompt before the changes take effect. Minor updates will be reflected by changing the "Last Updated" date above. Continued use of the App following any changes constitutes your acceptance of the revised policy.

The third-party providers used by the App (including hosting providers, AI providers, and market data providers) may change from time to time without notice. We will update this policy to reflect material changes to data flows.

### 1.14 Support Communications

If you choose to contact us at lowlabs.dev@gmail.com for support, feedback, or any other reason, the contents of your message and your email address will be received and stored by Google through its consumer Gmail service and retained indefinitely unless you request deletion. We use support correspondence solely to respond to your query. We may refer back to past support conversations to address recurring issues, but we do not use support data for marketing, newsletters, mailing lists, or any other purpose. We do not share support correspondence with any third party except where required by law.

If you include screenshots or attachments containing your financial data in a support email, please note that you are voluntarily sharing that information with us outside the App. You may request deletion of your support correspondence at any time by emailing the same address.

### 1.15 California Residents (CCPA)

If you are a resident of California, the rights described in Section 1.9 apply equivalently under the California Consumer Privacy Act (CCPA) and the California Privacy Rights Act (CPRA). In addition:

- **Categories of personal information collected:** For users who use the AI Chat feature, we process financial information and a device-scoped identifier as described in Section 1.7. For all users, we process support email correspondence as described in Section 1.14.
- **Sale or sharing of personal information:** We do not sell or share your personal information as those terms are defined under the CCPA. We have not done so in the preceding 12 months and we have no plans to do so.
- **Sensitive personal information:** We do not collect sensitive personal information as defined by the CCPA, except to the extent that financial data processed during AI Chat requests may qualify as such. We use this information solely to generate AI Chat responses and not for any purpose that would trigger your right to limit its use under the CCPA.
- **Non-discrimination:** We will not discriminate against you for exercising any of your CCPA rights.

---

## 2. Terms of Service

### 2.1 No Financial Advice

The App is a personal utility for tracking finances and investments. It is **not** a trading platform, brokerage service, tax preparation tool, or substitute for professional financial advice. We are not financial advisors, accountants, tax professionals, or fiduciaries, and we are not licensed to provide financial advisory services in any jurisdiction, including Singapore under the Financial Advisers Act 2001 or the Securities and Futures Act 2001.

The information, portfolio tracking, calculations, and AI-generated responses provided by the App are for informational and reference purposes only. You are solely responsible for your financial decisions, investment choices, tax obligations, and monetary management. You should consult a qualified professional before acting on any information displayed by the App.

### 2.2 AI-Generated Content

Responses generated by the AI Chat feature are produced by a large language model and may contain errors, omissions, or inaccuracies. This includes misinterpretation of your own financial data — for example, miscategorising a transaction, misreading an amount, confusing expenses with income, or drawing incorrect conclusions from your recorded notes. AI-generated content is not financial advice and should not be relied upon as such. You are responsible for independently verifying any output before acting on it or sharing it with others.

### 2.3 "As Is" Disclaimer

The App is provided on an "AS IS" and "AS AVAILABLE" basis. While we strive for accuracy, we make no warranties, express or implied, regarding the accuracy, reliability, completeness, or availability of any feature of the App, including but not limited to account balance calculations, budget tracking, spending summaries, credit card cycle computations, portfolio valuations, market data, currency conversions, AI responses, and data storage. Market prices and exchange rates may be delayed, inaccurate, or unavailable. You should independently verify all calculations before making any financial decisions.

### 2.4 Limitation of Liability

To the maximum extent permitted by applicable law, Low Timothy shall not be liable for any direct, indirect, incidental, consequential, special, or punitive damages arising out of or in connection with your use of the App. This includes, but is not limited to, financial losses, trading losses, data loss due to device failure or App deletion, or inaccuracies in calculations, market data, portfolio valuations, currency exchange rates, or AI-generated responses. Nothing in these terms excludes or limits any liability that cannot be excluded or limited under applicable law.

### 2.5 Data Backup

Your data is stored locally on your device. You are entirely responsible for backing up your data, whether via the App's built-in iCloud backup feature, your device's iCloud or iTunes backup, or the CSV or JSON export features. We are unable to recover lost, deleted, or corrupted data.

### 2.6 Acceptable Use

You agree to use the App lawfully and responsibly. You agree not to reverse engineer, decompile, disassemble, or attempt to extract the source code of the App, except to the extent such restriction is prohibited by applicable law. You agree not to attempt to circumvent rate limits, spoof request headers, or otherwise interfere with the operation of our server infrastructure.

### 2.7 Indemnification

You agree to indemnify, defend, and hold harmless Low Timothy from and against any claims, liabilities, damages, losses, and expenses, including reasonable legal fees, arising out of or connected with your access to or use of the App, your violation of these terms, or your violation of any third-party rights or applicable laws. This indemnity does not apply to the extent such claims arise from our own wilful misconduct or gross negligence, and is subject to any mandatory consumer protection laws in your jurisdiction.

### 2.8 Governing Law and Jurisdiction

These terms shall be governed by and construed in accordance with the laws of Singapore, without regard to its conflict of law provisions. You agree to submit to the exclusive personal jurisdiction of the courts located in Singapore for the resolution of any legal disputes. Nothing in these terms shall limit any rights you may have under the mandatory consumer protection laws of your country of residence, including the Singapore Consumer Protection (Fair Trading) Act 2003 and the Unfair Contract Terms Act 1977 where applicable.

**Informal resolution:** Before initiating any formal legal proceedings, you agree to first attempt to resolve the dispute by contacting us at lowlabs.dev@gmail.com with a clear description of the issue and the outcome you are seeking. We will make a good-faith effort to respond and resolve the matter within 30 days of receiving your notice.

### 2.9 Service Availability

We may temporarily or permanently discontinue the App, any feature of the App (including the AI Chat feature, iCloud backup, or third-party market data integrations), or any server-side service at any time, with or without notice, and without liability to you. We may also be unable to provide service during events beyond our reasonable control, including network outages, failures of third-party services (such as iCloud, Google's Gemini API, Railway's hosting platform, or our market data providers), and similar events. If we permanently discontinue Premium features, we encourage affected subscribers to request a refund through Apple as described in Section 1.6.

### 2.10 Severability

If any provision of these terms is found by a court of competent jurisdiction to be unenforceable or invalid, that specific provision will be limited or eliminated to the minimum extent necessary so that the remaining terms remain in full force and effect.

### 2.11 Apple App Store Additional Terms

By downloading the App from the Apple App Store, you acknowledge and agree to the following additional terms required by Apple:

- This agreement is concluded solely between you and Low Timothy, and not with Apple Inc. ("Apple"). Low Timothy, not Apple, is solely responsible for the App and its content.
- Apple has no obligation whatsoever to furnish any maintenance or support services with respect to the App.
- Low Timothy, not Apple, is responsible for addressing any claims by you or any third party relating to the App or your possession or use of the App, including product liability claims, claims that the App fails to conform to any applicable legal or regulatory requirement, and claims arising under consumer protection or similar legislation.
- You must comply with applicable third-party terms of agreement when using the App.
- Apple and Apple's subsidiaries are third-party beneficiaries of this agreement, and upon your acceptance of these terms, Apple will have the right to enforce this agreement against you as a third-party beneficiary.

---

## 3. Contact

If you have any questions, concerns, or feedback regarding this policy or the App, please contact:

**Low Timothy**
Email: lowlabs.dev@gmail.com
