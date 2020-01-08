---
title: Limitaciones de Async
ms.date: 12/13/2019
description: Explica las limitaciones de las API asincrónicas y algunas alternativas que puede usar en su lugar.
ms.openlocfilehash: 350237dc5c03023f60e9680e8b9c94aabb62606f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450337"
---
# <a name="async-limitations"></a><span data-ttu-id="47fab-103">Limitaciones de Async</span><span class="sxs-lookup"><span data-stu-id="47fab-103">Async limitations</span></span>

<span data-ttu-id="47fab-104">SQLite no es compatible con la e/s asincrónica.</span><span class="sxs-lookup"><span data-stu-id="47fab-104">SQLite doesn't support asynchronous I/O.</span></span> <span data-ttu-id="47fab-105">Los métodos asincrónicos de ADO.NET se ejecutarán sincrónicamente en Microsoft. Data. SQLite.</span><span class="sxs-lookup"><span data-stu-id="47fab-105">Async ADO.NET methods will execute synchronously in Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="47fab-106">Evite llamarlos.</span><span class="sxs-lookup"><span data-stu-id="47fab-106">Avoid calling them.</span></span>

<span data-ttu-id="47fab-107">En su lugar, use [el registro de escritura previa](https://www.sqlite.org/wal.html) para mejorar el rendimiento y la simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="47fab-107">Instead, use [write-ahead logging](https://www.sqlite.org/wal.html) to improve performance and concurrency.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> <span data-ttu-id="47fab-108">El registro de escritura previa está habilitado de forma predeterminada en las bases de datos creadas mediante [Entity Framework Core](/ef/core/).</span><span class="sxs-lookup"><span data-stu-id="47fab-108">Write-ahead logging is enabled by default on databases created using [Entity Framework Core](/ef/core/).</span></span>
