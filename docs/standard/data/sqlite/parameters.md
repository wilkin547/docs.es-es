---
title: Parameters
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar los parámetros SQL.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450427"
---
# <a name="parameters"></a><span data-ttu-id="55215-103">Parameters</span><span class="sxs-lookup"><span data-stu-id="55215-103">Parameters</span></span>

<span data-ttu-id="55215-104">Los parámetros se usan para protegerse frente a ataques de inyección de SQL.</span><span class="sxs-lookup"><span data-stu-id="55215-104">Parameters are used to protect against SQL injection attacks.</span></span> <span data-ttu-id="55215-105">En lugar de concatenar los datos proporcionados por el usuario con instrucciones SQL, use los parámetros para asegurarse de que la entrada solo se trate como un valor literal y no se ejecute nunca.</span><span class="sxs-lookup"><span data-stu-id="55215-105">Instead of concatenating user input with SQL statements, use parameters to ensure input is only ever treated as a literal value and never executed.</span></span> <span data-ttu-id="55215-106">En SQLite, los parámetros se permiten normalmente en cualquier lugar en el que se permita un literal en las instrucciones SQL.</span><span class="sxs-lookup"><span data-stu-id="55215-106">In SQLite, parameters are typically allowed anywhere a literal is allowed in SQL statements.</span></span>

<span data-ttu-id="55215-107">Los parámetros pueden tener como prefijo `:`, `@`o `$`.</span><span class="sxs-lookup"><span data-stu-id="55215-107">Parameters can be prefixed with either `:`, `@`, or `$`.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

<span data-ttu-id="55215-108">Vea [tipos de datos](types.md) para obtener más información sobre cómo se asignan los valores de .net a los valores de SQLite.</span><span class="sxs-lookup"><span data-stu-id="55215-108">See [Data types](types.md) for details about how .NET values are mapped to SQLite values.</span></span>

## <a name="truncation"></a><span data-ttu-id="55215-109">Truncamiento</span><span class="sxs-lookup"><span data-stu-id="55215-109">Truncation</span></span>

<span data-ttu-id="55215-110">Use la propiedad <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> para truncar los valores de texto y BLOB.</span><span class="sxs-lookup"><span data-stu-id="55215-110">Use the <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> property to truncate TEXT and BLOB values.</span></span>

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a><span data-ttu-id="55215-111">Tipos alternativos</span><span class="sxs-lookup"><span data-stu-id="55215-111">Alternative types</span></span>

<span data-ttu-id="55215-112">En ocasiones, es posible que desee usar un tipo de SQLite alternativo.</span><span class="sxs-lookup"><span data-stu-id="55215-112">Sometimes, you may want to use an alternative SQLite type.</span></span> <span data-ttu-id="55215-113">Para ello, establezca la propiedad <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>.</span><span class="sxs-lookup"><span data-stu-id="55215-113">Do this by setting the <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> property.</span></span>

<span data-ttu-id="55215-114">Se pueden usar las siguientes asignaciones de tipos alternativos.</span><span class="sxs-lookup"><span data-stu-id="55215-114">The following alternative type mappings can be used.</span></span> <span data-ttu-id="55215-115">Para las asignaciones predeterminadas, vea [tipos de datos](types.md).</span><span class="sxs-lookup"><span data-stu-id="55215-115">For the default mappings, see [Data types](types.md).</span></span>

| <span data-ttu-id="55215-116">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="55215-116">Value</span></span>          | <span data-ttu-id="55215-117">SqliteType</span><span class="sxs-lookup"><span data-stu-id="55215-117">SqliteType</span></span> | <span data-ttu-id="55215-118">Notas</span><span class="sxs-lookup"><span data-stu-id="55215-118">Remarks</span></span>          |
| -------------- | ---------- | ---------------- |
| <span data-ttu-id="55215-119">Char</span><span class="sxs-lookup"><span data-stu-id="55215-119">Char</span></span>           | <span data-ttu-id="55215-120">Integer</span><span class="sxs-lookup"><span data-stu-id="55215-120">Integer</span></span>    | <span data-ttu-id="55215-121">UTF-16</span><span class="sxs-lookup"><span data-stu-id="55215-121">UTF-16</span></span>           |
| <span data-ttu-id="55215-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="55215-122">DateTime</span></span>       | <span data-ttu-id="55215-123">Real</span><span class="sxs-lookup"><span data-stu-id="55215-123">Real</span></span>       | <span data-ttu-id="55215-124">Valor de día juliano</span><span class="sxs-lookup"><span data-stu-id="55215-124">Julian day value</span></span> |
| <span data-ttu-id="55215-125">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="55215-125">DateTimeOffset</span></span> | <span data-ttu-id="55215-126">Real</span><span class="sxs-lookup"><span data-stu-id="55215-126">Real</span></span>       | <span data-ttu-id="55215-127">Valor de día juliano</span><span class="sxs-lookup"><span data-stu-id="55215-127">Julian day value</span></span> |
| <span data-ttu-id="55215-128">GUID</span><span class="sxs-lookup"><span data-stu-id="55215-128">Guid</span></span>           | <span data-ttu-id="55215-129">Blob</span><span class="sxs-lookup"><span data-stu-id="55215-129">Blob</span></span>       |                  |
| <span data-ttu-id="55215-130">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="55215-130">TimeSpan</span></span>       | <span data-ttu-id="55215-131">Real</span><span class="sxs-lookup"><span data-stu-id="55215-131">Real</span></span>       | <span data-ttu-id="55215-132">En días</span><span class="sxs-lookup"><span data-stu-id="55215-132">In days</span></span>          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a><span data-ttu-id="55215-133">Parámetros de salida</span><span class="sxs-lookup"><span data-stu-id="55215-133">Output parameters</span></span>

<span data-ttu-id="55215-134">SQLite no admite parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="55215-134">SQLite doesn't support output parameters.</span></span> <span data-ttu-id="55215-135">En su lugar, devuelve los valores de los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="55215-135">Return values in the query results instead.</span></span>

## <a name="see-also"></a><span data-ttu-id="55215-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="55215-136">See also</span></span>

* [<span data-ttu-id="55215-137">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="55215-137">Data types</span></span>](types.md)
