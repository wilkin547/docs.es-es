---
title: Limitaciones de Async
ms.date: 09/04/2020
description: Se explican las limitaciones de las API asincrónicas y algunas alternativas que puede usar en su lugar.
ms.openlocfilehash: 8b14fcfeb12d331d8d43ca6d77332007a12ae5dc
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2020
ms.locfileid: "89516000"
---
# <a name="async-limitations"></a><span data-ttu-id="5a848-103">Limitaciones de Async</span><span class="sxs-lookup"><span data-stu-id="5a848-103">Async limitations</span></span>

<span data-ttu-id="5a848-104">SQLite no es compatible con la E/S asincrónica.</span><span class="sxs-lookup"><span data-stu-id="5a848-104">SQLite doesn't support asynchronous I/O.</span></span> <span data-ttu-id="5a848-105">Los métodos asincrónicos de ADO.NET se ejecutarán de forma sincrónica en Microsoft.Data.SQLite.</span><span class="sxs-lookup"><span data-stu-id="5a848-105">Async ADO.NET methods will execute synchronously in Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="5a848-106">Evite llamarlos.</span><span class="sxs-lookup"><span data-stu-id="5a848-106">Avoid calling them.</span></span>

<span data-ttu-id="5a848-107">En su lugar, use una [caché compartida](connection-strings.md#cache) y el [registro de escritura anticipada](https://www.sqlite.org/wal.html) para mejorar el rendimiento y la simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="5a848-107">Instead, use a [shared cache](connection-strings.md#cache) and [write-ahead logging](https://www.sqlite.org/wal.html) to improve performance and concurrency.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> <span data-ttu-id="5a848-108">El registro de escritura anticipada está habilitado de forma predeterminada en las bases de datos creadas mediante [Entity Framework Core](/ef/core/).</span><span class="sxs-lookup"><span data-stu-id="5a848-108">Write-ahead logging is enabled by default on databases created using [Entity Framework Core](/ef/core/).</span></span>
