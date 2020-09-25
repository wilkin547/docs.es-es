---
title: System.DateTime (Métodos)
ms.date: 03/30/2017
ms.assetid: 4f80700c-e83f-4ab6-af0f-1c9a606e1133
ms.openlocfilehash: e3bffb1f47c19ccf7ea59151cd3545a15d59f1f2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203493"
---
# <a name="systemdatetime-methods"></a><span data-ttu-id="18421-102">System.DateTime (Métodos)</span><span class="sxs-lookup"><span data-stu-id="18421-102">System.DateTime Methods</span></span>

<span data-ttu-id="18421-103">Los métodos, operadores y propiedades siguientes admitidos en LINQ to SQL, están disponibles para su uso en las consultas de LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="18421-103">The following LINQ to SQL-supported methods, operators, and properties are available to use in LINQ to SQL queries.</span></span> <span data-ttu-id="18421-104">Si no se admite un método, operador ni propiedad, LINQ to SQL no puede convertir el miembro para la ejecución en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="18421-104">When a method, operator or property is unsupported, LINQ to SQL cannot translate the member for execution on the SQL Server.</span></span> <span data-ttu-id="18421-105">Puede usar estos miembros en el código, sin embargo, deben evaluarse antes de convertir la consulta a Transact-SQL o después de recuperar los resultados de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="18421-105">You may use these members in your code, however, they must be evaluated before the query is translated to Transact-SQL or after the results have been retrieved from the database.</span></span>  
  
## <a name="supported-systemdatetime-members"></a><span data-ttu-id="18421-106">Miembros System.DateTime admitidos</span><span class="sxs-lookup"><span data-stu-id="18421-106">Supported System.DateTime Members</span></span>  

 <span data-ttu-id="18421-107">Una vez asignado en el modelo de objetos o en el archivo de asignación externo, LINQ to SQL permite llamar a los siguientes miembros de <xref:System.DateTime?displayProperty=nameWithType> en las consultas de LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="18421-107">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call the following <xref:System.DateTime?displayProperty=nameWithType> members inside LINQ to SQL queries.</span></span>  
  
|<span data-ttu-id="18421-108">Métodos <xref:System.DateTime> compatibles</span><span class="sxs-lookup"><span data-stu-id="18421-108">Supported <xref:System.DateTime> Methods</span></span>|<span data-ttu-id="18421-109">Operadores <xref:System.DateTime> compatibles</span><span class="sxs-lookup"><span data-stu-id="18421-109">Supported <xref:System.DateTime> Operators</span></span>|<span data-ttu-id="18421-110">Propiedades <xref:System.DateTime> admitidas</span><span class="sxs-lookup"><span data-stu-id="18421-110">Supported <xref:System.DateTime> Properties</span></span>|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Add%2A>|<xref:System.DateTime.op_Addition%2A>|<xref:System.DateTime.Date%2A>|  
|<xref:System.DateTime.AddDays%2A>|<xref:System.DateTime.op_Equality%2A>|<xref:System.DateTime.Day%2A>|  
|<xref:System.DateTime.AddHours%2A>|<xref:System.DateTime.op_GreaterThan%2A>|<xref:System.DateTime.DayOfWeek%2A>|  
|<xref:System.DateTime.AddMilliseconds%2A>|<xref:System.DateTime.op_GreaterThanOrEqual%2A>|<xref:System.DateTime.DayOfYear%2A>|  
|<xref:System.DateTime.AddMinutes%2A>|<xref:System.DateTime.op_Inequality%2A>|<xref:System.DateTime.Hour%2A>|  
|<xref:System.DateTime.AddMonths%2A>|<xref:System.DateTime.op_LessThan%2A>|<xref:System.DateTime.Millisecond%2A>|  
|<xref:System.DateTime.AddSeconds%2A>|<xref:System.DateTime.op_LessThanOrEqual%2A>|<xref:System.DateTime.Minute%2A>|  
|<xref:System.DateTime.AddTicks%2A>|<xref:System.DateTime.op_Subtraction%2A>|<xref:System.DateTime.Month%2A>|  
|<xref:System.DateTime.AddYears%2A>||<xref:System.DateTime.Now%2A>|  
|<xref:System.DateTime.Compare%2A>||<xref:System.DateTime.Second%2A>|  
|<xref:System.DateTime.CompareTo%28System.DateTime%29>||<xref:System.DateTime.TimeOfDay%2A>|  
|<xref:System.DateTime.Equals%28System.DateTime%29>||<xref:System.DateTime.Today%2A>|  
|||<xref:System.DateTime.Year%2A>|  
  
