# Simple Contacts

A lightweight desktop contact manager for Windows — keep people and companies organized, linked together, and easy to find, with import/export to the standard vCard format.

<p align="center">
  <img src="images/screenshot-company.png" alt="Company detail view" width="90%">
</p>
<p align="center">
  <img src="images/screenshot-contact.png" alt="Contact detail view" width="90%">
</p>

## Features

- **Contacts & Companies** — store both individually, each with their own profile.
- **Linking** — connect a contact to one or more companies (and see the connection from either side).
- **Multiple entries per field** — add several phone numbers, emails, and addresses per contact/company, each tagged by kind (Work, Home, Mobile, Direct, Other…).
- **Notes** — freeform notes attached to each contact or company.
- **Search** — quickly filter contacts and companies by name.
- **Import / Export (vCard)** — bring contacts in from a `.vcf` file, or export your data out to share or back up.
- **Local & offline** — all data is stored locally in a SQLite database; no account or internet connection required.

## Tech Stack

| Layer | Technology |
|---|---|
| UI | WPF (.NET 8), [CommunityToolkit.Mvvm](https://github.com/CommunityToolkit/dotnet) |
| Data access | Entity Framework Core 8 |
| Database | SQLite |
| vCard import/export | [FolkerKinzel.VCards](https://github.com/FolkerKinzel/VCards) |

## Getting Started

### Prerequisites

- Windows 10 (1809) or later
- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- Visual Studio 2022 with the **.NET desktop development** workload (includes WPF)

### Build & Run

```bash
git clone https://github.com/<your-username>/SimpleContacts.git
cd SimpleContacts
```

1. Open `SimpleContacts.sln` in Visual Studio 2022.
2. Set **SimpleContacts** as the startup project (it is by default).
3. Press **F5** (or `Build > Build Solution` then `Debug > Start Without Debugging`).

On first launch, the app creates its own local SQLite database under `%AppData%\SimpleContacts\` — no manual setup needed.

## Project Structure

```
SimpleContacts/              # WPF app (UI, views, startup)
SimpleContacts.Services/     # Business logic (contacts, companies, vCard, notifications)
SimpleContacts.Data/         # EF Core DbContext, entities, migrations
SimpleContacts.DataMapping/  # Mapping between data entities and domain models
SimpleContacts.Models/       # Domain/UI models (MVVM observable objects)
```

## License

Distributed under the MIT License. See [`LICENSE`](LICENSE) for details.
