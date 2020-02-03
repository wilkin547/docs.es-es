---
title: Versiones personalizadas de SQLite
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar una versión personalizada de la biblioteca nativa de SQLite.
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746994"
---
# <a name="custom-sqlite-versions"></a>Versiones personalizadas de SQLite

Microsoft. Data. SQLite se basa en SQLitePCLRaw. Puede usar versiones personalizadas de la biblioteca nativa de SQLite mediante una agrupación o mediante la configuración de un proveedor de SQLitePCLRaw.

## <a name="bundles"></a>Agrupaciones

SQLitePCLRaw proporciona paquetes de agrupación que facilitan la inclusión de las dependencias adecuadas en distintas plataformas.

El paquete principal de Microsoft. Data. SQLite se pone en SQLitePCLRaw. bundle_e_sqlite3 de forma predeterminada.

Para usar un paquete diferente, instale en su lugar el paquete de `Microsoft.Data.Sqlite.Core` junto con el paquete de agrupación que desea utilizar. Microsoft. Data. SQLite inicializa automáticamente las agrupaciones.

| Agrupación | Descripción |
| --- | --- |
| SQLitePCLRaw. bundle_e_sqlite3 | Proporciona una versión coherente de SQLite en todas las plataformas. Incluye las extensiones de árbol FTS4, FTS5, JSON1 y R *. Este es el valor predeterminado. |
| SQLitePCLRaw. bundle_green | Igual que bundle_e_sqlite3, excepto en iOS donde usa la biblioteca de SQLite del sistema. |
| SQLitePCLRaw. bundle_zetetic | Usa las compilaciones oficiales de SQLCipher de Zetetic (no se incluye). |
| SQLitePCLRaw. bundle_winsqlite3 | Usa winsqlite3. dll, la biblioteca SQLite del sistema en Windows 10. |
| SQLitePCLRaw. bundle_e_sqlcipher | Proporciona una compilación no oficial de código abierto de SQLCipher. |

Por ejemplo, para usar la compilación de código abierto no oficial de SQLCipher, use los siguientes comandos.

### <a name="net-core-clitabnetcore-cli"></a>[CLI de .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a>Proveedores de SQLitePCLRaw

Puede usar su propia compilación de SQLite aprovechando el paquete de `SQLitePCLRaw.provider.dynamic_cdecl`. En este caso, es responsable de implementar la biblioteca nativa con la aplicación. Tenga en cuenta que los detalles de la implementación de bibliotecas nativas con la aplicación varían considerablemente en función de la plataforma .NET y el tiempo de ejecución que esté usando.

En primer lugar, debe implementar IGetFunctionPointer. La implementación es bastante trivial en .NET Core.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

A continuación, configure el proveedor SQLitePCLRaw. Asegúrese de que esto se realiza antes de que se use Microsoft. Data. SQLite en la aplicación. Además, evite usar un paquete de agrupación de SQLitePCLRaw que puede invalidar el proveedor.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
