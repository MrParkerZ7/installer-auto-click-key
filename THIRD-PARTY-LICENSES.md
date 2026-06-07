# Third-Party Licenses

AutoKeyClick ships as a **self-contained** application — the build bundles the .NET
runtime, so end users need no separate install. This file attributes the third-party
components redistributed in (or used to build) the application.

## Redistributed in the application (self-contained build)

| Component | Publisher | License |
|-----------|-----------|---------|
| .NET 8 Runtime, incl. WPF & Windows Forms (Windows Desktop) | Microsoft Corporation | MIT — <https://github.com/dotnet/runtime/blob/main/LICENSE.TXT> |

The bundled .NET runtime and Windows Desktop libraries are © Microsoft Corporation,
redistributed under the MIT License.

## Build-time only (NOT redistributed in the released binaries)

| Component | License |
|-----------|---------|
| StyleCop.Analyzers 1.1.118 | MIT / Apache-2.0 — <https://github.com/DotNetAnalyzers/StyleCopAnalyzers/blob/master/LICENSE> |
| Microsoft.NET.ILLink.Tasks 8.0.8 | MIT |
| xUnit · FluentAssertions · Moq · coverlet (test projects only) | MIT / Apache-2.0 |

AutoKeyClick declares **no third-party runtime NuGet dependencies** of its own beyond the
Microsoft .NET platform.

<!-- TODO: if you add runtime NuGet packages later, regenerate this list with
     `dotnet list package --include-transitive` and append each redistributed package
     and its license here. -->

This project itself is licensed under the MIT License — see [LICENSE](LICENSE).
