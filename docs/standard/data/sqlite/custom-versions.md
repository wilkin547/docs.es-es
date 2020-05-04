---
title: Versiones personalizadas de SQLite
ms.date: 12/13/2019
description: Información sobre cómo usar una versión personalizada de la biblioteca SQLite nativa.
ms.openlocfilehash: dd27278c1dbe17b12e5067d04d19043bf259b1e8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746994"
---
# <a name="custom-sqlite-versions"></a>Versiones personalizadas de SQLite

Microsoft.Data.Sqlite se basa en SQLitePCLRaw. Se pueden usar versiones personalizadas de la biblioteca SQLite nativa usando una agrupación o configurando un proveedor de SQLitePCLRaw.

## <a name="bundles"></a>Agrupaciones

SQLitePCLRaw proporciona paquetes de agrupación que hacen que sea muy fácil incorporar las dependencias adecuadas en distintas plataformas.

El paquete Microsoft.Data.SQLite principal incorpora SQLitePCLRaw.bundle_e_sqlite3 de forma predeterminada.

Para usar otra agrupación, instale el paquete `Microsoft.Data.Sqlite.Core` en su lugar junto con el paquete de agrupación que quiera usar. Microsoft.Data.Sqlite inicializa las agrupaciones automáticamente.

| Agrupación | Descripción |
| --- | --- |
| SQLitePCLRaw.bundle_e_sqlite3 | Proporciona la misma versión de SQLite en todas las plataformas. Incluye las extensiones FTS4, FTS5, JSON1 y R*Tree. Este es el valor predeterminado. |
| SQLitePCLRaw.bundle_green | Igual que bundle_e_sqlite3, salvo en iOS, donde usa la biblioteca SQLite del sistema. |
| SQLitePCLRaw.bundle_zetetic | Usa las compilaciones de SQLCipher oficiales de Zetetic (no se incluye). |
| SQLitePCLRaw.bundle_winsqlite3 | Usa winsqlite3.dll, la biblioteca SQLite del sistema en Windows 10. |
| SQLitePCLRaw.bundle_e_sqlcipher | Proporciona una compilación de código abierto no oficial de SQLCipher. |

Por ejemplo, para usar la compilación de código abierto no oficial de SQLCipher, use los siguientes comandos.

### <a name="net-core-cli"></a>[CLI de .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

## <a name="sqlitepclraw-providers"></a>Proveedores de SQLitePCLRaw

Para usar su propia compilación de SQLite, use el paquete `SQLitePCLRaw.provider.dynamic_cdecl`. En este caso, será su responsabilidad implementar la biblioteca nativa con la aplicación. Tenga en cuenta que los detalles de la implementación de bibliotecas nativas con su aplicación variarán considerablemente en función de la plataforma .NET y del runtime que use.

En primer lugar, debe implementar IGetFunctionPointer. La implementación es bastante fácil en .NET Core.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

Luego, configure el proveedor de SQLitePCLRaw. Asegúrese de llevar esto a cabo antes de que Microsoft.Data.SQLite se use en la aplicación. Evite también usar un paquete de agrupación de SQLitePCLRaw, lo que podría invalidar el proveedor.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
