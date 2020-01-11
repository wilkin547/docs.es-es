---
title: Limitaciones de Dapper
ms.date: 12/13/2019
description: Describe algunas de las limitaciones que encontrará al usar Dapper.
ms.openlocfilehash: 396507f25f591a9ab5c3bb07c0af6fd8d175e4ea
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901207"
---
# <a name="dapper-limitations"></a><span data-ttu-id="f23d6-103">Limitaciones de Dapper</span><span class="sxs-lookup"><span data-stu-id="f23d6-103">Dapper limitations</span></span>

<span data-ttu-id="f23d6-104">Hay algunas limitaciones que debe tener en cuenta al usar Microsoft. Data. SQLite con [Dapper](https://stackexchange.github.io/Dapper/).</span><span class="sxs-lookup"><span data-stu-id="f23d6-104">There are a few limitations you should be aware of when using Microsoft.Data.Sqlite with [Dapper](https://stackexchange.github.io/Dapper/).</span></span>

## <a name="parameters"></a><span data-ttu-id="f23d6-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f23d6-105">Parameters</span></span>

<span data-ttu-id="f23d6-106">Los nombres de los parámetros de SQLite distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f23d6-106">SQLite parameter names are case-sensitive.</span></span> <span data-ttu-id="f23d6-107">Asegúrese de que los nombres de parámetro utilizados en SQL coinciden con las propiedades del objeto anónimo.</span><span class="sxs-lookup"><span data-stu-id="f23d6-107">Ensure that the parameter names used in SQL match the case of the anonymous object's properties.</span></span> <span data-ttu-id="f23d6-108">Problema [#18861](https://github.com/dotnet/efcore/issues/18861) mejoraría esta experiencia.</span><span class="sxs-lookup"><span data-stu-id="f23d6-108">Issue [#18861](https://github.com/dotnet/efcore/issues/18861) would improve this experience.</span></span>

<span data-ttu-id="f23d6-109">Dapper también espera parámetros para usar el prefijo `@`.</span><span class="sxs-lookup"><span data-stu-id="f23d6-109">Dapper also expects parameters to use the `@` prefix.</span></span> <span data-ttu-id="f23d6-110">Otros prefijos no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="f23d6-110">Other prefixes won't work.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a><span data-ttu-id="f23d6-111">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f23d6-111">Data types</span></span>

<span data-ttu-id="f23d6-112">Dapper Lee los valores mediante el indizador SqliteDataReader.</span><span class="sxs-lookup"><span data-stu-id="f23d6-112">Dapper reads values using the SqliteDataReader indexer.</span></span> <span data-ttu-id="f23d6-113">El tipo de valor devuelto de este indexador es Object, lo que significa que solo devolverá los valores Long, Double, String o Byte [].</span><span class="sxs-lookup"><span data-stu-id="f23d6-113">The return type of this indexer is object, which means it will only ever return long, double, string, or byte[] values.</span></span> <span data-ttu-id="f23d6-114">Para obtener más información, vea [tipos de datos](types.md).</span><span class="sxs-lookup"><span data-stu-id="f23d6-114">For more information, see [Data types](types.md).</span></span> <span data-ttu-id="f23d6-115">Dapper controla la mayoría de las conversiones entre estos y otros tipos primitivos.</span><span class="sxs-lookup"><span data-stu-id="f23d6-115">Dapper handles most conversions between these and other primitive types.</span></span> <span data-ttu-id="f23d6-116">Desafortunadamente, no controla `DateTimeOffset`, `Guid`o `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="f23d6-116">Unfortunately, it doesn't handle `DateTimeOffset`, `Guid`, or `TimeSpan`.</span></span> <span data-ttu-id="f23d6-117">Cree controladores de tipos si desea utilizar estos tipos en los resultados.</span><span class="sxs-lookup"><span data-stu-id="f23d6-117">Create type handlers if you want to use these types in your results.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

<span data-ttu-id="f23d6-118">No olvide agregar los controladores de tipo antes de realizar la consulta.</span><span class="sxs-lookup"><span data-stu-id="f23d6-118">Don't forget to add the type handlers before querying.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a><span data-ttu-id="f23d6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f23d6-119">See also</span></span>

* [<span data-ttu-id="f23d6-120">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f23d6-120">Data types</span></span>](types.md)
* [<span data-ttu-id="f23d6-121">Limitaciones de Async</span><span class="sxs-lookup"><span data-stu-id="f23d6-121">Async limitations</span></span>](async.md)
