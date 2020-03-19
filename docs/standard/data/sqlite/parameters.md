---
title: Parámetros
ms.date: 12/13/2019
description: Aprenda a usar parámetros SQL.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401206"
---
# <a name="parameters"></a><span data-ttu-id="35e11-103">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35e11-103">Parameters</span></span>

<span data-ttu-id="35e11-104">Los parámetros se utilizan para proteger contra ataques de inyección SQL.</span><span class="sxs-lookup"><span data-stu-id="35e11-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="35e11-105">En lugar de concatenar la entrada del usuario con instrucciones SQL, utilice parámetros para asegurarse de que la entrada solo se trata como un valor literal y nunca se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="35e11-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="35e11-106">En SQLite, los parámetros normalmente se permiten en cualquier lugar donde se permite un literal en instrucciones SQL.</span><span class="sxs-lookup"><span data-stu-id="35e11-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="35e11-107">Los parámetros se `:`pueden `@`prefijar con , , o `$`.</span><span class="sxs-lookup"><span data-stu-id="35e11-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="35e11-108">Consulte [Tipos](types.md) de datos para obtener más información sobre cómo se asignan los valores de .NET a los valores de SQLite.</span><span class="sxs-lookup"><span data-stu-id="35e11-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="35e11-109">Truncamiento</span><span class="sxs-lookup"><span data-stu-id="35e11-109">Truncation</span></span>

<span data-ttu-id="35e11-110">Utilice <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> la propiedad para truncar los valores TEXT y BLOB.</span><span class="sxs-lookup"><span data-stu-id="35e11-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="35e11-111">Tipos alternativos</span><span class="sxs-lookup"><span data-stu-id="35e11-111">Alternative types</span></span>

<span data-ttu-id="35e11-112">A veces, es posible que desee utilizar un tipo SQLite alternativo.</span><span class="sxs-lookup"><span data-stu-id="35e11-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="35e11-113">Para ello, <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> establezca la propiedad.</span><span class="sxs-lookup"><span data-stu-id="35e11-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="35e11-114">Se pueden utilizar las siguientes asignaciones de tipos alternativos.</span><span class="sxs-lookup"><span data-stu-id="35e11-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="35e11-115">Para ver las asignaciones predeterminadas, consulte [Tipos de datos](types.md).</span><span class="sxs-lookup"><span data-stu-id="35e11-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="35e11-116">Value</span><span class="sxs-lookup"><span data-stu-id="35e11-116">Value</span></span>          | <span data-ttu-id="35e11-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="35e11-117">SqliteType</span></span> | <span data-ttu-id="35e11-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35e11-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="35e11-119">Char</span><span class="sxs-lookup"><span data-stu-id="35e11-119">Char</span></span>           | <span data-ttu-id="35e11-120">Entero</span><span class="sxs-lookup"><span data-stu-id="35e11-120">Integer</span></span>    | <span data-ttu-id="35e11-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="35e11-121">UTF-16</span></span>           |
| <span data-ttu-id="35e11-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="35e11-122">DateTime</span></span>       | <span data-ttu-id="35e11-123">Real</span><span class="sxs-lookup"><span data-stu-id="35e11-123">Real</span></span>       | <span data-ttu-id="35e11-124">Valor del día juliano</span><span class="sxs-lookup"><span data-stu-id="35e11-124">Julian day value</span></span> |
| <span data-ttu-id="35e11-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="35e11-125">DateTimeOffset</span></span> | <span data-ttu-id="35e11-126">Real</span><span class="sxs-lookup"><span data-stu-id="35e11-126">Real</span></span>       | <span data-ttu-id="35e11-127">Valor del día juliano</span><span class="sxs-lookup"><span data-stu-id="35e11-127">Julian day value</span></span> |
| <span data-ttu-id="35e11-128">Guid</span><span class="sxs-lookup"><span data-stu-id="35e11-128">Guid</span></span>           | <span data-ttu-id="35e11-129">Blob</span><span class="sxs-lookup"><span data-stu-id="35e11-129">Blob</span></span>       |                  |
| <span data-ttu-id="35e11-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="35e11-130">TimeSpan</span></span>       | <span data-ttu-id="35e11-131">Real</span><span class="sxs-lookup"><span data-stu-id="35e11-131">Real</span></span>       | <span data-ttu-id="35e11-132">En días</span><span class="sxs-lookup"><span data-stu-id="35e11-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="35e11-133">Parámetros de salida</span><span class="sxs-lookup"><span data-stu-id="35e11-133">Output parameters</span></span>

<span data-ttu-id="35e11-134">SQLite no admite parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="35e11-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="35e11-135">En su lugar, devuelve valores en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="35e11-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="35e11-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35e11-136">See also</span></span>

* [<span data-ttu-id="35e11-137">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="35e11-137">Data types</span></span>](types.md)
