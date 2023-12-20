---
type: NoteCard
---

# C# Unsafe Code
> Most of the C# code you write is "verifiably safe code." *Verifiably safe code* means .NET tools can verify that the code is safe. In general, safe code doesn't directly access memory using pointers. It also doesn't allocate raw memory. It creates managed objects instead.
>
> C# supports an [`unsafe`](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/unsafe) context, in which you may write *unverifiable* code. In an `unsafe` context, code may use pointers, allocate and free blocks of memory, and call methods using function pointers. Unsafe code in C# isn't necessarily dangerous; it's just code whose safety cannot be verified.
>
> — <https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/unsafe-code>

Some of the code that runs in Unity, might require “unsafe code” context. Unity supports unsafe code, with we can toggle in “Project Settings.”