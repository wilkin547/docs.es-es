---
title: Bases de datos en memoria
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar las bases de datos de SQLite en memoria.
ms.openlocfilehash: 16a9b6536fbfede203c24b757e96e28e7c49dc05
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777409"
---
# <a name="in-memory-databases"></a><span data-ttu-id="1eecc-103">Bases de datos en memoria</span><span class="sxs-lookup"><span data-stu-id="1eecc-103">In-memory databases</span></span>

<span data-ttu-id="1eecc-104">Las bases de datos en memoria de SQLite son bases de datos almacenadas por completo en la memoria, no en el disco.</span><span class="sxs-lookup"><span data-stu-id="1eecc-104">SQLite in-memory databases are databases stored entirely in memory, not on disk.</span></span> <span data-ttu-id="1eecc-105">Use el nombre de archivo de origen de datos Especial `:memory:` para crear una base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="1eecc-105">Use the special data source filename `:memory:` to create an in-memory database.</span></span> <span data-ttu-id="1eecc-106">Cuando se cierra la conexión, se elimina la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1eecc-106">When the connection is closed, the database is deleted.</span></span> <span data-ttu-id="1eecc-107">Al utilizar `:memory:`, cada conexión crea su propia base de datos.</span><span class="sxs-lookup"><span data-stu-id="1eecc-107">When using `:memory:`, each connection creates its own database.</span></span>

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a><span data-ttu-id="1eecc-108">Bases de datos en memoria que se pueden compartir</span><span class="sxs-lookup"><span data-stu-id="1eecc-108">Shareable in-memory databases</span></span>

<span data-ttu-id="1eecc-109">Las bases de datos en memoria se pueden compartir entre varias conexiones mediante `Mode=Memory` y `Cache=Shared` en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="1eecc-109">In-memory databases can be shared between multiple connections by using `Mode=Memory` and `Cache=Shared` in the connection string.</span></span> <span data-ttu-id="1eecc-110">La palabra clave `Data Source` se usa para asignar un nombre a la base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="1eecc-110">The `Data Source` keyword is used to give the in-memory database a name.</span></span> <span data-ttu-id="1eecc-111">Las cadenas de conexión que usen el mismo nombre tendrán acceso a la misma base de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="1eecc-111">Connection strings using the same name will access the same in-memory database.</span></span> <span data-ttu-id="1eecc-112">La base de datos se conserva siempre y cuando al menos una conexión con ella permanezca abierta.</span><span class="sxs-lookup"><span data-stu-id="1eecc-112">The database persists as long as at least one connection to it remains open.</span></span> <span data-ttu-id="1eecc-113">Un [ejemplo](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/InMemorySample/Program.cs) que muestra esto está disponible en github.</span><span class="sxs-lookup"><span data-stu-id="1eecc-113">A [sample](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/InMemorySample/Program.cs) demonstrating this is available on GitHub.</span></span>

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
