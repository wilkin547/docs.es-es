---
title: Procesamiento por lotes
ms.date: 12/13/2019
description: Obtenga información sobre cómo ejecutar un lote de instrucciones SQL en un solo comando.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450313"
---
# <a name="batching"></a><span data-ttu-id="e4800-103">Procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="e4800-103">Batching</span></span>

<span data-ttu-id="e4800-104">SQLite no admite de forma nativa instrucciones SQL por lotes juntas en un solo comando.</span><span class="sxs-lookup"><span data-stu-id="e4800-104">SQLite doesn't natively support batching SQL statements together into a single command.</span></span> <span data-ttu-id="e4800-105">Sin embargo, dado que no hay ninguna red implicada, no sería realmente útil el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e4800-105">But because there's no network involved, it wouldn't really help performance anyway.</span></span> <span data-ttu-id="e4800-106">Sin embargo, Microsoft. Data. SQLite no implementa el procesamiento por lotes de instrucciones para que se comporte de forma más similar a otros proveedores de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e4800-106">Microsoft.Data.Sqlite does, however, implement statement batching as a convenience to make it behave more like other ADO.NET providers.</span></span>

<span data-ttu-id="e4800-107">Al llamar a <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, las instrucciones se ejecutan hasta la primera que devuelve los resultados.</span><span class="sxs-lookup"><span data-stu-id="e4800-107">When calling <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, statements are executed up to the first one that returns results.</span></span> <span data-ttu-id="e4800-108">La llamada a <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continúa ejecutando instrucciones hasta el siguiente que devuelve los resultados o hasta que llega al final del lote.</span><span class="sxs-lookup"><span data-stu-id="e4800-108">Calling <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continues executing statements until the next one that returns results or until it reaches the end of the batch.</span></span> <span data-ttu-id="e4800-109">La llamada a <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> o <xref:System.Data.Common.DbDataReader.Close%2A> ejecuta cualquier instrucción restante que no haya consumido `NextResult()`.</span><span class="sxs-lookup"><span data-stu-id="e4800-109">Calling <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> or <xref:System.Data.Common.DbDataReader.Close%2A> executes any remaining statements that haven't been consumed by `NextResult()`.</span></span> <span data-ttu-id="e4800-110">Si no desecha un lector de datos, el finalizador intenta ejecutar las instrucciones restantes, pero se omiten los errores que encuentre.</span><span class="sxs-lookup"><span data-stu-id="e4800-110">If you don't dispose a data reader, the finalizer tries to execute the remaining statements, but any errors it encounters are ignored.</span></span> <span data-ttu-id="e4800-111">Por este motivo, es importante desechar `DbDataReader` objetos al usar lotes.</span><span class="sxs-lookup"><span data-stu-id="e4800-111">Because of this, it's important to dispose `DbDataReader` objects when using batches.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a><span data-ttu-id="e4800-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4800-112">See also</span></span>

* [<span data-ttu-id="e4800-113">Bulk Insert</span><span class="sxs-lookup"><span data-stu-id="e4800-113">Bulk Insert</span></span>](bulk-insert.md)
