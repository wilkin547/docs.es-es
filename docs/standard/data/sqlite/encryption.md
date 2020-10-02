---
title: Cifrado
ms.date: 09/08/2020
description: Obtenga información sobre cómo cifrar el archivo de base de datos.
ms.openlocfilehash: 1b33e1510a269aba87caba2cd39faab33791aa55
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203415"
---
# <a name="encryption"></a>Cifrado

SQLite no permite cifrar archivos de base de datos de forma predeterminada. En su lugar, hay que usar una versión modificada de SQLite, como [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/) o [wxSQLite3](https://utelle.github.io/wxsqlite3). En este artículo se explica cómo usar una versión de código abierto y no compatible de SQLCipher, pero esta información es igualmente válida en otras soluciones, ya que básicamente siguen el mismo patrón.

## <a name="installation"></a>Instalación

### <a name="net-core-cli"></a>[CLI de .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

Para más información sobre cómo usar otra biblioteca nativa para el cifrado, vea [Versiones personalizadas de SQLite](custom-versions.md).

## <a name="specify-the-key"></a>Especificación de la clave

Para permitir el cifrado en una nueva base de datos, especifique la clave por medio de la palabra clave de cadena de conexión `Password`. Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> para agregar o actualizar el valor de la entrada del usuario y evitar ataques de inyección de cadenas de conexión.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

> [!TIP]
> El método para cifrar y descifrar las bases de datos existentes varía en función de la solución que esté usando. Por ejemplo, debe usar la función `sqlcipher_export()` en SQLCipher. Consulte la documentación de la solución para más información.

## <a name="rekeying-the-database"></a>Generación de una nueva clave de base de datos

Si quiere cambiar la clave de cifrado de una base de datos, emita una instrucción `PRAGMA rekey`.

Desafortunadamente, SQLite no admite el uso de parámetros en las instrucciones `PRAGMA`. En su lugar, use la función `quote()` para evitar la inyección de código SQL.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
