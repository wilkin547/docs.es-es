---
title: Inserción masiva
ms.date: 12/13/2019
description: Sugerencias de rendimiento que puede usar al realizar numerosos cambios en la base de datos.
ms.openlocfilehash: 9d87d5c8d70f8e70479f9aa02b7802f73b88de9e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450301"
---
# <a name="bulk-insert"></a><span data-ttu-id="e8141-103">Inserción masiva</span><span class="sxs-lookup"><span data-stu-id="e8141-103">Bulk insert</span></span>

<span data-ttu-id="e8141-104">SQLite no tiene ninguna manera especial de insertar datos de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="e8141-104">SQLite doesn't have any special way to bulk insert data.</span></span> <span data-ttu-id="e8141-105">Para obtener un rendimiento óptimo al insertar o actualizar datos, asegúrese de hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8141-105">To get optimal performance when inserting or updating data, ensure that you do the following:</span></span>

- <span data-ttu-id="e8141-106">Use una transacción.</span><span class="sxs-lookup"><span data-stu-id="e8141-106">Use a transaction.</span></span>
- <span data-ttu-id="e8141-107">Reutilice el mismo comando con parámetros.</span><span class="sxs-lookup"><span data-stu-id="e8141-107">Reuse the same parameterized command.</span></span> <span data-ttu-id="e8141-108">Las ejecuciones posteriores volverán a usar la compilación de la primera.</span><span class="sxs-lookup"><span data-stu-id="e8141-108">Subsequent executions will reuse the compilation of the first one.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BulkInsertSample/Program.cs?name=snippet_BulkInsert)]
