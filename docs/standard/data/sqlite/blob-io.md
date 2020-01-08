---
title: E/s de BLOB
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar la característica de e/s de BLOB de SQLite.
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450307"
---
# <a name="blob-io"></a><span data-ttu-id="ac677-103">E/s de BLOB</span><span class="sxs-lookup"><span data-stu-id="ac677-103">Blob I/O</span></span>

<span data-ttu-id="ac677-104">Puede reducir el uso de memoria mientras lee y escribe objetos grandes transmitiendo los datos dentro y fuera de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ac677-104">You can reduce memory usage while reading and writing large objects by streaming the data into and out of the database.</span></span> <span data-ttu-id="ac677-105">Esto puede ser especialmente útil cuando se analizan o transforman los datos.</span><span class="sxs-lookup"><span data-stu-id="ac677-105">This can be especially useful when parsing or transforming the data.</span></span>

<span data-ttu-id="ac677-106">Empiece por insertar una fila como normal.</span><span class="sxs-lookup"><span data-stu-id="ac677-106">Start by inserting a row as normal.</span></span> <span data-ttu-id="ac677-107">Utilice la función SQL `zeroblob()` para asignar espacio en la base de datos para que contenga el objeto grande.</span><span class="sxs-lookup"><span data-stu-id="ac677-107">Use the `zeroblob()` SQL function to allocate space in the database to hold the large object.</span></span> <span data-ttu-id="ac677-108">La función `last_insert_rowid()` proporciona una manera cómoda de obtener el ROWID.</span><span class="sxs-lookup"><span data-stu-id="ac677-108">The `last_insert_rowid()` function provides a convenient way to get its rowid.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

<span data-ttu-id="ac677-109">Después de insertar la fila, abra una secuencia para escribir el objeto grande mediante <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span><span class="sxs-lookup"><span data-stu-id="ac677-109">After inserting the row, open a stream to write the large object using <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

<span data-ttu-id="ac677-110">Para transmitir el objeto grande fuera de la base de datos, debe seleccionar el ROWID o uno de sus alias como se muestra aquí además de la columna del objeto grande.</span><span class="sxs-lookup"><span data-stu-id="ac677-110">To stream the large object out of the database, you must select the rowid or one of its aliases as show here in addition to the large object's column.</span></span> <span data-ttu-id="ac677-111">Si no selecciona ROWID, todo el objeto se cargará en la memoria.</span><span class="sxs-lookup"><span data-stu-id="ac677-111">If you don't select the rowid, the entire object will be loaded into memory.</span></span> <span data-ttu-id="ac677-112">El objeto devuelto por `GetStream()` será una `SqliteBlob` cuando se haya realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="ac677-112">The object returned by `GetStream()` will be a `SqliteBlob` when done correctly.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
