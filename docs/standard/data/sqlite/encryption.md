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
# <a name="encryption"></a><span data-ttu-id="fb5cf-103">Cifrado</span><span class="sxs-lookup"><span data-stu-id="fb5cf-103">Encryption</span></span>

<span data-ttu-id="fb5cf-104">SQLite no admite el cifrado de archivos de base de datos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fb5cf-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="fb5cf-105">En su lugar, debe usar una versión modificada de SQLite como [Ver](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/)o [wxSQLite3](https://utelle.github.io/wxsqlite3).</span><span class="sxs-lookup"><span data-stu-id="fb5cf-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="fb5cf-106">En este artículo se muestra el uso de una compilación no compatible de código abierto de SQLCipher, pero la información también se aplica a otras soluciones, ya que generalmente siguen el mismo patrón.</span><span class="sxs-lookup"><span data-stu-id="fb5cf-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="fb5cf-107">Instalación de</span><span class="sxs-lookup"><span data-stu-id="fb5cf-107">Installation</span></span>

### <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="fb5cf-108">CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="fb5cf-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="fb5cf-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fb5cf-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="fb5cf-110">Para obtener más información sobre el uso de una biblioteca nativa diferente para el cifrado, consulte [versiones personalizadas de SQLite](custom-versions.md).</span><span class="sxs-lookup"><span data-stu-id="fb5cf-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="fb5cf-111">Especificar la clave</span><span class="sxs-lookup"><span data-stu-id="fb5cf-111">Specify the key</span></span>

<span data-ttu-id="fb5cf-112">Para habilitar el cifrado, especifique la clave mediante la palabra clave de cadena de conexión `Password`.</span><span class="sxs-lookup"><span data-stu-id="fb5cf-112">To enable encryption, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="fb5cf-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> para agregar o actualizar el valor de los datos proporcionados por el usuario y evitar ataques de inyección de cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="fb5cf-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

## <a name="rekeying-the-database"></a><span data-ttu-id="fb5cf-114">Regenerar la clave de la base de datos</span><span class="sxs-lookup"><span data-stu-id="fb5cf-114">Rekeying the database</span></span>

<span data-ttu-id="fb5cf-115">Si desea cambiar la clave de cifrado de una base de datos, emita una instrucción `PRAGMA rekey`.</span><span class="sxs-lookup"><span data-stu-id="fb5cf-115">If you want to change the encryption key of a database, issue a `PRAGMA rekey` statement.</span></span> <span data-ttu-id="fb5cf-116">Para descifrar la base de datos, especifique `NULL`.</span><span class="sxs-lookup"><span data-stu-id="fb5cf-116">To decrypt the database, specify `NULL`.</span></span>

<span data-ttu-id="fb5cf-117">Desafortunadamente, SQLite no admite parámetros en `PRAGMA` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="fb5cf-117">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="fb5cf-118">En su lugar, use la función `quote()` para evitar la inyección de SQL.</span><span class="sxs-lookup"><span data-stu-id="fb5cf-118">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
