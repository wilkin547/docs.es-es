---
title: Cifrado
ms.date: 12/13/2019
description: Obtenga información acerca de cómo cifrar el archivo de base de datos.
ms.openlocfilehash: ccdd4b6b8642b3cde1c2667c9ca432a9b0ef21f2
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450487"
---
# <a name="encryption"></a>Cifrado

SQLite no admite el cifrado de archivos de base de datos de forma predeterminada. En su lugar, debe usar una versión modificada de SQLite como [Ver](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/)o [wxSQLite3](https://utelle.github.io/wxsqlite3). En este artículo se muestra el uso de una compilación no compatible de código abierto de SQLCipher, pero la información también se aplica a otras soluciones, ya que generalmente siguen el mismo patrón.

## <a name="installation"></a>Instalación de

### <a name="net-core-clitabnetcore-cli"></a>[CLI de .NET Core](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[Visual Studio](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

Para obtener más información sobre el uso de una biblioteca nativa diferente para el cifrado, consulte [versiones personalizadas de SQLite](custom-versions.md).

## <a name="specify-the-key"></a>Especificar la clave

Para habilitar el cifrado, especifique la clave mediante la palabra clave de cadena de conexión `Password`. Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> para agregar o actualizar el valor de los datos proporcionados por el usuario y evitar ataques de inyección de cadenas de conexión.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a>Regenerar la clave de la base de datos

Si desea cambiar la clave de cifrado de una base de datos, emita una instrucción `PRAGMA rekey`. Para descifrar la base de datos, especifique `NULL`.

Desafortunadamente, SQLite no admite parámetros en `PRAGMA` instrucciones. En su lugar, use la función `quote()` para evitar la inyección de SQL.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
