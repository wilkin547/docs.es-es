---
description: 'Más información sobre: métodos System. TimeSpan'
title: System.TimeSpan (Métodos)
ms.date: 03/30/2017
ms.assetid: 9333fee8-1454-4374-855b-8c14c002f48f
ms.openlocfilehash: fa3192d18a59e589f2c7510776f8510b2c12cac4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681193"
---
# <a name="systemtimespan-methods"></a><span data-ttu-id="85449-103">System.TimeSpan (Métodos)</span><span class="sxs-lookup"><span data-stu-id="85449-103">System.TimeSpan Methods</span></span>

<span data-ttu-id="85449-104">La compatibilidad de miembros con <xref:System.TimeSpan?displayProperty=nameWithType> depende en gran medida de las versiones de .NET Framework y Microsoft SQL Server que use.</span><span class="sxs-lookup"><span data-stu-id="85449-104">Member support for <xref:System.TimeSpan?displayProperty=nameWithType> greatly depends on the versions of the .NET Framework and Microsoft SQL Server that you are using.</span></span>  
  
 <span data-ttu-id="85449-105">Si no se admite un método, operador o propiedad, significa que LINQ to SQL no puede traducir el miembro para la ejecución en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="85449-105">When a method, operator, or property is unsupported; it means that LINQ to SQL cannot translate the member for execution on the SQL Server.</span></span> <span data-ttu-id="85449-106">Todavía puede usar estos miembros en el código.</span><span class="sxs-lookup"><span data-stu-id="85449-106">You may still be able to use these members in your code.</span></span> <span data-ttu-id="85449-107">No obstante, deben evaluarse antes de traducir la consulta a Transact-SQL o después de recuperar los resultados de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="85449-107">However, they must be evaluated before the query is translated to Transact-SQL or after the results have been retrieved from the database.</span></span>  
  
## <a name="previous-limitations"></a><span data-ttu-id="85449-108">Limitaciones anteriores</span><span class="sxs-lookup"><span data-stu-id="85449-108">Previous Limitations</span></span>  

 <span data-ttu-id="85449-109">Al usar LINQ to SQL con versiones de .NET Framework anteriores a .NET Framework 3.5 Service Pack 1, no puede asignar campos de base de datos de SQL Server a <xref:System.TimeSpan?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="85449-109">When using LINQ to SQL with versions of the .NET Framework prior to .NET Framework 3.5 SP1, you cannot map SQL Server database fields to <xref:System.TimeSpan?displayProperty=nameWithType>.</span></span> <span data-ttu-id="85449-110">Sin embargo, se admiten las operaciones en <xref:System.TimeSpan> porque se pueden devolver valores <xref:System.TimeSpan> a partir de la sustracción de <xref:System.DateTime> o se pueden incluir en una expresión como una variable literal o una variable enlazada.</span><span class="sxs-lookup"><span data-stu-id="85449-110">However, operations on <xref:System.TimeSpan> are supported because <xref:System.TimeSpan> values can be returned from <xref:System.DateTime> subtraction or introduced into an expression as a literal or bound variable.</span></span>  
  
## <a name="supported-systemtimespan-member-support"></a><span data-ttu-id="85449-111">Compatibilidad con miembros System. TimeSpan admitidos</span><span class="sxs-lookup"><span data-stu-id="85449-111">Supported System.TimeSpan member support</span></span>

 <span data-ttu-id="85449-112">Los métodos, operadores y propiedades siguientes admitidos en LINQ to SQL, están disponibles para su uso en las consultas de LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="85449-112">The following LINQ to SQL-supported methods, operators, and properties are available for you to use in your LINQ to SQL queries.</span></span> <span data-ttu-id="85449-113">Una vez asignado en el modelo de objetos o en el archivo de asignación externo, LINQ to SQL permite llamar a muchos de los miembros de <xref:System.TimeSpan?displayProperty=nameWithType> dentro de las consultas de LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="85449-113">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call many of the <xref:System.TimeSpan?displayProperty=nameWithType> members inside your LINQ to SQL queries.</span></span>  
  
