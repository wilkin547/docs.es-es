---
title: System.DateTimeOffset (Métodos)
ms.date: 03/30/2017
ms.assetid: 25b3e5c0-7603-4a70-b3e5-2149e3da69a2
ms.openlocfilehash: 288a0d99feecdeccc0d215ec3c14ec31bb3ccb54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149726"
---
# <a name="systemdatetimeoffset-methods"></a><span data-ttu-id="3963b-102">System.DateTimeOffset (Métodos)</span><span class="sxs-lookup"><span data-stu-id="3963b-102">System.DateTimeOffset Methods</span></span>
<span data-ttu-id="3963b-103">LINQ to SQL permite llamar a la mayoría de los métodos, operadores y propiedades de <xref:System.DateTimeOffset?displayProperty=nameWithType> desde las consultas LINQ to SQL, cuando se hayan asignado en el modelo de objetos o en el archivo de asignación externo.</span><span class="sxs-lookup"><span data-stu-id="3963b-103">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call most of the <xref:System.DateTimeOffset?displayProperty=nameWithType> methods, operators, and properties from within your LINQ to SQL queries.</span></span>  
  
 <span data-ttu-id="3963b-104">Los únicos métodos no admitidos son los heredados de <xref:System.Object?displayProperty=nameWithType> que no tienen sentido en el contexto de las consultas LINQ to SQL, como: `Finalize`, `GetHashCode`, `GetType` y `MemberwiseClone`.</span><span class="sxs-lookup"><span data-stu-id="3963b-104">The only methods not supported are those inherited from <xref:System.Object?displayProperty=nameWithType> that do not make sense in the context of LINQ to SQL queries, such as: `Finalize`, `GetHashCode`, `GetType`, and `MemberwiseClone`.</span></span> <span data-ttu-id="3963b-105">Estos métodos no se admiten porque LINQ to SQL no puede convertirlos para su ejecución en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3963b-105">These methods are not supported because LINQ to SQL cannot translate them for execution on the SQL Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3963b-106">La estructura de Common Language Runtime (CLR) <xref:System.DateTimeOffset?displayProperty=nameWithType> y la funcionalidad de asignarla a una columna `DATETIMEOFFSET` de SQL con LINQ to SQL, requiere .NET Framework 3.5 SP1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="3963b-106">The common language runtime (CLR) <xref:System.DateTimeOffset?displayProperty=nameWithType> structure, and the ability to map it to a SQL `DATETIMEOFFSET` column with LINQ to SQL, requires the .NET Framework 3.5 SP1 or beyond.</span></span> <span data-ttu-id="3963b-107">La columna `DATETIMEOFFSET` de SQL está disponible sólo en Microsoft SQL Server 2008 y posterior.</span><span class="sxs-lookup"><span data-stu-id="3963b-107">The SQL `DATETIMEOFFSET` column is only available in Microsoft SQL Server 2008 and beyond.</span></span>  
  
## <a name="sqlmethods-date-and-time-methods"></a><span data-ttu-id="3963b-108">Métodos Date y Time de SQLMethods</span><span class="sxs-lookup"><span data-stu-id="3963b-108">SQLMethods Date and Time Methods</span></span>  
 <span data-ttu-id="3963b-109">Además de los métodos proporcionados por la estructura <xref:System.DateTimeOffset>, LINQ to SQL proporciona los métodos citados en la siguiente tabla desde la clase <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> para trabajar con fechas y horas.</span><span class="sxs-lookup"><span data-stu-id="3963b-109">In addition to the methods offered by the <xref:System.DateTimeOffset> structure, LINQ to SQL offers the methods listed in the following table from the <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> class for working with date and time.</span></span>  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="3963b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="3963b-110">See also</span></span>

- [<span data-ttu-id="3963b-111">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="3963b-111">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="3963b-112">Creación del modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="3963b-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [<span data-ttu-id="3963b-113">Asignación de tipos entre CLR y SQL</span><span class="sxs-lookup"><span data-stu-id="3963b-113">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
