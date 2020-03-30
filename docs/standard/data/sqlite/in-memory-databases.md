---
title: Bases de datos en memoria
ms.date: 12/13/2019
description: Aprenda a usar bases de datos SQLite en memoria.
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391213"
---
# <a name="in-memory-databases"></a><span data-ttu-id="c4688-103">Bases de datos en memoria</span><span class="sxs-lookup"><span data-stu-id="c4688-103">In-memory databases</span></span>

<span data-ttu-id="c4688-104">Las bases de datos en memoria de SQLite son bases de datos almacenadas completamente en memoria, no en disco.</span><span class="sxs-lookup"><span data-stu-id="c4688-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="c4688-105">Utilice el nombre `:memory:` de archivo de origen de datos especial para crear una base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="c4688-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="c4688-106">Cuando se cierra la conexión, se elimina la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c4688-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="c4688-107">Cuando `:memory:`se utiliza , cada conexión crea su propia base de datos.</span><span class="sxs-lookup"><span data-stu-id="c4688-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="c4688-108">Bases de datos en memoria compartibles</span><span class="sxs-lookup"><span data-stu-id="c4688-108">Shareable in-memory databases</span></span>

<span data-ttu-id="c4688-109">Las bases de datos en memoria `Mode=Memory` se `Cache=Shared` pueden compartir entre varias conexiones mediante el uso y la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="c4688-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="c4688-110">La `Data Source` palabra clave se utiliza para asignar un nombre a la base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="c4688-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="c4688-111">Las cadenas de conexión con el mismo nombre tendrán acceso a la misma base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="c4688-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="c4688-112">La base de datos persiste mientras al menos una conexión a ella permanezca abierta.</span><span class="sxs-lookup"><span data-stu-id="c4688-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="c4688-113">Un [ejemplo](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) que demuestra esto está disponible en GitHub.</span><span class="sxs-lookup"><span data-stu-id="c4688-113">A [sample](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