## <a name="members-not-supported-by-linq-to-sql"></a><span data-ttu-id="18421-111">Miembros no admitidos por LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="18421-111">Members Not Supported by LINQ to SQL</span></span>  

 <span data-ttu-id="18421-112">Los siguientes miembros no se admiten en consultas de LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="18421-112">The following members are not supported inside LINQ to SQL queries.</span></span>  
  
|||  
|-|-|  
|<xref:System.DateTime.IsDaylightSavingTime%2A>|<xref:System.DateTime.IsLeapYear%2A>|  
|<xref:System.DateTime.DaysInMonth%2A>|<xref:System.DateTime.ToBinary%2A>|  
|<xref:System.DateTime.ToFileTime%2A>|<xref:System.DateTime.ToFileTimeUtc%2A>|  
|<xref:System.DateTime.ToLongDateString%2A>|<xref:System.DateTime.ToLongTimeString%2A>|  
|<xref:System.DateTime.ToOADate%2A>|<xref:System.DateTime.ToShortDateString%2A>|  
|<xref:System.DateTime.ToShortTimeString%2A>|<xref:System.DateTime.ToUniversalTime%2A>|  
|<xref:System.DateTime.FromBinary%2A>|<xref:System.DateTime.UtcNow%2A>|  
|<xref:System.DateTime.FromFileTime%2A>|<xref:System.DateTime.FromFileTimeUtc%2A>|  
|<xref:System.DateTime.FromOADate%2A>|<xref:System.DateTime.GetDateTimeFormats%2A>|  
  
## <a name="method-translation-example"></a><span data-ttu-id="18421-113">Ejemplo de conversión de método</span><span class="sxs-lookup"><span data-stu-id="18421-113">Method Translation Example</span></span>  

 <span data-ttu-id="18421-114">Todos los métodos admitidos por LINQ to SQL se convierten a Transact-SQL antes de enviarse a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="18421-114">All methods supported by LINQ to SQL are translated to Transact-SQL before they are sent to   SQL Server.</span></span> <span data-ttu-id="18421-115">Por ejemplo, considere el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="18421-115">For example, consider the following pattern.</span></span>  
  
 `(dateTime1 – dateTime2).{Days, Hours, Milliseconds, Minutes, Months, Seconds, Years}`  
  
 <span data-ttu-id="18421-116">Cuando se reconoce, se convierte en una llamada directa a la función `DATEDIFF` de SQL Server, de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="18421-116">When it is recognized, it is translated into a direct call to the SQL Server `DATEDIFF` function, as follows:</span></span>  
  
 `DATEDIFF({DatePart}, @dateTime1, @dateTime2)`  
  
## <a name="sqlmethods-date-and-time-methods"></a><span data-ttu-id="18421-117">Métodos Date y Time de SQLMethods</span><span class="sxs-lookup"><span data-stu-id="18421-117">SQLMethods Date and Time Methods</span></span>  

 <span data-ttu-id="18421-118">Además de los métodos proporcionados por la estructura <xref:System.DateTime>, LINQ to SQL proporciona los métodos citados en la siguiente tabla desde la clase <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> para trabajar con fechas y horas.</span><span class="sxs-lookup"><span data-stu-id="18421-118">In addition to the methods offered by the <xref:System.DateTime> structure, LINQ to SQL offers the methods listed in the following table from the <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> class for working with date and time.</span></span>  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="18421-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18421-119">See also</span></span>

- [<span data-ttu-id="18421-120">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="18421-120">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="18421-121">Crear el modelo de objetos</span><span class="sxs-lookup"><span data-stu-id="18421-121">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="18421-122">Asignación de tipos entre CLR y SQL</span><span class="sxs-lookup"><span data-stu-id="18421-122">SQL-CLR Type Mapping</span></span>](sql-clr-type-mapping.md)
- [<span data-ttu-id="18421-123">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="18421-123">Data Types and Functions</span></span>](data-types-and-functions.md)
