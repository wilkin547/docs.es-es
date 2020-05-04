---
title: Limitaciones de ADO.NET
ms.date: 12/13/2019
description: Describe algunas de las limitaciones de ADO.NET que puede encontrar.
ms.openlocfilehash: 8664b73071fc859ed30080f549b05e7d6ed020f4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901259"
---
# <a name="adonet-limitations"></a><span data-ttu-id="c61e1-103">Limitaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c61e1-103">ADO.NET limitations</span></span>

<span data-ttu-id="c61e1-104">Microsoft.Data.SQLite proporciona implementaciones de muchas de las abstracciones de ADO.NET, pero hay algunas limitaciones.</span><span class="sxs-lookup"><span data-stu-id="c61e1-104">Microsoft.Data.Sqlite provides implementations of many of the ADO.NET abstractions, but there are some limitations.</span></span>

## <a name="database-schema-information"></a><span data-ttu-id="c61e1-105">Información de esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="c61e1-105">Database schema information</span></span>

<span data-ttu-id="c61e1-106">Los metadatos sobre los resultados de la consulta están disponibles mediante el método <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="c61e1-106">Metadata about query results is available using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method.</span></span>

<span data-ttu-id="c61e1-107">`DbConnection.GetSchema()` no se implementa.</span><span class="sxs-lookup"><span data-stu-id="c61e1-107">`DbConnection.GetSchema()` isn't implemented.</span></span> <span data-ttu-id="c61e1-108">Esta API no está bien definida, por lo que se recomienda recuperar los metadatos de la base de datos directamente mediante las API de SQLite estándar, como la tabla [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) y la pragma [table_info](https://www.sqlite.org/pragma.html#pragma_table_info).</span><span class="sxs-lookup"><span data-stu-id="c61e1-108">This API isn't well-defined, so we recommend retrieving database metadata directly using standard SQLite APIs like the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and the [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA.</span></span>

<span data-ttu-id="c61e1-109">Para obtener más información, vea [Metadatos](metadata.md).</span><span class="sxs-lookup"><span data-stu-id="c61e1-109">For more information, see [Metadata](metadata.md).</span></span>

## <a name="systemtransactions"></a><span data-ttu-id="c61e1-110">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="c61e1-110">System.Transactions</span></span>

<span data-ttu-id="c61e1-111">Microsoft.Data.SQLite todavía no admite System.Transactions.</span><span class="sxs-lookup"><span data-stu-id="c61e1-111">Microsoft.Data.Sqlite doesn't yet support System.Transactions.</span></span> <span data-ttu-id="c61e1-112">En su lugar, use transacciones de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="c61e1-112">Use ADO.NET transactions instead.</span></span> <span data-ttu-id="c61e1-113">Para más información, consulte [Transacciones](transactions.md).</span><span class="sxs-lookup"><span data-stu-id="c61e1-113">For more information, see [Transactions](transactions.md).</span></span>

<span data-ttu-id="c61e1-114">Proporcione comentarios sobre la falta de compatibilidad con System.Transactions en la incidencia [#13825](https://github.com/dotnet/efcore/issues/13825).</span><span class="sxs-lookup"><span data-stu-id="c61e1-114">Provide feedback about the lack of support for System.Transactions on issue [#13825](https://github.com/dotnet/efcore/issues/13825).</span></span>

## <a name="data-adapters"></a><span data-ttu-id="c61e1-115">Adaptadores de datos</span><span class="sxs-lookup"><span data-stu-id="c61e1-115">Data adapters</span></span>

<span data-ttu-id="c61e1-116">Microsoft.Data.SQLite todavía no implementa `DbDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="c61e1-116">`DbDataAdapter` isn't yet implemented by Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="c61e1-117">Esto significa que solo puede usar `DataSet` y `DataTable` de ADO.NET para cargar datos y no actualizarlos.</span><span class="sxs-lookup"><span data-stu-id="c61e1-117">This means you can only use ADO.NET `DataSet` and `DataTable` to load data and not update it.</span></span>

<span data-ttu-id="c61e1-118">Use la incidencia [#13838](https://github.com/dotnet/efcore/issues/13838) para proporcionar comentarios sobre la implementación de `DbDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="c61e1-118">Use issue [#13838](https://github.com/dotnet/efcore/issues/13838) to provide feedback about implementing `DbDataAdapter`.</span></span>

## <a name="output-parameters"></a><span data-ttu-id="c61e1-119">Parámetros de salida</span><span class="sxs-lookup"><span data-stu-id="c61e1-119">Output parameters</span></span>

<span data-ttu-id="c61e1-120">SQLite no admite parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="c61e1-120">SQLite doesn't support output parameters.</span></span>

## <a name="positional-parameters"></a><span data-ttu-id="c61e1-121">Parámetros posicionales</span><span class="sxs-lookup"><span data-stu-id="c61e1-121">Positional parameters</span></span>

<span data-ttu-id="c61e1-122">Microsoft.Data.SQLite solo admite [parámetros](parameters.md) con nombre.</span><span class="sxs-lookup"><span data-stu-id="c61e1-122">Microsoft.Data.Sqlite only supports named [parameters](parameters.md).</span></span> <span data-ttu-id="c61e1-123">No se admiten los parámetros posicionales.</span><span class="sxs-lookup"><span data-stu-id="c61e1-123">Positional parameters aren't supported.</span></span>

## <a name="stored-procedures"></a><span data-ttu-id="c61e1-124">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="c61e1-124">Stored procedures</span></span>

<span data-ttu-id="c61e1-125">SQLite no admite procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="c61e1-125">SQLite doesn't support stored procedures.</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="c61e1-126">Niveles de aislamiento</span><span class="sxs-lookup"><span data-stu-id="c61e1-126">Isolation levels</span></span>

<span data-ttu-id="c61e1-127">Los niveles de aislamiento `Chaos` y `Snapshot` no se admiten en las transacciones de SQLite.</span><span class="sxs-lookup"><span data-stu-id="c61e1-127">The `Chaos` and `Snapshot` isolation levels aren't supported in SQLite transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="c61e1-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c61e1-128">See also</span></span>

* [<span data-ttu-id="c61e1-129">Limitaciones de Async</span><span class="sxs-lookup"><span data-stu-id="c61e1-129">Async limitations</span></span>](async.md)
* [<span data-ttu-id="c61e1-130">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="c61e1-130">Data types</span></span>](types.md)
* [<span data-ttu-id="c61e1-131">Transacciones</span><span class="sxs-lookup"><span data-stu-id="c61e1-131">Transactions</span></span>](transactions.md)
