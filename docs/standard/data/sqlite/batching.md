---
title: Procesamiento por lotes
ms.date: 12/13/2019
description: Obtenga información sobre cómo ejecutar un lote de instrucciones SQL en un mismo comando.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450313"
---
# <a name="batching"></a><span data-ttu-id="99e16-103">Procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="99e16-103">Batching</span></span>

<span data-ttu-id="99e16-104">SQLite no admite de forma nativa la ejecución de instrucciones SQL por lotes en un mismo comando,</span><span class="sxs-lookup"><span data-stu-id="99e16-104">SQLite doesn't natively support batching SQL statements together into a single command.</span></span> <span data-ttu-id="99e16-105">pero, al no haber ninguna red implicada, hacerlo no supondría una mejora del rendimiento de todas formas.</span><span class="sxs-lookup"><span data-stu-id="99e16-105">But because there's no network involved, it wouldn't really help performance anyway.</span></span> <span data-ttu-id="99e16-106">Con todo, Microsoft.Data.Sqlite sí que implementa el procesamiento de instrucciones por lotes para hacer que se comporte de forma más parecida a otros proveedores de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="99e16-106">Microsoft.Data.Sqlite does, however, implement statement batching as a convenience to make it behave more like other ADO.NET providers.</span></span>

<span data-ttu-id="99e16-107">Al llamar a <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, las instrucciones se van ejecutando hasta la primera que devuelva resultados.</span><span class="sxs-lookup"><span data-stu-id="99e16-107">When calling <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, statements are executed up to the first one that returns results.</span></span> <span data-ttu-id="99e16-108">La llamada a <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> sigue ejecutando instrucciones hasta llegar a la siguiente que devuelva resultados o hasta alcanzar el final del lote.</span><span class="sxs-lookup"><span data-stu-id="99e16-108">Calling <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continues executing statements until the next one that returns results or until it reaches the end of the batch.</span></span> <span data-ttu-id="99e16-109">Cuando se llama a <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> o <xref:System.Data.Common.DbDataReader.Close%2A>, se ejecuta cualquier instrucción restante que `NextResult()` no haya usado.</span><span class="sxs-lookup"><span data-stu-id="99e16-109">Calling <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> or <xref:System.Data.Common.DbDataReader.Close%2A> executes any remaining statements that haven't been consumed by `NextResult()`.</span></span> <span data-ttu-id="99e16-110">Si no se dispone de un lector de datos, el finalizador intenta ejecutar las instrucciones restantes, pero los errores que encuentre se omitirán,</span><span class="sxs-lookup"><span data-stu-id="99e16-110">If you don't dispose a data reader, the finalizer tries to execute the remaining statements, but any errors it encounters are ignored.</span></span> <span data-ttu-id="99e16-111">de ahí que sea importante disponer de objetos `DbDataReader` al usar lotes.</span><span class="sxs-lookup"><span data-stu-id="99e16-111">Because of this, it's important to dispose `DbDataReader` objects when using batches.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a><span data-ttu-id="99e16-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="99e16-112">See also</span></span>

* [<span data-ttu-id="99e16-113">Inserción masiva</span><span class="sxs-lookup"><span data-stu-id="99e16-113">Bulk Insert</span></span>](bulk-insert.md)
