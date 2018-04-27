---
title: Desajustes de tipos entre SQL y CLR
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 0a90c33f-7ed7-4501-ad5f-6224c5da8e9b
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 6006bb8fd1f6b49382c89acc2b55efcb035ffbf5
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="sql-clr-type-mismatches"></a><span data-ttu-id="410cf-102">Desajustes de tipos entre SQL y CLR</span><span class="sxs-lookup"><span data-stu-id="410cf-102">SQL-CLR Type Mismatches</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="410cf-103"> automatiza gran parte de la conversión entre el modelo de objetos y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="410cf-103"> automates much of the translation between the object model and SQL Server.</span></span> <span data-ttu-id="410cf-104">No obstante, algunas situaciones impiden la exactitud de la conversión.</span><span class="sxs-lookup"><span data-stu-id="410cf-104">Nevertheless, some situations prevent exact translation.</span></span> <span data-ttu-id="410cf-105">Estas discordancias clave entre los tipos de Common Language Runtime (CLR) y los de base de datos de SQL Server se resumen en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="410cf-105">These key mismatches between the common language runtime (CLR) types and the SQL Server database types are summarized in the following sections.</span></span> <span data-ttu-id="410cf-106">Puede encontrar más detalles acerca de las asignaciones de tipo específico y la traducción de la función en [asignación de tipo de CLR de SQL](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md) y [tipos de datos y funciones](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md).</span><span class="sxs-lookup"><span data-stu-id="410cf-106">You can find more details about specific type mappings and function translation at [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md) and [Data Types and Functions](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="410cf-107">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="410cf-107">Data Types</span></span>  
 <span data-ttu-id="410cf-108">La conversión entre CLR y SQL Server se produce cuando se envía una consulta a la base de datos y cuando los resultados se devuelven al modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="410cf-108">Translation between the CLR and SQL Server occurs when a query is being sent to the database, and when the results are sent back to your object model.</span></span> <span data-ttu-id="410cf-109">Por ejemplo, la siguiente consulta de Transact-SQL requiere dos conversiones de valores:</span><span class="sxs-lookup"><span data-stu-id="410cf-109">For example, the following Transact-SQL query requires two value conversions:</span></span>  
  
```  
Select DateOfBirth From Customer Where CustomerId = @id     
```  
  
 <span data-ttu-id="410cf-110">Antes de que se pueda ejecutar la consulta en SQL Server, se debe especificar el valor del parámetro de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="410cf-110">Before the query can be executed on SQL Server, the value for the Transact-SQL parameter must be specified.</span></span> <span data-ttu-id="410cf-111">En este ejemplo, el valor del parámetro `id` primero se debe convertir de un tipo de elemento <xref:System.Int32?displayProperty=nameWithType> de CLR a un tipo de elemento `INT` de SQL Server para que la base de datos pueda entender el significado del valor.</span><span class="sxs-lookup"><span data-stu-id="410cf-111">In this example, the `id` parameter value must first be translated from a CLR <xref:System.Int32?displayProperty=nameWithType> type to a SQL Server `INT` type so that the database can understand what the value is.</span></span> <span data-ttu-id="410cf-112">Después, para recuperar los resultados, la columna `DateOfBirth` de SQL Server se debe convertir de un tipo de elemento `DATETIME` de SQL Server a un tipo de elemento <xref:System.DateTime?displayProperty=nameWithType> de CLR para su uso en el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="410cf-112">Then to retrieve the results, the SQL Server `DateOfBirth` column must be translated from a SQL Server `DATETIME` type to a CLR <xref:System.DateTime?displayProperty=nameWithType> type for use in the object model.</span></span> <span data-ttu-id="410cf-113">En este ejemplo, los tipos del modelo de objetos de CLR y la base de datos de SQL Server tienen asignaciones naturales.</span><span class="sxs-lookup"><span data-stu-id="410cf-113">In this example, the types in the CLR object model and SQL Server database have natural mappings.</span></span> <span data-ttu-id="410cf-114">Pero no siempre es así.</span><span class="sxs-lookup"><span data-stu-id="410cf-114">But, this is not always the case.</span></span>  
  
### <a name="missing-counterparts"></a><span data-ttu-id="410cf-115">Ausencia de tipos equivalentes</span><span class="sxs-lookup"><span data-stu-id="410cf-115">Missing Counterparts</span></span>  
 <span data-ttu-id="410cf-116">Los tipos siguientes no tienen equivalencias razonables.</span><span class="sxs-lookup"><span data-stu-id="410cf-116">The following types do not have reasonable counterparts.</span></span>  
  
-   <span data-ttu-id="410cf-117">Discordancias del espacio de nombres <xref:System> de CLR:</span><span class="sxs-lookup"><span data-stu-id="410cf-117">Mismatches in the CLR <xref:System> namespace:</span></span>  
  
    -   <span data-ttu-id="410cf-118">**Números enteros sin signo**.</span><span class="sxs-lookup"><span data-stu-id="410cf-118">**Unsigned integers**.</span></span> <span data-ttu-id="410cf-119">Estos tipos suelen asignarse a sus equivalentes con signo de mayor tamaño para evitar el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="410cf-119">These types are typically mapped to their signed counterparts of larger size to avoid overflow.</span></span> <span data-ttu-id="410cf-120">Los literales se pueden convertir a un tipo numérico con signo del mismo tamaño o de un tamaño inferior, según su valor.</span><span class="sxs-lookup"><span data-stu-id="410cf-120">Literals can be converted to a signed numeric of the same or smaller size, based on value.</span></span>  
  
    -   <span data-ttu-id="410cf-121">**Booleano**.</span><span class="sxs-lookup"><span data-stu-id="410cf-121">**Boolean**.</span></span> <span data-ttu-id="410cf-122">Estos tipos pueden asignarse a un valor numérico en bits o mayor, o a una cadena.</span><span class="sxs-lookup"><span data-stu-id="410cf-122">These types can be mapped to a bit or larger numeric or string.</span></span> <span data-ttu-id="410cf-123">Un literal se puede asignar a una expresión que se evalúe en el mismo valor (por ejemplo, `1=1` en SQL para `True` en CLS).</span><span class="sxs-lookup"><span data-stu-id="410cf-123">A literal can be mapped to an expression that evaluates to the same value (for example, `1=1` in SQL for `True` in CLS).</span></span>  
  
    -   <span data-ttu-id="410cf-124">**Intervalo de tiempo**.</span><span class="sxs-lookup"><span data-stu-id="410cf-124">**TimeSpan**.</span></span> <span data-ttu-id="410cf-125">Este tipo representa la diferencia entre dos valores `DateTime` y no se corresponde con `timestamp` en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="410cf-125">This type represents the difference between two `DateTime` values and does not correspond to the `timestamp` of SQL Server.</span></span> <span data-ttu-id="410cf-126">El elemento <xref:System.TimeSpan?displayProperty=nameWithType> de CLR también se puede asignar al tipo de elemento `TIME` de SQL Server en algunos casos.</span><span class="sxs-lookup"><span data-stu-id="410cf-126">The CLR <xref:System.TimeSpan?displayProperty=nameWithType> may also map to the SQL Server `TIME` type in some cases.</span></span> <span data-ttu-id="410cf-127">La única finalidad del tipo de elemento `TIME` de SQL Server era representar valores positivos menores que 24 horas.</span><span class="sxs-lookup"><span data-stu-id="410cf-127">The SQL Server `TIME` type was only intended to represent positive values less than 24 hours.</span></span> <span data-ttu-id="410cf-128">El ámbito del elemento <xref:System.TimeSpan> de CLR es mucho más amplio.</span><span class="sxs-lookup"><span data-stu-id="410cf-128">The CLR <xref:System.TimeSpan> has a much larger range.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="410cf-129">Específicas de SQL Server [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] tipos de <xref:System.Data.SqlTypes> no se incluyen en esta comparación.</span><span class="sxs-lookup"><span data-stu-id="410cf-129">SQL Server-specific [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] types in <xref:System.Data.SqlTypes> are not included in this comparison.</span></span>  
  
-   <span data-ttu-id="410cf-130">Discordancias de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="410cf-130">Mismatches in SQL Server:</span></span>  
  
    -   <span data-ttu-id="410cf-131">**Tipos de caracteres de longitud fija**.</span><span class="sxs-lookup"><span data-stu-id="410cf-131">**Fixed length character types**.</span></span> <span data-ttu-id="410cf-132">Transact-SQL distingue entre las categorías Unicode y no Unicode y tiene tres tipos distintos en cada categoría: una longitud fija `nchar` / `char`, longitud variable `nvarchar` / `varchar`, y mayor tamaño `ntext` / `text`.</span><span class="sxs-lookup"><span data-stu-id="410cf-132">Transact-SQL distinguishes between Unicode and non-Unicode categories and has three distinct types in each category: fixed length `nchar`/`char`, variable length `nvarchar`/`varchar`, and larger-sized `ntext`/`text`.</span></span> <span data-ttu-id="410cf-133">Los tipos de caracteres de longitud fija podrían asignarse al tipo de elemento <xref:System.Char?displayProperty=nameWithType> de CLR para recuperar los caracteres, pero realmente no se corresponden con el mismo tipo en conversiones y comportamiento.</span><span class="sxs-lookup"><span data-stu-id="410cf-133">The fixed length character types could be mapped to the CLR <xref:System.Char?displayProperty=nameWithType> type for retrieving characters, but they do not really correspond to the same type in conversions and behavior.</span></span>  
  
    -   <span data-ttu-id="410cf-134">**Bits**.</span><span class="sxs-lookup"><span data-stu-id="410cf-134">**Bit**.</span></span> <span data-ttu-id="410cf-135">Aunque el dominio `bit` tiene el mismo número de valores que `Nullable<Boolean>`, ambos son tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="410cf-135">Although the `bit` domain has the same number of values as `Nullable<Boolean>`, the two are different types.</span></span> <span data-ttu-id="410cf-136">`Bit` toma los valores `1` y `0` en lugar de `true` / `false`y no se puede usar como equivalente de expresiones booleanas.</span><span class="sxs-lookup"><span data-stu-id="410cf-136">`Bit` takes values `1` and `0` instead of `true`/`false`, and cannot be used as an equivalent to Boolean expressions.</span></span>  
  
    -   <span data-ttu-id="410cf-137">**Marca de tiempo**.</span><span class="sxs-lookup"><span data-stu-id="410cf-137">**Timestamp**.</span></span> <span data-ttu-id="410cf-138">A diferencia del tipo de elemento <xref:System.TimeSpan?displayProperty=nameWithType> de CLR, el tipo de elemento `TIMESTAMP` de SQL Server representa un número de 8 bits generado por la base de datos que es único para cada actualización y no se basa en la diferencia entre los valores de <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="410cf-138">Unlike the CLR <xref:System.TimeSpan?displayProperty=nameWithType> type, the SQL Server `TIMESTAMP` type represents an 8-byte number generated by the database that is unique for each update and is not based on the difference between <xref:System.DateTime> values.</span></span>  
  
    -   <span data-ttu-id="410cf-139">**Money** y **SmallMoney**.</span><span class="sxs-lookup"><span data-stu-id="410cf-139">**Money** and **SmallMoney**.</span></span> <span data-ttu-id="410cf-140">Estos tipos pueden asignarse a <xref:System.Decimal>, pero básicamente son tipos diferentes y son tratados como tales en las conversiones y por las funciones basadas en servidor.</span><span class="sxs-lookup"><span data-stu-id="410cf-140">These types can be mapped to <xref:System.Decimal> but are basically different types and are treated as such by server-based functions and conversions.</span></span>  
  
### <a name="multiple-mappings"></a><span data-ttu-id="410cf-141">Asignaciones múltiples</span><span class="sxs-lookup"><span data-stu-id="410cf-141">Multiple Mappings</span></span>  
 <span data-ttu-id="410cf-142">Existen muchos tipos de datos de SQL Server que se pueden asignar a uno o más tipos de datos de CLR.</span><span class="sxs-lookup"><span data-stu-id="410cf-142">There are many SQL Server data types that you can map to one or more CLR data types.</span></span> <span data-ttu-id="410cf-143">Asimismo, existen muchos tipos de datos de CLR que se pueden asignar a uno o más tipos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="410cf-143">There are also many CLR types that you can map to one or more SQL Server types.</span></span> <span data-ttu-id="410cf-144">Aunque LINQ to SQL pueda admitir una asignación, no significa que dos tipos asignados entre CLR y SQL Server tengan una coincidencia perfecta en precisión, ámbito y semántica.</span><span class="sxs-lookup"><span data-stu-id="410cf-144">Although a mapping may be supported by LINQ to SQL, it does not mean that the two types mapped between the CLR and SQL Server are a perfect match in precision, range, and semantics.</span></span> <span data-ttu-id="410cf-145">Algunas asignaciones pueden incluir diferencias en alguna o todas estas dimensiones.</span><span class="sxs-lookup"><span data-stu-id="410cf-145">Some mappings may include differences in any or all of these dimensions.</span></span> <span data-ttu-id="410cf-146">Puede encontrar más información sobre estas diferencias posibles para las diversas posibilidades de asignación en [asignación de tipos de CLR de SQL](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="410cf-146">You can find details about these potential differences for the various mapping possibilities at [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
### <a name="user-defined-types"></a><span data-ttu-id="410cf-147">Tipos definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="410cf-147">User-defined Types</span></span>  
 <span data-ttu-id="410cf-148">Los tipos de CLR definidos por el usuario están diseñados para eliminar las lagunas del sistema de tipos.</span><span class="sxs-lookup"><span data-stu-id="410cf-148">User-defined CLR types are designed to help bridge the type system gap.</span></span> <span data-ttu-id="410cf-149">No obstante, revelan problemas interesantes con el control de versiones de los tipos.</span><span class="sxs-lookup"><span data-stu-id="410cf-149">Nevertheless they surface interesting issues about type versioning.</span></span> <span data-ttu-id="410cf-150">Un cambio de versión en el cliente podría no corresponderse con un cambio en el tipo almacenado en el servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="410cf-150">A change in the version on the client might not be matched by a change in the type stored on the database server.</span></span> <span data-ttu-id="410cf-151">Esto generaría otra discordancia de tipos según la cual no coincidiría la semántica de tipos y es probable que saltase a la vista la diferencia entre las versiones.</span><span class="sxs-lookup"><span data-stu-id="410cf-151">Any such change causes another type mismatch where the type semantics might not match and the version gap is likely to become visible.</span></span> <span data-ttu-id="410cf-152">Esto se complica todavía más cuando las jerarquías de herencia se refactorizan en sucesivas versiones.</span><span class="sxs-lookup"><span data-stu-id="410cf-152">Further complications occur as inheritance hierarchies are refactored in successive versions.</span></span>  
  
## <a name="expression-semantics"></a><span data-ttu-id="410cf-153">Semántica de expresión</span><span class="sxs-lookup"><span data-stu-id="410cf-153">Expression Semantics</span></span>  
 <span data-ttu-id="410cf-154">Además de la discordancia en pares entre los tipos de CLR y los tipos de base de datos, las expresiones agregan complejidad.</span><span class="sxs-lookup"><span data-stu-id="410cf-154">In addition to the pairwise mismatch between CLR and database types, expressions add complexity to the mismatch.</span></span> <span data-ttu-id="410cf-155">Deben considerarse las discordancias en la semántica de operador, semántica de función, conversión de tipos implícita y reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="410cf-155">Mismatches in operator semantics, function semantics, implicit type conversion, and precedence rules must be considered.</span></span>  
  
 <span data-ttu-id="410cf-156">Las subsecciones siguientes muestran la discordancia entre expresiones aparentemente similares.</span><span class="sxs-lookup"><span data-stu-id="410cf-156">The following subsections illustrate the mismatch between apparently similar expressions.</span></span> <span data-ttu-id="410cf-157">Quizás se puedan generar expresiones SQL semánticamente equivalentes a una expresión CLR dada.</span><span class="sxs-lookup"><span data-stu-id="410cf-157">It might be possible to generate SQL expressions that are semantically equivalent to a given CLR expression.</span></span> <span data-ttu-id="410cf-158">Sin embargo, no está claro si las diferencias semánticas entre expresiones aparentemente similares son evidentes para un usuario de CLR y, por tanto, si se han previsto o no los cambios necesarios para la equivalencia semántica.</span><span class="sxs-lookup"><span data-stu-id="410cf-158">However, it is not clear whether the semantic differences between apparently similar expressions are evident to a CLR user, and therefore whether the changes that are required for semantic equivalence are intended or not.</span></span> <span data-ttu-id="410cf-159">Éste es un problema especialmente crítico cuando una expresión se evalúa para un conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="410cf-159">This is an especially critical issue when an expression is evaluated for a set of values.</span></span> <span data-ttu-id="410cf-160">La visibilidad de la diferencia podría depender de los datos y ser difícil de identificar durante la codificación y depuración.</span><span class="sxs-lookup"><span data-stu-id="410cf-160">The visibility of the difference might depend on data- and be hard to identify during coding and debugging.</span></span>  
  
### <a name="null-semantics"></a><span data-ttu-id="410cf-161">Semántica de null</span><span class="sxs-lookup"><span data-stu-id="410cf-161">Null Semantics</span></span>  
 <span data-ttu-id="410cf-162">Las expresiones SQL proporcionan lógica de tres valores para las expresiones booleanas.</span><span class="sxs-lookup"><span data-stu-id="410cf-162">SQL expressions provide three-valued logic for Boolean expressions.</span></span> <span data-ttu-id="410cf-163">El resultado puede ser True, False o Null.</span><span class="sxs-lookup"><span data-stu-id="410cf-163">The result can be true, false, or null.</span></span> <span data-ttu-id="410cf-164">En cambio, CLR especifica un resultado booleano de dos valores para las comparaciones que implican valores de tipo NULL.</span><span class="sxs-lookup"><span data-stu-id="410cf-164">By contrast, CLR specifies two-valued Boolean result for comparisons involving null values.</span></span> <span data-ttu-id="410cf-165">Observe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="410cf-165">Consider the following code:</span></span>  
  
 [!code-csharp[DLinqMismatch#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#2)]
 [!code-vb[DLinqMismatch#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#2)]  
  
```  
-- Assume col1 and col2 are integer columns with null values.   
-- Assume that ANSI null behavior has not been explicitly  
--    turned off.  
Select …  
From …  
Where col1 = col2  
-- Evaluates to null, not true and the corresponding row is not  
--     selected.  
-- To obtain matching behavior (i -> col1, j -> col2) change  
--     the query to the following:  
Select …  
From …  
Where  
    col1 = col2   
or (col1 is null and col2 is null)  
-- (Visual Basic 'Nothing'.)  
```  
  
 <span data-ttu-id="410cf-166">Un problema similar se da cuando se asumen resultados de dos valores.</span><span class="sxs-lookup"><span data-stu-id="410cf-166">A similar problem occurs with the assumption about two-valued results.</span></span>  
  
 [!code-csharp[DLinqMismatch#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#3)]
 [!code-vb[DLinqMismatch#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#3)]  
  
```  
-- Assume col1 and col2 are nullable columns.  
-- Assume that ANSI null behavior has not been explicitly  
--     turned off.  
Select …  
From …  
Where  
    col1 = col2        
or col1 != col2  
-- Visual Basic: col1 <> col2.  
  
-- Excludes the case where the boolean expression evaluates  
--     to null. Therefore the where clause does not always  
--     evaluate to true.  
```  
  
 <span data-ttu-id="410cf-167">En el caso anterior, puede obtener un comportamiento equivalente para generar SQL, pero la conversión podría no reflejar su intención de manera precisa.</span><span class="sxs-lookup"><span data-stu-id="410cf-167">In the previous case, you can get equivalent behavior in generating SQL, but the translation might not accurately reflect your intention.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="410cf-168"> no impone C# `null` o Visual Basic `nothing` una semántica de comparación en SQL.</span><span class="sxs-lookup"><span data-stu-id="410cf-168"> does not impose C# `null` or Visual Basic `nothing` comparison semantics on SQL.</span></span> <span data-ttu-id="410cf-169">Los operadores de comparación se convierten sintácticamente en sus equivalentes SQL.</span><span class="sxs-lookup"><span data-stu-id="410cf-169">Comparison operators are syntactically translated to their SQL equivalents.</span></span> <span data-ttu-id="410cf-170">La semántica refleja la semántica de SQL tal como la define la configuración del servidor o de la conexión.</span><span class="sxs-lookup"><span data-stu-id="410cf-170">The semantics reflect SQL semantics as defined by server or connection settings.</span></span> <span data-ttu-id="410cf-171">Dos valores nulos se consideran distintos según la configuración predeterminada de SQL Server (aunque se puede cambiar la configuración para cambiar la semántica).</span><span class="sxs-lookup"><span data-stu-id="410cf-171">Two null values are considered unequal under default SQL Server settings (although you can change the settings to change the semantics).</span></span> <span data-ttu-id="410cf-172">Sea como fuere, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no considera la configuración del servidor en la conversión de consultas.</span><span class="sxs-lookup"><span data-stu-id="410cf-172">Regardless, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not consider server settings in query translation.</span></span>  
  
 <span data-ttu-id="410cf-173">Una comparación con el literal `null` (`nothing`) se convierte a la versión de SQL correcta (`is null` o `is not null`).</span><span class="sxs-lookup"><span data-stu-id="410cf-173">A comparison with the literal `null` (`nothing`) is translated to the appropriate SQL version (`is null` or `is not null`).</span></span>  
  
 <span data-ttu-id="410cf-174">SQL Server define el valor `null` (`nothing`) en la intercalación; [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no cambia la intercalación.</span><span class="sxs-lookup"><span data-stu-id="410cf-174">The value of `null` (`nothing`) in collation is defined by SQL Server; [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not change the collation.</span></span>  
  
### <a name="type-conversion-and-promotion"></a><span data-ttu-id="410cf-175">Conversión y promoción de tipos</span><span class="sxs-lookup"><span data-stu-id="410cf-175">Type Conversion and Promotion</span></span>  
 <span data-ttu-id="410cf-176">SQL admite un completo conjunto de conversiones implícitas en las expresiones.</span><span class="sxs-lookup"><span data-stu-id="410cf-176">SQL supports a rich set of implicit conversions in expressions.</span></span> <span data-ttu-id="410cf-177">Las mismas expresiones en C# requerirían una conversión de tipos explícita.</span><span class="sxs-lookup"><span data-stu-id="410cf-177">Similar expressions in C# would require an explicit cast.</span></span> <span data-ttu-id="410cf-178">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="410cf-178">For example:</span></span>  
  
-   <span data-ttu-id="410cf-179">Los tipos `Nvarchar` y `DateTime` se pueden comparar en SQL sin ninguna conversión de tipos explícita; C# requiere la conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="410cf-179">`Nvarchar` and `DateTime` types can be compared in SQL without any explicit casts; C# requires explicit conversion.</span></span>  
  
-   <span data-ttu-id="410cf-180">`Decimal` se convierte implícitamente a `DateTime` en SQL.</span><span class="sxs-lookup"><span data-stu-id="410cf-180">`Decimal` is implicitly converted to `DateTime` in SQL.</span></span> <span data-ttu-id="410cf-181">C# no permite una conversión implícita.</span><span class="sxs-lookup"><span data-stu-id="410cf-181">C# does not allow for an implicit conversion.</span></span>  
  
 <span data-ttu-id="410cf-182">De igual forma, la prioridad de los tipos en Transact-SQL difiere de la prioridad de los tipos en C#, ya que el conjunto de tipos subyacente es diferente.</span><span class="sxs-lookup"><span data-stu-id="410cf-182">Likewise, type precedence in Transact-SQL differs from type precedence in C# because the underlying set of types is different.</span></span> <span data-ttu-id="410cf-183">De hecho, no hay una relación clara de subconjuntos/supraconjuntos entre las listas de prioridades.</span><span class="sxs-lookup"><span data-stu-id="410cf-183">In fact, there is no clear subset/superset relationship between the precedence lists.</span></span> <span data-ttu-id="410cf-184">Por ejemplo, al comparar `nvarchar` con `varchar`, se produce la conversión implícita de la expresión `varchar` a `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="410cf-184">For example, comparing an `nvarchar` with a `varchar` causes the implicit conversion of the `varchar` expression to `nvarchar`.</span></span> <span data-ttu-id="410cf-185">CLR no proporciona ninguna promoción equivalente.</span><span class="sxs-lookup"><span data-stu-id="410cf-185">The CLR provides no equivalent promotion.</span></span>  
  
 <span data-ttu-id="410cf-186">En casos más sencillos, estas diferencias generan expresiones CLR con conversiones de tipos que van a ser redundantes para la expresión SQL correspondiente.</span><span class="sxs-lookup"><span data-stu-id="410cf-186">In simple cases, these differences cause CLR expressions with casts to be redundant for a corresponding SQL expression.</span></span> <span data-ttu-id="410cf-187">Lo que es más importante, los resultados intermedios de una expresión SQL podrían promoverse implícitamente a un tipo que no tiene ningún homólogo preciso en C#, y lo mismo a la inversa.</span><span class="sxs-lookup"><span data-stu-id="410cf-187">More importantly, the intermediate results of a SQL expression might be implicitly promoted to a type that has no accurate counterpart in C#, and vice versa.</span></span> <span data-ttu-id="410cf-188">En general, las pruebas, la depuración y la validación de tales expresiones representan una carga adicional importante para el usuario.</span><span class="sxs-lookup"><span data-stu-id="410cf-188">Overall, the testing, debugging, and validation of such expressions adds significant burden on the user.</span></span>  
  
### <a name="collation"></a><span data-ttu-id="410cf-189">Collation</span><span class="sxs-lookup"><span data-stu-id="410cf-189">Collation</span></span>  
 <span data-ttu-id="410cf-190">Transact-SQL admite las intercalaciones explícitas como anotaciones en tipos de cadena de caracteres.</span><span class="sxs-lookup"><span data-stu-id="410cf-190">Transact-SQL supports explicit collations as annotations to character string types.</span></span> <span data-ttu-id="410cf-191">Estas intercalaciones determinan la validez de ciertas comparaciones.</span><span class="sxs-lookup"><span data-stu-id="410cf-191">These collations determine the validity of certain comparisons.</span></span> <span data-ttu-id="410cf-192">Por ejemplo, al comparar dos columnas con intercalaciones explícitas diferentes, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="410cf-192">For example, comparing two columns with different explicit collations is an error.</span></span> <span data-ttu-id="410cf-193">Si se utiliza el tipo de cadena CTS, más simplificado, no se producen tales errores.</span><span class="sxs-lookup"><span data-stu-id="410cf-193">The use of much simplified CTS string type does not cause such errors.</span></span> <span data-ttu-id="410cf-194">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="410cf-194">Consider the following example:</span></span>  
  
```  
create table T2 (  
    Col1 nvarchar(10),  
    Col2      nvarchar(10) collate Latin_general_ci_as  
)  
```  
  
 [!code-csharp[DLinqMismatch#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#4)]
 [!code-vb[DLinqMismatch#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#4)]  
  
```  
Select …  
From …  
Where Col1 = Col2  
-- Error, collation conflict.  
```  
  
 <span data-ttu-id="410cf-195">De hecho, la subcláusula de intercalación crea un *restringido tipo* que no es sustituible.</span><span class="sxs-lookup"><span data-stu-id="410cf-195">In effect, the collation subclause creates a *restricted type* that is not substitutable.</span></span>  
  
 <span data-ttu-id="410cf-196">De forma similar, el criterio de ordenación puede ser bastante diferente entre los sistemas de tipos.</span><span class="sxs-lookup"><span data-stu-id="410cf-196">Similarly, the sort order can be significantly different across the type systems.</span></span> <span data-ttu-id="410cf-197">Esta diferencia afecta a la ordenación de los resultados.</span><span class="sxs-lookup"><span data-stu-id="410cf-197">This difference affects the sorting of results.</span></span> <span data-ttu-id="410cf-198"><xref:System.Guid> se ordena en los 16 bytes por orden lexicográfico (`IComparable()`), mientras que T-SQL compara los GUID en el orden siguiente: node(10-15), clock-seq(8-9), time-high(6-7), time-mid(4-5), time-low(0-3).</span><span class="sxs-lookup"><span data-stu-id="410cf-198"><xref:System.Guid> is sorted on all 16 bytes by lexicographic order (`IComparable()`), whereas T-SQL compares GUIDs in the following order: node(10-15), clock-seq(8-9), time-high(6-7), time-mid(4-5), time-low(0-3).</span></span> <span data-ttu-id="410cf-199">Esta ordenación era la habitual en SQL 7.0, cuando los GUID generados por NT tenían este orden de octetos.</span><span class="sxs-lookup"><span data-stu-id="410cf-199">This ordering was done in SQL 7.0 when NT-generated GUIDs had such an octet order.</span></span> <span data-ttu-id="410cf-200">Este enfoque garantizaba que los GUID generados en el mismo clúster de nodos se obtenían juntos y ordenados secuencialmente, según la marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="410cf-200">The approach ensured that GUIDs generated at the same node cluster came together in sequential order according to timestamp.</span></span> <span data-ttu-id="410cf-201">También era útil para compilar índices (las inserciones se convertían en anexos en lugar de E/S aleatorias).</span><span class="sxs-lookup"><span data-stu-id="410cf-201">The approach was also useful for building indexes (inserts become appends instead of random IOs).</span></span> <span data-ttu-id="410cf-202">Posteriormente, el orden se codificó en Windows por cuestiones de privacidad, pero SQL debe mantener la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="410cf-202">The order was scrambled later in Windows because of privacy concerns, but SQL must maintain compatibility.</span></span> <span data-ttu-id="410cf-203">Una solución alternativa es usar <xref:System.Data.SqlTypes.SqlGuid> en lugar de <xref:System.Guid>.</span><span class="sxs-lookup"><span data-stu-id="410cf-203">A workaround is to use <xref:System.Data.SqlTypes.SqlGuid> instead of <xref:System.Guid>.</span></span>  
  
### <a name="operator-and-function-differences"></a><span data-ttu-id="410cf-204">Diferencias entre operadores y funciones</span><span class="sxs-lookup"><span data-stu-id="410cf-204">Operator and Function Differences</span></span>  
 <span data-ttu-id="410cf-205">Los operadores y las funciones que son esencialmente comparables presentan una semántica ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="410cf-205">Operators and functions that are essentially comparable have subtly different semantics.</span></span> <span data-ttu-id="410cf-206">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="410cf-206">For example:</span></span>  
  
-   <span data-ttu-id="410cf-207">C# especifica una semántica de cortocircuito basada en el orden léxico de los operandos para los operadores lógicos `&&` y `||`.</span><span class="sxs-lookup"><span data-stu-id="410cf-207">C# specifies short circuit semantics based on lexical order of operands for logical operators `&&` and `||`.</span></span> <span data-ttu-id="410cf-208">Por otro lado, SQL está orientado a consultas basadas en conjuntos y, por consiguiente, proporciona más libertad al optimizador para que decida el orden de ejecución.</span><span class="sxs-lookup"><span data-stu-id="410cf-208">SQL on the other hand is targeted for set-based queries and therefore provides more freedom for the optimizer to decide the order of execution.</span></span> <span data-ttu-id="410cf-209">Algunas de las implicaciones se exponen a continuación:</span><span class="sxs-lookup"><span data-stu-id="410cf-209">Some of the implications include the following:</span></span>  
  
    -   <span data-ttu-id="410cf-210">Conversión semánticamente equivalente requeriría "`CASE` ...</span><span class="sxs-lookup"><span data-stu-id="410cf-210">Semantically equivalent translation would require "`CASE` …</span></span> <span data-ttu-id="410cf-211">`WHEN` …</span><span class="sxs-lookup"><span data-stu-id="410cf-211">`WHEN` …</span></span> <span data-ttu-id="410cf-212">`THEN`"construir en SQL para evitar la reordenación de ejecución de los operandos.</span><span class="sxs-lookup"><span data-stu-id="410cf-212">`THEN`" construct in SQL to avoid reordering of operand execution.</span></span>  
  
    -   <span data-ttu-id="410cf-213">Una conversión libre a `AND` / `OR` podría producir errores inesperados si la expresión de C# basa en la evaluación del segundo operando se basa en el resultado de la evaluación del primer operando.</span><span class="sxs-lookup"><span data-stu-id="410cf-213">A loose translation to `AND`/`OR` operators could cause unexpected errors if the C# expression relies on evaluation the second operand being based on the result of the evaluation of the first operand.</span></span>  
  
-   <span data-ttu-id="410cf-214">La función `Round()` tiene una semántica diferente en [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] y en T-SQL.</span><span class="sxs-lookup"><span data-stu-id="410cf-214">`Round()` function has different semantics in [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] and in T-SQL.</span></span>  
  
-   <span data-ttu-id="410cf-215">El índice de inicio de las cadenas es 0 en CLR, pero 1 en SQL.</span><span class="sxs-lookup"><span data-stu-id="410cf-215">Starting index for strings is 0 in the CLR but 1 in SQL.</span></span> <span data-ttu-id="410cf-216">Por consiguiente, cualquier función que tenga un índice requiere la conversión del índice.</span><span class="sxs-lookup"><span data-stu-id="410cf-216">Therefore, any function that has index needs index translation.</span></span>  
  
-   <span data-ttu-id="410cf-217">CLR admite el operador de módulo (‘%’) para los números de punto flotante, pero SQL no.</span><span class="sxs-lookup"><span data-stu-id="410cf-217">The CLR supports modulus (‘%’) operator for floating point numbers but SQL does not.</span></span>  
  
-   <span data-ttu-id="410cf-218">El operador `Like` admite eficazmente las sobrecargas automáticas basadas en las conversiones implícitas.</span><span class="sxs-lookup"><span data-stu-id="410cf-218">The `Like` operator effectively acquires automatic overloads based on implicit conversions.</span></span> <span data-ttu-id="410cf-219">Aunque el operador `Like` por definición funciona en tipos de cadena de caracteres, la conversión implícita de tipos numéricos o tipos `DateTime` permite utilizar igualmente tipos que no son de cadena con `Like`.</span><span class="sxs-lookup"><span data-stu-id="410cf-219">Although the `Like` operator is defined to operate on character string types, implicit conversion from numeric types or `DateTime` types allows for those non-string types to be used with `Like` just as well.</span></span> <span data-ttu-id="410cf-220">En CTS, no existe una conversión implícita comparable.</span><span class="sxs-lookup"><span data-stu-id="410cf-220">In CTS, comparable implicit conversions do not exist.</span></span> <span data-ttu-id="410cf-221">Por lo tanto, se requieren sobrecargas adicionales.</span><span class="sxs-lookup"><span data-stu-id="410cf-221">Therefore, additional overloads are needed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="410cf-222">Este comportamiento del operador `Like` solo se aplica en C#; la palabra clave de Visual Basic `Like` se mantiene invariable.</span><span class="sxs-lookup"><span data-stu-id="410cf-222">This `Like` operator behavior applies to C# only; the Visual Basic `Like` keyword is unchanged.</span></span>  
  
-   <span data-ttu-id="410cf-223">Siempre se comprueba el desbordamiento en SQL, pero tiene que especificarse explícitamente en C# (no en Visual Basic) para evitar el salto.</span><span class="sxs-lookup"><span data-stu-id="410cf-223">Overflow is always checked in SQL but it has to be explicitly specified in C# (not in Visual Basic) to avoid wraparound.</span></span> <span data-ttu-id="410cf-224">Dadas las columnas de enteros C1, C2 y C3, si C1+C2 se almacena en C3 (Update T Set C3 = C1 + C2):</span><span class="sxs-lookup"><span data-stu-id="410cf-224">Given integer columns C1, C2 and C3, if C1+C2 is stored in C3 (Update T Set C3 = C1 + C2).</span></span>  
  
    ```  
    create table T3 (  
        Col1      integer,  
        Col2      integer  
    )  
    insert into T3 (col1, col2) values (2147483647, 5)  
    -- Valid values: max integer value and 5.  
    select * from T3 where col1 + col2 < 0  
    -- Produces arithmetic overflow error.  
    ```  
  
 [!code-csharp[DLinqMismatch#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#5)]
 [!code-vb[DLinqMismatch#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#5)]  
  
-   <span data-ttu-id="410cf-225">SQL realiza un redondeo aritmético simétrico mientras que [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] utiliza el redondeo bancario.</span><span class="sxs-lookup"><span data-stu-id="410cf-225">SQL performs symmetric arithmetic rounding while [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] uses banker’s rounding.</span></span> <span data-ttu-id="410cf-226">Para obtener información detallada, vea el artículo 196652 de Microsoft Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="410cf-226">See Knowledgebase article 196652 for additional details.</span></span>  
  
-   <span data-ttu-id="410cf-227">De forma predeterminada, para las configuraciones regionales comunes, en las comparaciones de cadenas de caracteres no se hace distinción entre mayúsculas y minúsculas en SQL.</span><span class="sxs-lookup"><span data-stu-id="410cf-227">By default, for common locales, character-string comparisons are case-insensitive in SQL.</span></span> <span data-ttu-id="410cf-228">En Visual Basic y en C#, se distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="410cf-228">In Visual Basic and in C#, they are case-sensitive.</span></span> <span data-ttu-id="410cf-229">Por ejemplo, `s == "Food"` (`s = "Food"` en Visual Basic) y `s == "Food"` pueden producir resultados diferentes si `s` es `food`.</span><span class="sxs-lookup"><span data-stu-id="410cf-229">For example, `s == "Food"` (`s = "Food"` in Visual Basic) and `s == "Food"` can yield different results if `s` is `food`.</span></span>  
  
    ```  
    -- Assume default US-English locale (case insensitive).  
    create table T4 (  
        Col1      nvarchar (256)  
    )  
    insert into T4 values (‘Food’)   
    insert into T4 values (‘FOOD’)  
    select * from T4 where Col1 = ‘food’  
    -- Both the rows are returned because of case-insensitive matching.  
    ```  
  
 [!code-csharp[DLinqMismatch#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#6)]
 [!code-vb[DLinqMismatch#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#6)]  
  
-   <span data-ttu-id="410cf-230">Los operadores o las funciones aplicados a argumentos de tipo de caracteres de longitud fija en SQL tienen una semántica significativamente diferente a la de las mismas funciones y operadores aplicados a <xref:System.String?displayProperty=nameWithType> de CLR.</span><span class="sxs-lookup"><span data-stu-id="410cf-230">Operators/ functions applied to fixed length character type arguments in SQL have significantly different semantics than the same operators/functions applied to the CLR <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="410cf-231">Esto también podría interpretarse como una implicación más del problema de la ausencia de tipos equivalentes que se describió en la sección relativa a los tipos.</span><span class="sxs-lookup"><span data-stu-id="410cf-231">This could also be viewed as an extension of the missing counterpart problem discussed in the section about types.</span></span>  
  
    ```  
    create table T4 (  
        Col1      nchar(4)  
    )  
    Insert into T5(Col1) values ('21');  
    Insert into T5(Col1) values ('1021');  
    Select * from T5 where Col1 like '%1'  
    -- Only the second row with Col1 = '1021' is returned.  
    -- Not the first row!  
    ```  
  
     [!code-csharp[DLinqMismatch#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#7)]
     [!code-vb[DLinqMismatch#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#7)]  
  
     <span data-ttu-id="410cf-232">Un problema similar se produce con la concatenación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="410cf-232">A similar problem occurs with string concatenation.</span></span>  
  
    ```  
    create table T6 (  
        Col1      nchar(4)  
        Col2       nchar(4)  
    )  
    Insert into T6 values ('a', 'b');  
    Select Col1+Col2 from T6  
    -- Returns concatenation of padded strings "a   b   " and not "ab".  
    ```  
  
 <span data-ttu-id="410cf-233">En resumen, podría requerirse una conversión compleja para las expresiones CLR, así como operadores o funciones adicionales para exponer la funcionalidad de SQL.</span><span class="sxs-lookup"><span data-stu-id="410cf-233">In summary, a convoluted translation might be required for CLR expressions and additional operators/functions may be necessary to expose SQL functionality.</span></span>  
  
### <a name="type-casting"></a><span data-ttu-id="410cf-234">Conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="410cf-234">Type Casting</span></span>  
 <span data-ttu-id="410cf-235">En C# y en SQL, los usuarios pueden invalidar la semántica predeterminada de las expresiones utilizando conversiones de tipos explícitas (`Cast` y `Convert`).</span><span class="sxs-lookup"><span data-stu-id="410cf-235">In C# and in SQL, users can override the default semantics of expressions by using explicit type casts (`Cast` and `Convert`).</span></span> <span data-ttu-id="410cf-236">Sin embargo, exponer esta funcionalidad entre los límites del sistema de tipos puede plantear un dilema.</span><span class="sxs-lookup"><span data-stu-id="410cf-236">However, exposing this capability across the type system boundary poses a dilemma.</span></span> <span data-ttu-id="410cf-237">Una conversión de tipos de SQL que proporciona la semántica deseada no se puede convertir con facilidad a la conversión de tipos de C# correspondiente.</span><span class="sxs-lookup"><span data-stu-id="410cf-237">A SQL cast that provides the desired semantics cannot be easily translated to a corresponding C# cast.</span></span> <span data-ttu-id="410cf-238">Por otro lado, una conversión de tipos de C# no se puede convertir directamente en una conversión de tipos de SQL equivalente debido a las discordancias de los tipos, la ausencia de tipos equivalentes y las diferencias en las jerarquías de prioridades de tipos.</span><span class="sxs-lookup"><span data-stu-id="410cf-238">On the other hand, a C# cast cannot be directly translated into an equivalent SQL cast because of type mismatches, missing counterparts, and different type precedence hierarchies.</span></span> <span data-ttu-id="410cf-239">Es necesario elegir entre exponer la discordancia con el sistema de tipos y perder una importante capacidad de expresión.</span><span class="sxs-lookup"><span data-stu-id="410cf-239">There is a trade-off between exposing the type system mismatch and losing significant power of expression.</span></span>  
  
 <span data-ttu-id="410cf-240">En otros casos, puede que la conversión de tipos no sea necesaria para validar una expresión en cualquiera de los dos dominios, pero podría serlo para garantizar que una asignación no predeterminada se aplica correctamente a la expresión.</span><span class="sxs-lookup"><span data-stu-id="410cf-240">In other cases, type casting might not be needed in either domain for validation of an expression but might be required to make sure that a non-default mapping is correctly applied to the expression.</span></span>  
  
```  
-- Example from "Non-default Mapping" section extended  
create table T5 (  
    Col1      nvarchar(10),  
    Col2      nvarchar(10)  
)  
Insert into T5(col1, col2) values (‘3’, ‘2’);  
```  
  
 [!code-csharp[DLinqMismatch#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#8)]
 [!code-vb[DLinqMismatch#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#8)]  
  
```  
Select *  
From T5  
Where Col1 + Col2 > 4     
-- "Col1 + Col2" expr evaluates to '32'   
```  
  
## <a name="performance-issues"></a><span data-ttu-id="410cf-241">Problemas de rendimiento</span><span class="sxs-lookup"><span data-stu-id="410cf-241">Performance Issues</span></span>  
 <span data-ttu-id="410cf-242">Si se tienen en cuenta algunas de las diferencias de los tipos de SQL Server-CLR, el resultado puede ser una reducción del rendimiento si se entrecruzan los sistemas de tipos de CLR y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="410cf-242">Accounting for some SQL Server-CLR type differences may resut in a decrease in performance when crossing between the CLR and SQL Server type systems.</span></span> <span data-ttu-id="410cf-243">A continuación se muestran ejemplos de escenarios cuyo rendimiento se ve muy afectado:</span><span class="sxs-lookup"><span data-stu-id="410cf-243">Examples of scenarios impacting performance include the following:</span></span>  
  
-   <span data-ttu-id="410cf-244">Orden forzado de evaluación de los operadores lógicos AND/OR</span><span class="sxs-lookup"><span data-stu-id="410cf-244">Forced order of evaluation for logical and/or operators</span></span>  
  
-   <span data-ttu-id="410cf-245">La generación de SQL para aplicar el orden de evaluación del predicado limita la funcionalidad del optimizador de SQL.</span><span class="sxs-lookup"><span data-stu-id="410cf-245">Generating SQL to enforce order of predicate evaluation restricts the SQL optimizer’s ability.</span></span>  
  
-   <span data-ttu-id="410cf-246">Las conversiones de tipos, ya sean originadas por un compilador de CLR o por una implementación de consulta relacional de objetos, pueden reducir el uso de los índices.</span><span class="sxs-lookup"><span data-stu-id="410cf-246">Type conversions, whether introduced by a CLR compiler or by an Object-Relational query implementation, may curtail index usage.</span></span>  
  
     <span data-ttu-id="410cf-247">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="410cf-247">For example,</span></span>  
  
    ```  
    -- Table DDL  
    create table T5 (  
        Col1      varchar(100)  
    )  
    ```  
  
     [!code-csharp[DLinqMismatch#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#9)]
     [!code-vb[DLinqMismatch#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#9)]  
  
     <span data-ttu-id="410cf-248">Considere la conversión de la expresión `(s = SOME_STRING_CONSTANT)`.</span><span class="sxs-lookup"><span data-stu-id="410cf-248">Consider the translation of expression `(s = SOME_STRING_CONSTANT)`.</span></span>  
  
    ```  
    -- Corresponding part of SQL where clause  
    Where …  
    Col1 = SOME_STRING_CONSTANT  
    -- This expression is of the form <varchar> = <nvarchar>.  
    -- Hence SQL introduces a conversion from varchar to nvarchar,  
    --     resulting in  
    Where …  
    Convert(nvarchar(100), Col1) = SOME_STRING_CONSTANT  
    -- Cannot use the index for column Col1 for some implementations.  
    ```  
  
 <span data-ttu-id="410cf-249">Además de las diferencias semánticas, es importante tener en cuenta el impacto en el rendimiento si se entrecruzan los sistemas de tipos de CLR y SQL Server.</span><span class="sxs-lookup"><span data-stu-id="410cf-249">In addition to semantic differences, it is important to consider impacts to performance when crossing between the SQL Server and CLR type systems.</span></span> <span data-ttu-id="410cf-250">Para los conjuntos de datos grandes, estos problemas de rendimiento pueden determinar si una aplicación se puede implementar o no.</span><span class="sxs-lookup"><span data-stu-id="410cf-250">For large data sets, such performance issues can determine whether an application is deployable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="410cf-251">Vea también</span><span class="sxs-lookup"><span data-stu-id="410cf-251">See Also</span></span>  
 [<span data-ttu-id="410cf-252">Información general</span><span class="sxs-lookup"><span data-stu-id="410cf-252">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
