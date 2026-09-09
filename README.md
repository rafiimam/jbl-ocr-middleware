# OCR Middleware

Document OCR API for Jamuna Bank PLC. eKYC and other channels send an image. The API extracts fields, stores an audit row, and returns confidence scores. The provider can be swapped without changing the controller.

## What I owned

I designed the provider boundary. Today the implementation uses Google Cloud Vision. Azure or another engine can sit behind the same interface. Every request is logged with its source app and document type.

## Technologies

- .NET 8
- Entity Framework Core and SQL Server
- Google Cloud Vision client
- Swagger
- Multi-image requests in one call

## Features

- Single or multiple images per request
- Source tracking (which channel asked)
- Document types such as utility bills and identity cards
- Confidence on extracted fields
- Full audit of request and result
- Provider selected from configuration, credentials from a local file that is never committed

## Public sample

No Vision credentials file is included. `appsettings.example.json` in spirit: provider name only, path left blank.

Portfolio: https://rafiimam.github.io/rafi_portfolio/
