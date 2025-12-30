# CilpronMailSdk

CilpronMailSdk is the official C# client library for **CILPRON Limited’s Email API**.  
It provides a simple, strongly‑typed interface for sending emails, managing templates, and integrating advanced features without dealing with raw JSON or HTTP calls.

---

## 🚀 Features

- Send plain text and HTML emails
- Support for multiple recipients (To, CC, BCC)
- Attachments
- Templates and dynamic template data
- Categories and custom arguments
- IP pool selection
- Tracking settings (open/click/subscription)
- Mail settings (sandbox mode, spam check, footer injection)
- Strongly‑typed models and helper methods
- Async/await support

---

## 📦 Installation

Add the package via NuGet:

```bash
dotnet add package Cilpron.Mail

Or

PM> Install-Package Cilpron.Mail


🛠 Usage

``
using Cilpron.Mail;
using Cilpron.Mail.Models;
using Cilpron.Mail.Helpers;

var client = new CilpronMailClient("YOUR_API_KEY");

var from = new EmailAddress("noreply@cilpron.com", "CILPRON Limited");
var to = new EmailAddress("customer@example.com", "Customer");

var msg = MailHelper.CreateSingleEmail(
    from,
    to,
    "Welcome to Cilpron!",
    "Hello, thanks for joining us.",
    "<strong>Hello, thanks for joining us.</strong>"
);

var response = await client.SendEmailAsync(msg);

Console.WriteLine($"Status: {response.StatusCode}");
``
