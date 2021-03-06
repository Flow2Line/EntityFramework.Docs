---
title: Interoperability - Microsoft.Data.Sqlite
author: bricelam
ms.date: 11/25/2019
---
# Interoperability

Microsoft.Data.Sqlite uses SQLitePCLRaw to interact with the native SQLite library. SQLitePCLRaw provides a thin .NET API over the native SQLite API. SqliteConnection and SqliteDataReader provide access to the underlying SQLitePCLRaw objects letting you call these APIs directly.

Here is an example of calling sqlite3_trace to write executed SQL statements to the console.

[!code-csharp[](../samples/msdata-sqlite/InteropSample/Program.cs?name=snippet_Trace)]

And this example shows calling sqlite3_stmt_status to see how many SQLite virtual machine steps a SQL statement compiled into.

[!code-csharp[](../samples/msdata-sqlite/InteropSample/Program.cs?name=snippet_StatementStatus)]

The SQLitePCLRaw objects even expose a pointer to the native objects letting you P/Invoke additional native SQLite APIs.
