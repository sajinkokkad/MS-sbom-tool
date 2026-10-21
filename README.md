# SQL Injection Demo (C#) - Learning Only

An intentionally vulnerable console app used to demonstrate SQL injection and how
SAST (CodeQL) detects it. It uses an in-memory SQLite database with fake data.

> Do not deploy this or reuse the vulnerable pattern. Educational use only.

## Run
```bash
dotnet run
```
- Input `alice` returns one row in both lookups.
- Input `' OR '1'='1` returns **all rows** in the vulnerable lookup but **none** in the safe one.

## What to learn
- **Vulnerable:** `FindUserVulnerable` builds SQL by string concatenation (CWE-89).
- **Fixed:** `FindUserSafe` uses a parameterized query.

## Scan it
Push to GitHub and the included `CodeQL` workflow runs. Look under
**Security > Code scanning** for the `cs/sql-injection` alert on `Program.cs`.