|<span data-ttu-id="85449-114">Métodos <xref:System.TimeSpan> compatibles</span><span class="sxs-lookup"><span data-stu-id="85449-114">Supported <xref:System.TimeSpan> Methods</span></span>|<span data-ttu-id="85449-115">Operadores <xref:System.TimeSpan> compatibles</span><span class="sxs-lookup"><span data-stu-id="85449-115">Supported <xref:System.TimeSpan> Operators</span></span>|<span data-ttu-id="85449-116">Propiedades <xref:System.TimeSpan> admitidas</span><span class="sxs-lookup"><span data-stu-id="85449-116">Supported <xref:System.TimeSpan> Properties</span></span>|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.TimeSpan.Compare%2A>|<xref:System.TimeSpan.op_Equality%2A>|<xref:System.TimeSpan.Days%2A>|  
|<xref:System.TimeSpan.CompareTo%28System.TimeSpan%29>|<xref:System.TimeSpan.op_GreaterThan%2A>|<xref:System.TimeSpan.Hours%2A>|  
|<xref:System.TimeSpan.Duration%2A>|<xref:System.TimeSpan.op_GreaterThanOrEqual%2A>|<xref:System.TimeSpan.MaxValue>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%2CSystem.TimeSpan%29>|<xref:System.TimeSpan.op_Inequality%2A>|<xref:System.TimeSpan.Milliseconds%2A>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%29>|<xref:System.TimeSpan.op_LessThan%2A>|<xref:System.TimeSpan.Minutes%2A>|  
||<xref:System.TimeSpan.op_LessThanOrEqual%2A>|<xref:System.TimeSpan.MinValue>|  
  
> [!NOTE]
> <span data-ttu-id="85449-117">La capacidad para asignar <xref:System.TimeSpan?displayProperty=nameWithType> a una columna `TIME` de SQL con LINQ to SQL requiere .NET Framework 3.5 Service Pack 1 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="85449-117">The ability to map <xref:System.TimeSpan?displayProperty=nameWithType> to a SQL `TIME` column with LINQ to SQL requires the .NET Framework 3.5 SP1 and beyond.</span></span> <span data-ttu-id="85449-118">El tipo de datos `TIME` de SQL está disponible solo en Microsoft SQL Server 2008 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="85449-118">The SQL `TIME` data type is only available in Microsoft SQL Server 2008 and beyond.</span></span>  
  
### <a name="addition-and-subtraction"></a><span data-ttu-id="85449-119">Suma y resta</span><span class="sxs-lookup"><span data-stu-id="85449-119">Addition and Subtraction</span></span>  

 <span data-ttu-id="85449-120">Aunque el tipo <xref:System.TimeSpan?displayProperty=nameWithType> de CLR admite la suma y resta, el tipo `TIME` de SQL no.</span><span class="sxs-lookup"><span data-stu-id="85449-120">Although the CLR <xref:System.TimeSpan?displayProperty=nameWithType> type does support addition and subtraction, the SQL `TIME` type does not.</span></span> <span data-ttu-id="85449-121">Debido a esto, las consultas de LINQ to SQL generarán errores si intentan realizar operaciones de suma o resta cuando se asignan al tipo `TIME` de SQL.</span><span class="sxs-lookup"><span data-stu-id="85449-121">Because of this, your LINQ to SQL queries will generate errors if they attempt addition and subtraction when they are mapped to the SQL `TIME` type.</span></span> <span data-ttu-id="85449-122">Puede encontrar otras consideraciones para trabajar con tipos de fecha y hora SQL en [la asignación de tipos SQL-CLR](sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="85449-122">You can find other considerations for working with SQL date and time types in [SQL-CLR Type Mapping](sql-clr-type-mapping.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85449-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="85449-123">See also</span></span>

- [<span data-ttu-id="85449-124">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="85449-124">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="85449-125">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="85449-125">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="85449-126">Asignación de tipos entre CLR y SQL</span><span class="sxs-lookup"><span data-stu-id="85449-126">SQL-CLR Type Mapping</span></span>](sql-clr-type-mapping.md)
- [<span data-ttu-id="85449-127">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="85449-127">Data Types and Functions</span></span>](data-types-and-functions.md)
