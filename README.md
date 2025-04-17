# ⚡️ EFWatch – The EF Core Performance Profiler

**Get insights. Save queries. Boost performance.**

EFWatch is a dynamic performance profiling plugin for Entity Framework Core. Designed for developers who care about fast queries, clean architecture, and production-ready insights.

---

## 🚀 Features

- 🕵️‍♂️ **Query Tracking** – Detects unnecessary tracking usage.
- 🧩 **AsSplitQuery Comparison** – Automatically benchmarks SplitQuery vs SingleQuery in the background.
- 🔄 **Batch Update Detection** – Warns about repeated `SaveChanges()` calls in loops.
- 💤 **Async Method Detection** – Highlights sync DB methods where async should be used.
- 📦 **Large Object Fetching** – Detects when heavy entities are loaded but barely accessed.
- 🔁 **Count() in Loops** – Spots repeated `.Count()` calls in iterations.
- 📉 **Low-Load Activation** (Pro) – Activates only during low system activity.
- 🌫️ **Shadow Queries** (Pro) – Run background queries without impacting production.
- 🧱 **Extensible Rule Engine** (Pro) – Add custom rules for deep performance analysis.

---

## ⚙️ Installation

```bash
dotnet add package EFWatch
```

For Pro users:

```bash
dotnet add package EFWatch.Pro
```

---

## 🧑‍💻 Usage Example

```csharp
public class AppDbContext : DbContext
{
    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        optionsBuilder
            .UseSqlServer("your-connection-string")
            .UseEFWatch(() => IsProfilerEnabled());
    }

    private bool IsProfilerEnabled()
    {
        // Example: enable profiler only in development
        return Environment.GetEnvironmentVariable("EFWATCH") == "true";
    }
}
```

---

## 🔍 Rules in This Version

✅ Autodetect AsSplitQuery  
✅ Detect Tracking vs NoTracking  
✅ Detect Batch Updates  
✅ Detect Async vs Sync Queries  
✅ Detect Multiple SaveChanges()  
✅ Detect Multiple `.Count()` Calls  
✅ Detect Large Transactions  
✅ Detect Large Object Fetches  
✅ Detect Missing Pagination  
🔒 Shadow Queries (Pro)  
🔒 Extensible Rule Engine (Pro)  
🔒 Low-Load Based Activation (Pro)  
🔒 Logging to File/Console (Pro)

---

## 💼 Why EFWatch?

- 🔎 Real-time insights into EF Core behavior
- ⚡️ Detect costly patterns before they hit production
- 🔄 Easy to integrate with existing codebases
- 🧩 Modular, extensible & Open Source friendly
- 💸 Professional Pro version with premium insights

---

## 🤝 Contributing

EFWatch is built by the community – and we’d love your help!  
Want to write new rules, fix bugs, or extend the core?

> Check out our [Contributing Guide](CONTRIBUTING.md) to get started!

---

## 🧠 Made by Developers, for Developers

Created with ❤️ by lecramr & contributors to help teams build faster, cleaner apps with EF Core.

---

## 📬 Contact & Support

Have feedback or want to try EFWatch Pro?  
Open an [issue](https://github.com/lecramr/efwatch/issues).
