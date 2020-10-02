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
# <a name="encryption"></a><span data-ttu-id="e0b02-103">Cifrado</span><span class="sxs-lookup"><span data-stu-id="e0b02-103">Encryption</span></span>

<span data-ttu-id="e0b02-104">SQLite no permite cifrar archivos de base de datos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e0b02-104">SQLite doesn't support encrypting database files by default.</span></span> <span data-ttu-id="e0b02-105">En su lugar, hay que usar una versión modificada de SQLite, como [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/) o [wxSQLite3](https://utelle.github.io/wxsqlite3).</span><span class="sxs-lookup"><span data-stu-id="e0b02-105">Instead, you need to use a modified version of SQLite like [SEE](https://www.hwaci.com/sw/sqlite/see.html), [SQLCipher](https://www.zetetic.net/sqlcipher/), [SQLiteCrypt](http://www.sqlite-crypt.com/), or [wxSQLite3](https://utelle.github.io/wxsqlite3).</span></span> <span data-ttu-id="e0b02-106">En este artículo se explica cómo usar una versión de código abierto y no compatible de SQLCipher, pero esta información es igualmente válida en otras soluciones, ya que básicamente siguen el mismo patrón.</span><span class="sxs-lookup"><span data-stu-id="e0b02-106">This article demonstrates using an unsupported, open-source build of SQLCipher, but the information also applies to other solutions since they generally follow the same pattern.</span></span>

## <a name="installation"></a><span data-ttu-id="e0b02-107">Instalación</span><span class="sxs-lookup"><span data-stu-id="e0b02-107">Installation</span></span>

### <a name="net-core-cli"></a>[<span data-ttu-id="e0b02-108">CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="e0b02-108">.NET Core CLI</span></span>](#tab/netcore-cli)

```dotnetcli
dotnet remove package Microsoft.Data.Sqlite
dotnet add package Microsoft.Data.Sqlite.Core
dotnet add package SQLitePCLRaw.bundle_e_sqlcipher
```

### <a name="visual-studio"></a>[<span data-ttu-id="e0b02-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e0b02-109">Visual Studio</span></span>](#tab/visual-studio)

``` PowerShell
Remove-Package Microsoft.Data.Sqlite
Install-Package Microsoft.Data.Sqlite.Core
Install-Package SQLitePCLRaw.bundle_e_sqlcipher
```

---

<span data-ttu-id="e0b02-110">Para más información sobre cómo usar otra biblioteca nativa para el cifrado, vea [Versiones personalizadas de SQLite](custom-versions.md).</span><span class="sxs-lookup"><span data-stu-id="e0b02-110">For more information about using a different native library for encryption, see [Custom SQLite versions](custom-versions.md).</span></span>

## <a name="specify-the-key"></a><span data-ttu-id="e0b02-111">Especificación de la clave</span><span class="sxs-lookup"><span data-stu-id="e0b02-111">Specify the key</span></span>

<span data-ttu-id="e0b02-112">Para permitir el cifrado en una nueva base de datos, especifique la clave por medio de la palabra clave de cadena de conexión `Password`.</span><span class="sxs-lookup"><span data-stu-id="e0b02-112">To enable encryption on a new database, specify the key using the `Password` connection string keyword.</span></span> <span data-ttu-id="e0b02-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> para agregar o actualizar el valor de la entrada del usuario y evitar ataques de inyección de cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="e0b02-113">Use <xref:Microsoft.Data.Sqlite.SqliteConnectionStringBuilder> to add or update the value from user input and avoid connection string injection attacks.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_ConnectionStringBuilder)]

> [!TIP]
> <span data-ttu-id="e0b02-114">El método para cifrar y descifrar las bases de datos existentes varía en función de la solución que esté usando.</span><span class="sxs-lookup"><span data-stu-id="e0b02-114">The method for encrypting and decrypting existing databases varies depending on which solution you're using.</span></span> <span data-ttu-id="e0b02-115">Por ejemplo, debe usar la función `sqlcipher_export()` en SQLCipher.</span><span class="sxs-lookup"><span data-stu-id="e0b02-115">For example, you need to use the `sqlcipher_export()` function on SQLCipher.</span></span> <span data-ttu-id="e0b02-116">Consulte la documentación de la solución para más información.</span><span class="sxs-lookup"><span data-stu-id="e0b02-116">Check your solution's documentation for details.</span></span>

## <a name="rekeying-the-database"></a><span data-ttu-id="e0b02-117">Generación de una nueva clave de base de datos</span><span class="sxs-lookup"><span data-stu-id="e0b02-117">Rekeying the database</span></span>

<span data-ttu-id="e0b02-118">Si quiere cambiar la clave de cifrado de una base de datos, emita una instrucción `PRAGMA rekey`.</span><span class="sxs-lookup"><span data-stu-id="e0b02-118">If you want to change the key of an encrypted database, issue a `PRAGMA rekey` statement.</span></span>

<span data-ttu-id="e0b02-119">Desafortunadamente, SQLite no admite el uso de parámetros en las instrucciones `PRAGMA`.</span><span class="sxs-lookup"><span data-stu-id="e0b02-119">Unfortunately, SQLite doesn't support parameters in `PRAGMA` statements.</span></span> <span data-ttu-id="e0b02-120">En su lugar, use la función `quote()` para evitar la inyección de código SQL.</span><span class="sxs-lookup"><span data-stu-id="e0b02-120">Instead, use the `quote()` function to prevent SQL injection.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/EncryptionSample/Program.cs?name=snippet_Rekey)]
