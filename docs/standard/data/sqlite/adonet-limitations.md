---
title: Limitaciones de ADO.NET
ms.date: 12/13/2019
description: Describe algunas de las limitaciones de ADO.NET que puede encontrar.
ms.openlocfilehash: b58fd3a9ea324e9c17ad21479e53e45f5982db9d
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450343"
---
# <a name="adonet-limitations"></a><span data-ttu-id="7d06b-103">Limitaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7d06b-103">ADO.NET limitations</span></span>

<span data-ttu-id="7d06b-104">Microsoft. Data. SQLite proporciona implementaciones de muchas de las abstracciones de ADO.NET, pero hay algunas limitaciones.</span><span class="sxs-lookup"><span data-stu-id="7d06b-104">Microsoft.Data.Sqlite provides implementations of many of the ADO.NET abstractions, but there are some limitations.</span></span>

## <a name="database-schema-information"></a><span data-ttu-id="7d06b-105">Información de esquema de base de datos</span><span class="sxs-lookup"><span data-stu-id="7d06b-105">Database schema information</span></span>

<span data-ttu-id="7d06b-106">Los metadatos acerca de los resultados de la consulta están disponibles mediante el método <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="7d06b-106">Metadata about query results is available using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method.</span></span>

<span data-ttu-id="7d06b-107">`DbConnection.GetSchema()` no está implementado.</span><span class="sxs-lookup"><span data-stu-id="7d06b-107">`DbConnection.GetSchema()` isn't implemented.</span></span> <span data-ttu-id="7d06b-108">Esta API no está bien definida, por lo que se recomienda recuperar los metadatos de la base de datos directamente mediante las API de SQLite estándar, como la tabla [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) y la pragma [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) .</span><span class="sxs-lookup"><span data-stu-id="7d06b-108">This API isn't well-defined, so we recommend retrieving database metadata directly using standard SQLite APIs like the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and the [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) PRAGMA.</span></span>

<span data-ttu-id="7d06b-109">Para obtener más información, vea [metadatos](metadata.md).</span><span class="sxs-lookup"><span data-stu-id="7d06b-109">For more information, see [Metadata](metadata.md).</span></span>

## <a name="systemtransactions"></a><span data-ttu-id="7d06b-110">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="7d06b-110">System.Transactions</span></span>

<span data-ttu-id="7d06b-111">Microsoft. Data. SQLite todavía no admite System. Transactions.</span><span class="sxs-lookup"><span data-stu-id="7d06b-111">Microsoft.Data.Sqlite doesn't yet support System.Transactions.</span></span> <span data-ttu-id="7d06b-112">En su lugar, use las transacciones ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="7d06b-112">Use ADO.NET transactions instead.</span></span> <span data-ttu-id="7d06b-113">Para obtener más información, vea [transacciones](transactions.md).</span><span class="sxs-lookup"><span data-stu-id="7d06b-113">For more information, see [Transactions](transactions.md).</span></span>

<span data-ttu-id="7d06b-114">Proporcione comentarios sobre la falta de compatibilidad con System. Transactions en el [#13825](https://github.com/aspnet/EntityFrameworkCore/issues/13825)de problemas.</span><span class="sxs-lookup"><span data-stu-id="7d06b-114">Provide feedback about the lack of support for System.Transactions on issue [#13825](https://github.com/aspnet/EntityFrameworkCore/issues/13825).</span></span>

## <a name="data-adapters"></a><span data-ttu-id="7d06b-115">Adaptadores de datos</span><span class="sxs-lookup"><span data-stu-id="7d06b-115">Data adapters</span></span>

<span data-ttu-id="7d06b-116">Microsoft. Data. SQLite todavía no ha implementado `DbDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="7d06b-116">`DbDataAdapter` isn't yet implemented by Microsoft.Data.Sqlite.</span></span> <span data-ttu-id="7d06b-117">Esto significa que solo puede usar `DataSet` ADO.NET y `DataTable` para cargar datos y no actualizarlos.</span><span class="sxs-lookup"><span data-stu-id="7d06b-117">This means you can only use ADO.NET `DataSet` and `DataTable` to load data and not update it.</span></span>

<span data-ttu-id="7d06b-118">Use el [#13838](https://github.com/aspnet/EntityFrameworkCore/issues/13838) de problemas para proporcionar comentarios sobre la implementación de `DbDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="7d06b-118">Use issue [#13838](https://github.com/aspnet/EntityFrameworkCore/issues/13838) to provide feedback about implementing `DbDataAdapter`.</span></span>

## <a name="output-parameters"></a><span data-ttu-id="7d06b-119">Parámetros de salida</span><span class="sxs-lookup"><span data-stu-id="7d06b-119">Output parameters</span></span>

<span data-ttu-id="7d06b-120">SQLite no admite parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="7d06b-120">SQLite doesn't support output parameters.</span></span>

## <a name="positional-parameters"></a><span data-ttu-id="7d06b-121">Parámetros posicionales</span><span class="sxs-lookup"><span data-stu-id="7d06b-121">Positional parameters</span></span>

<span data-ttu-id="7d06b-122">Microsoft. Data. SQLite solo admite [parámetros](parameters.md)con nombre.</span><span class="sxs-lookup"><span data-stu-id="7d06b-122">Microsoft.Data.Sqlite only supports named [parameters](parameters.md).</span></span> <span data-ttu-id="7d06b-123">No se admiten los parámetros posicionales.</span><span class="sxs-lookup"><span data-stu-id="7d06b-123">Positional parameters aren't supported.</span></span>

## <a name="stored-procedures"></a><span data-ttu-id="7d06b-124">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="7d06b-124">Stored procedures</span></span>

<span data-ttu-id="7d06b-125">SQLite no admite procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="7d06b-125">SQLite doesn't support stored procedures.</span></span>

## <a name="isolation-levels"></a><span data-ttu-id="7d06b-126">Niveles de aislamiento</span><span class="sxs-lookup"><span data-stu-id="7d06b-126">Isolation levels</span></span>

<span data-ttu-id="7d06b-127">Los niveles de aislamiento `Chaos` y `Snapshot` no se admiten en las transacciones de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7d06b-127">The `Chaos` and `Snapshot` isolation levels aren't supported in SQLite transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d06b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d06b-128">See also</span></span>

* [<span data-ttu-id="7d06b-129">Limitaciones de Async</span><span class="sxs-lookup"><span data-stu-id="7d06b-129">Async limitations</span></span>](async.md)
* [<span data-ttu-id="7d06b-130">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="7d06b-130">Data types</span></span>](types.md)
* [<span data-ttu-id="7d06b-131">Transacciones</span><span class="sxs-lookup"><span data-stu-id="7d06b-131">Transactions</span></span>](transactions.md)
