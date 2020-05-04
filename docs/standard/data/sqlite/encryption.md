---
title: Cifrado
ms.date: 12/13/2019
description: Obtenga información sobre cómo cifrar el archivo de base de datos.
ms.openlocfilehash: ccdd4b6b8642b3cde1c2667c9ca432a9b0ef21f2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450487"
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

Para permitir el cifrado, especifique la clave por medio de la palabra clave de cadena de conexión `Password`. Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> para agregar o actualizar el valor de la entrada del usuario y evitar ataques de inyección de cadenas de conexión.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a>Generación de una nueva clave de base de datos

Si quiere cambiar la clave de cifrado de una base de datos, emita una instrucción `PRAGMA rekey`. Para descifrar la base de datos, especifique `NULL`.

Desafortunadamente, SQLite no admite el uso de parámetros en las instrucciones `PRAGMA`. En su lugar, use la función `quote()` para evitar la inyección de código SQL.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
