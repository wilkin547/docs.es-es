---
title: Bases de datos en memoria
ms.date: 12/13/2019
description: Aprenda a usar las bases de datos SQLite en memoria.
ms.openlocfilehash: fbda5787d95a9ce462752b985f847af0b0551fa6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555372"
---
# <a name="in-memory-databases"></a><span data-ttu-id="f42db-103">Bases de datos en memoria</span><span class="sxs-lookup"><span data-stu-id="f42db-103">In-memory databases</span></span>

<span data-ttu-id="f42db-104">Las bases de datos SQLite en memoria son bases de datos almacenadas por completo en la memoria, no en el disco.</span><span class="sxs-lookup"><span data-stu-id="f42db-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="f42db-105">Use el nombre de archivo de origen de datos especial `:memory:` para crear una base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="f42db-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="f42db-106">Cuando se cierra la conexión, se elimina la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f42db-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="f42db-107">Al utilizar `:memory:`, cada conexión crea su propia base de datos.</span><span class="sxs-lookup"><span data-stu-id="f42db-107">When using `:memory:`, each connection creates its own database.</span></span>

```connectionstring
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="f42db-108">Bases de datos en memoria que se pueden compartir</span><span class="sxs-lookup"><span data-stu-id="f42db-108">Shareable in-memory databases</span></span>

<span data-ttu-id="f42db-109">Las bases de datos en memoria se pueden compartir entre varias conexiones mediante el uso de `Mode=Memory` y `Cache=Shared` en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="f42db-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="f42db-110">La palabra clave `Data Source` se usa para asignar un nombre a la base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="f42db-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="f42db-111">Las cadenas de conexión que usen el mismo nombre tendrán acceso a la misma base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="f42db-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="f42db-112">La base de datos se conserva siempre y cuando al menos una conexión con ella permanezca abierta.</span><span class="sxs-lookup"><span data-stu-id="f42db-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="f42db-113">En GitHub se ofrece un [ejemplo](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) que lo muestra.</span><span class="sxs-lookup"><span data-stu-id="f42db-113">A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```connectionstring
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
