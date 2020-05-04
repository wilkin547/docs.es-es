---
title: Parámetros
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar los parámetros SQL.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401206"
---
# <a name="parameters"></a><span data-ttu-id="67549-103">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67549-103">Parameters</span></span>

<span data-ttu-id="67549-104">Los parámetros se usan como protección contra ataques por inyección de código SQL.</span><span class="sxs-lookup"><span data-stu-id="67549-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="67549-105">En lugar de concatenar la entrada proporcionada por el usuario con instrucciones SQL, use los parámetros para asegurarse de que la entrada solo se trate como un valor literal y no se ejecute nunca.</span><span class="sxs-lookup"><span data-stu-id="67549-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="67549-106">En SQLite, los parámetros se permiten normalmente en cualquier lugar en el que se permita un literal en las instrucciones SQL.</span><span class="sxs-lookup"><span data-stu-id="67549-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="67549-107">Los parámetros pueden tener como prefijo `:`, `@` o `$`.</span><span class="sxs-lookup"><span data-stu-id="67549-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="67549-108">Vea [Tipos de datos](types.md) para obtener más información sobre cómo se asignan los valores de .NET a los de SQLite.</span><span class="sxs-lookup"><span data-stu-id="67549-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="67549-109">Truncamiento</span><span class="sxs-lookup"><span data-stu-id="67549-109">Truncation</span></span>

<span data-ttu-id="67549-110">Use la propiedad <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> para truncar los valores TEXT y BLOB.</span><span class="sxs-lookup"><span data-stu-id="67549-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="67549-111">Tipos alternativos</span><span class="sxs-lookup"><span data-stu-id="67549-111">Alternative types</span></span>

<span data-ttu-id="67549-112">En ocasiones, es posible que quiera usar un tipo de SQLite alternativo.</span><span class="sxs-lookup"><span data-stu-id="67549-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="67549-113">Puede hacerlo si establece la propiedad <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>.</span><span class="sxs-lookup"><span data-stu-id="67549-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="67549-114">Se pueden usar las siguientes asignaciones de tipos alternativos.</span><span class="sxs-lookup"><span data-stu-id="67549-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="67549-115">Para las asignaciones predeterminadas, vea [Tipos de datos](types.md).</span><span class="sxs-lookup"><span data-stu-id="67549-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="67549-116">Valor</span><span class="sxs-lookup"><span data-stu-id="67549-116">Value</span></span>          | <span data-ttu-id="67549-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="67549-117">SqliteType</span></span> | <span data-ttu-id="67549-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="67549-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="67549-119">Char</span><span class="sxs-lookup"><span data-stu-id="67549-119">Char</span></span>           | <span data-ttu-id="67549-120">Integer</span><span class="sxs-lookup"><span data-stu-id="67549-120">Integer</span></span>    | <span data-ttu-id="67549-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="67549-121">UTF-16</span></span>           |
| <span data-ttu-id="67549-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="67549-122">DateTime</span></span>       | <span data-ttu-id="67549-123">Real</span><span class="sxs-lookup"><span data-stu-id="67549-123">Real</span></span>       | <span data-ttu-id="67549-124">Valor de día juliano</span><span class="sxs-lookup"><span data-stu-id="67549-124">Julian day value</span></span> |
| <span data-ttu-id="67549-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="67549-125">DateTimeOffset</span></span> | <span data-ttu-id="67549-126">Real</span><span class="sxs-lookup"><span data-stu-id="67549-126">Real</span></span>       | <span data-ttu-id="67549-127">Valor de día juliano</span><span class="sxs-lookup"><span data-stu-id="67549-127">Julian day value</span></span> |
| <span data-ttu-id="67549-128">GUID</span><span class="sxs-lookup"><span data-stu-id="67549-128">Guid</span></span>           | <span data-ttu-id="67549-129">Blob</span><span class="sxs-lookup"><span data-stu-id="67549-129">Blob</span></span>       |                  |
| <span data-ttu-id="67549-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="67549-130">TimeSpan</span></span>       | <span data-ttu-id="67549-131">Real</span><span class="sxs-lookup"><span data-stu-id="67549-131">Real</span></span>       | <span data-ttu-id="67549-132">En días</span><span class="sxs-lookup"><span data-stu-id="67549-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="67549-133">Parámetros de salida</span><span class="sxs-lookup"><span data-stu-id="67549-133">Output parameters</span></span>

<span data-ttu-id="67549-134">SQLite no admite parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="67549-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="67549-135">En su lugar, devuelve los valores de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="67549-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="67549-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="67549-136">See also</span></span>

* [<span data-ttu-id="67549-137">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="67549-137">Data types</span></span>](types.md)
