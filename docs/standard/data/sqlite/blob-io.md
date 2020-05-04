---
title: E/S de blob
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar la característica de E/S de blob de SQLite.
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450307"
---
# <a name="blob-io"></a><span data-ttu-id="ff464-103">E/S de blob</span><span class="sxs-lookup"><span data-stu-id="ff464-103">Blob I/O</span></span>

<span data-ttu-id="ff464-104">El uso de memoria mientras se leen y escriben objetos grandes se puede reducir transmitiendo los datos dentro y fuera de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ff464-104">You can reduce memory usage while reading and writing large objects by streaming the data into and out of the database.</span></span> <span data-ttu-id="ff464-105">Esto puede ser especialmente útil al analizar o transformar los datos.</span><span class="sxs-lookup"><span data-stu-id="ff464-105">This can be especially useful when parsing or transforming the data.</span></span>

<span data-ttu-id="ff464-106">Empiece insertando una fila del modo habitual.</span><span class="sxs-lookup"><span data-stu-id="ff464-106">Start by inserting a row as normal.</span></span> <span data-ttu-id="ff464-107">Use la función SQL `zeroblob()` para asignar espacio en la base de datos para que contenga el objeto grande.</span><span class="sxs-lookup"><span data-stu-id="ff464-107">Use the `zeroblob()` SQL function to allocate space in the database to hold the large object.</span></span> <span data-ttu-id="ff464-108">La función `last_insert_rowid()` proporciona un método cómodo de obtener el ROWID.</span><span class="sxs-lookup"><span data-stu-id="ff464-108">The `last_insert_rowid()` function provides a convenient way to get its rowid.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

<span data-ttu-id="ff464-109">Después de insertar la fila, abra una secuencia para escribir el objeto grande usando <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span><span class="sxs-lookup"><span data-stu-id="ff464-109">After inserting the row, open a stream to write the large object using <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

<span data-ttu-id="ff464-110">Para transmitir el objeto grande fuera de la base de datos, hay que seleccionar el ROWID o uno de sus alias como se muestra aquí, además de la columna del objeto grande.</span><span class="sxs-lookup"><span data-stu-id="ff464-110">To stream the large object out of the database, you must select the rowid or one of its aliases as show here in addition to the large object's column.</span></span> <span data-ttu-id="ff464-111">Si no se selecciona el ROWID, se cargará en la memoria el objeto entero.</span><span class="sxs-lookup"><span data-stu-id="ff464-111">If you don't select the rowid, the entire object will be loaded into memory.</span></span> <span data-ttu-id="ff464-112">El objeto devuelto por `GetStream()` será un elemento `SqliteBlob` si el proceso se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="ff464-112">The object returned by `GetStream()` will be a `SqliteBlob` when done correctly.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
