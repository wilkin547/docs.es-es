---
title: Versiones personalizadas de SQLite
ms.date: 09/04/2020
description: Información sobre cómo usar una versión personalizada de la biblioteca SQLite nativa.
ms.openlocfilehash: fbf4b4cd33e6e890ce0c0cfe0b7688487b94b4a3
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2020
ms.locfileid: "89516143"
---
# <a name="custom-sqlite-versions"></a>Versiones personalizadas de SQLite

`Microsoft.Data.Sqlite` se basa en `SQLitePCLRaw`. Se pueden usar versiones personalizadas de la biblioteca SQLite nativa usando una agrupación o configurando un proveedor de `SQLitePCLRaw`.

## <a name="bundles"></a>Agrupaciones

`SQLitePCLRaw` proporciona paquetes de agrupación prácticos que hacen que sea muy fácil incorporar las dependencias adecuadas en distintas plataformas. De forma predeterminada, el paquete principal de `Microsoft.Data.Sqlite` incluye `SQLitePCLRaw.bundle_e_sqlite3`. Para usar otra agrupación, instale el paquete `Microsoft.Data.Sqlite.Core` en su lugar junto con el paquete de agrupación que quiera usar. `Microsoft.Data.Sqlite` inicializa las agrupaciones automáticamente.

| Agrupación | Descripción |
|--|--|
| [SQLitePCLRaw.bundle_e_sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlite3) | Proporciona la misma versión de SQLite en todas las plataformas. Incluye las extensiones FTS4, FTS5, JSON1 y R*Tree. Este es el valor predeterminado. |
| [SQLitePCLRaw.bundle_e_sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.bundle_e_sqlcipher) | Proporciona una compilación de código abierto no oficial de `SQLCipher`. |
| [SQLitePCLRaw.bundle_green](https://www.nuget.org/packages/SQLitePCLRaw.bundle_green) | Igual que `bundle_e_sqlite3`, salvo en iOS, donde usa la biblioteca SQLite del sistema. |
| [SQLitePCLRaw.bundle_sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.bundle_sqlite3) | Usa la biblioteca SQLite del sistema. |
| [SQLitePCLRaw.bundle_winsqlite3](https://www.nuget.org/packages/SQLitePCLRaw.bundle_winsqlite3) | Usa `winsqlite3.dll`, la biblioteca SQLite del sistema en Windows 10. |
| [SQLitePCLRaw.bundle_zetetic](https://www.nuget.org/packages/SQLitePCLRaw.bundle_zetetic) | Usa las compilaciones de `SQLCipher` oficiales de Zetetic (no se incluye). |

Por ejemplo, para usar la compilación de código abierto no oficial de `SQLCipher`, use los siguientes comandos.

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

## <a name="sqlitepclraw-available-providers"></a>Proveedores de SQLitePCLRaw disponibles

Cuando no se basa en un paquete, puede usar los proveedores disponibles de SQLite con el ensamblado principal.

| Proveedor | Descripción |
|--|--|
| [SQLitePCLRaw.provider.dynamic](https://www.nuget.org/packages/SQLitePCLRaw.provider.dynamic) | El proveedor de `dynamic` carga la biblioteca nativa en lugar de utilizar los atributos de <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>. Para obtener más información sobre el uso de este proveedor, vea el [uso del proveedor dinámico](#use-the-dynamic-provider). |
| [SQLitePCLRaw.provider.e_sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlite3) | `e_sqlite3` es el proveedor predeterminado. |
| [SQLitePCLRaw.provider.e_sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.provider.e_sqlcipher) | El proveedor `e_sqlcipher` es el `SQLCipher` no oficial y no compatible. |
| [SQLitePCLRaw.provider.sqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlite3) | El proveedor `sqlite3` es un elemento `SQLite` proporcionado por el sistema para iOS, macOS y Linux. |
| [SQLitePCLRaw.provider.sqlcipher](https://www.nuget.org/packages/SQLitePCLRaw.provider.sqlcipher) | El proveedor `sqlcipher` es para las compilaciones `SQLCipher` oficiales de `Zetetic`. |
| [SQLitePCLRaw.provider.winsqlite3](https://www.nuget.org/packages/SQLitePCLRaw.provider.winsqlite3) | El proveedor `winsqlite3` es para entornos de Windows 10. |

Para usar el proveedor `sqlite3`, use los comandos siguientes:

### <a name="net-core-cli"></a>[CLI de .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.core
dotnet add package SQLitePCLRaw.provider.sqlite3
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.core
Install-Package SQLitePCLRaw.provider.sqlite3
```

---

Con los paquetes instalados, establezca el proveedor en la instancia de `sqlite3`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SqliteProviderSample/Program.cs)]

## <a name="use-the-dynamic-provider"></a>Uso del proveedor dinámico

Para usar su propia compilación de SQLite, use el paquete `SQLitePCLRaw.provider.dynamic_cdecl`. En este caso, será su responsabilidad implementar la biblioteca nativa con la aplicación. Tenga en cuenta que los detalles de la implementación de bibliotecas nativas con su aplicación variarán considerablemente en función de la plataforma .NET y del runtime que use.

En primer lugar, deberá implementar `IGetFunctionPointer`. La implementación en .NET Core es la siguiente:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_NativeLibraryAdapter)]

A continuación, configure el proveedor `SQLitePCLRaw`. Asegúrese de llevar esto a cabo antes de que `Microsoft.Data.Sqlite` se use en la aplicación. Evite también usar un paquete de agrupación de `SQLitePCLRaw`, lo que podría invalidar el proveedor.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/SystemLibrarySample/Program.cs?name=snippet_SetProvider)]
