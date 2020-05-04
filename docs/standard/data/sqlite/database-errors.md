---
title: Errores de base de datos
ms.date: 12/13/2019
description: Se describe cómo se controlan en la biblioteca los errores y las retiradas de la base de datos.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450493"
---
# <a name="database-errors"></a><span data-ttu-id="8ea94-103">Errores de base de datos</span><span class="sxs-lookup"><span data-stu-id="8ea94-103">Database errors</span></span>

<span data-ttu-id="8ea94-104"><xref:Microsoft.Data.Sqlite.SqliteException> se inicia cuando se encuentra un error de SQLite.</span><span class="sxs-lookup"><span data-stu-id="8ea94-104"><xref:Microsoft.Data.Sqlite.SqliteException> is thrown when a SQLite error is encountered.</span></span> <span data-ttu-id="8ea94-105">El mensaje lo proporciona SQLite.</span><span class="sxs-lookup"><span data-stu-id="8ea94-105">The message is provided by SQLite.</span></span> <span data-ttu-id="8ea94-106">Las propiedades `SqliteErrorCode` y `SqliteExtendedErrorCode` contienen el [código de resultado](https://www.sqlite.org/rescode.html) SQLite del error.</span><span class="sxs-lookup"><span data-stu-id="8ea94-106">The `SqliteErrorCode` and `SqliteExtendedErrorCode` properties contain the SQLite [result code](https://www.sqlite.org/rescode.html) of the error.</span></span>

<span data-ttu-id="8ea94-107">Es posible que se produzcan errores cada vez que Microsoft.Data.SQLite interactúe con la biblioteca nativa de SQLite.</span><span class="sxs-lookup"><span data-stu-id="8ea94-107">Errors may be encountered any time the Microsoft.Data.Sqlite interacts with the native SQLite library.</span></span> <span data-ttu-id="8ea94-108">En la lista siguiente se muestran los escenarios comunes en los que se pueden producir errores:</span><span class="sxs-lookup"><span data-stu-id="8ea94-108">The following list shows the common scenarios where errors can occur:</span></span>

* <span data-ttu-id="8ea94-109">Apertura de una conexión.</span><span class="sxs-lookup"><span data-stu-id="8ea94-109">Opening a connection.</span></span>
* <span data-ttu-id="8ea94-110">Inicio de una transacción.</span><span class="sxs-lookup"><span data-stu-id="8ea94-110">Beginning a transaction.</span></span>
* <span data-ttu-id="8ea94-111">Ejecutar un comando.</span><span class="sxs-lookup"><span data-stu-id="8ea94-111">Executing a command.</span></span>
* <span data-ttu-id="8ea94-112">Llamada a <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ea94-112">Calling <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.</span></span>

<span data-ttu-id="8ea94-113">Considere detenidamente cómo controlará la aplicación estos errores.</span><span class="sxs-lookup"><span data-stu-id="8ea94-113">Consider carefully how your app will handle these errors.</span></span>

## <a name="locking-retries-and-timeouts"></a><span data-ttu-id="8ea94-114">Bloqueo, reintentos y tiempos de expiración</span><span class="sxs-lookup"><span data-stu-id="8ea94-114">Locking, retries, and timeouts</span></span>

<span data-ttu-id="8ea94-115">SQLite es agresivo en lo que respecta al bloqueo de tablas y archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="8ea94-115">SQLite is aggressive when it comes to locking tables and database files.</span></span> <span data-ttu-id="8ea94-116">Si la aplicación habilita el acceso simultáneo a bases de datos, es probable que se produzcan errores de estado ocupado y bloqueado.</span><span class="sxs-lookup"><span data-stu-id="8ea94-116">If your app enables any concurrent database access, you'll likely encounter busy and locked errors.</span></span> <span data-ttu-id="8ea94-117">Puede mitigar muchos errores mediante una [caché compartida](connection-strings.md#cache) y el [registro de escritura anticipada](async.md).</span><span class="sxs-lookup"><span data-stu-id="8ea94-117">You can mitigate many errors by using a [shared cache](connection-strings.md#cache) and [write-ahead logging](async.md).</span></span>

<span data-ttu-id="8ea94-118">Siempre que Microsoft.Data.SQLite encuentra un error de estado ocupado o bloqueado, realizará reintentos automáticos hasta que se ejecute correctamente o se alcance el tiempo de expiración del comando.</span><span class="sxs-lookup"><span data-stu-id="8ea94-118">Whenever Microsoft.Data.Sqlite encounters a busy or locked error, it will automatically retry until it succeeds or the command timeout is reached.</span></span>

<span data-ttu-id="8ea94-119">Puede aumentar el tiempo de expiración del comando si establece <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ea94-119">You can increase the timeout of command by setting <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>.</span></span> <span data-ttu-id="8ea94-120">El tiempo de expiración predeterminado es de 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="8ea94-120">The default timeout is 30 seconds.</span></span> <span data-ttu-id="8ea94-121">Un valor de `0` significa que no hay tiempo de expiración.</span><span class="sxs-lookup"><span data-stu-id="8ea94-121">A value of `0` means no timeout.</span></span>

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

<span data-ttu-id="8ea94-122">En ocasiones, Microsoft.Data.SQLitetiene que crear un objeto de comando implícito.</span><span class="sxs-lookup"><span data-stu-id="8ea94-122">Microsoft.Data.Sqlite sometimes needs to create an implicit command object.</span></span> <span data-ttu-id="8ea94-123">Por ejemplo, durante BeginTransaction.</span><span class="sxs-lookup"><span data-stu-id="8ea94-123">For example, during BeginTransaction.</span></span> <span data-ttu-id="8ea94-124">Para establecer el tiempo de expiración para estos comandos, use <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ea94-124">To set the timeout for these commands, use <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>.</span></span>

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a><span data-ttu-id="8ea94-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ea94-125">See also</span></span>

* [<span data-ttu-id="8ea94-126">Códigos de error de SQLite</span><span class="sxs-lookup"><span data-stu-id="8ea94-126">SQLite Error Codes</span></span>](https://www.sqlite.org/rescode.html)
* [<span data-ttu-id="8ea94-127">Bloqueo de archivos en SQLite</span><span class="sxs-lookup"><span data-stu-id="8ea94-127">File Locking In SQLite</span></span>](https://www.sqlite.org/lockingv3.html)
* [<span data-ttu-id="8ea94-128">Modo de caché compartida</span><span class="sxs-lookup"><span data-stu-id="8ea94-128">Shared-Cache Mode</span></span>](https://www.sqlite.org/sharedcache.html)
* [<span data-ttu-id="8ea94-129">Registro de escritura anticipada</span><span class="sxs-lookup"><span data-stu-id="8ea94-129">Write-Ahead Logging</span></span>](https://www.sqlite.org/wal.html)
