---
title: ROW (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
ms.openlocfilehash: 2ab91d0c6d3c3ed3f88a7f0ddbf3a6c2f36d8b04
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202270"
---
# <a name="row-entity-sql"></a><span data-ttu-id="a13b4-102">ROW (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a13b4-102">ROW (Entity SQL)</span></span>

<span data-ttu-id="a13b4-103">Crea registros anónimos con tipos asignados estructuralmente a partir de uno o varios valores.</span><span class="sxs-lookup"><span data-stu-id="a13b4-103">Constructs anonymous, structurally typed records from one or more values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a13b4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a13b4-104">Syntax</span></span>  
  
```sql  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="a13b4-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a13b4-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="a13b4-106">Cualquier expresión de consulta válida que devuelve un valor que se va a crear en un tipo de fila.</span><span class="sxs-lookup"><span data-stu-id="a13b4-106">Any valid query expression that returns a value to construct in a row type.</span></span>  
  
 `alias`  
 <span data-ttu-id="a13b4-107">Especifica un alias para el valor especificado en un tipo de fila.</span><span class="sxs-lookup"><span data-stu-id="a13b4-107">Specifies an alias for the value specified in a row type.</span></span> <span data-ttu-id="a13b4-108">Si no se proporciona un alias, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta generar uno basándose en las reglas de generación de alias de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a13b4-108">If an alias is not provided, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to generate an alias based on the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] alias generation rules.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a13b4-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a13b4-109">Return Value</span></span>  

 <span data-ttu-id="a13b4-110">Un tipo de fila.</span><span class="sxs-lookup"><span data-stu-id="a13b4-110">A row type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a13b4-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a13b4-111">Remarks</span></span>  

 <span data-ttu-id="a13b4-112">Debe utilizar constructores ROW en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para crear registros anónimos escritos estructuralmente de uno o más valores.</span><span class="sxs-lookup"><span data-stu-id="a13b4-112">You use row constructors in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] to construct anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="a13b4-113">El tipo de resultado de un constructor ROW es un tipo de fila cuyos tipos de campo corresponden a los tipos de los valores que se utilizaron para crear la fila.</span><span class="sxs-lookup"><span data-stu-id="a13b4-113">The result type of a row constructor is a row type whose field types correspond to the types of the values that were used to construct the row.</span></span> <span data-ttu-id="a13b4-114">Por ejemplo, la expresión siguiente crea un valor de tipo `Record(a int, b string, c int)`.</span><span class="sxs-lookup"><span data-stu-id="a13b4-114">For example, the following expression constructs a value of type `Record(a int, b string, c int)`.</span></span>  
  
```sql  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 <span data-ttu-id="a13b4-115">Si no proporciona un alias para una expresión en un constructor ROW, Entity Framework intentará generar uno.</span><span class="sxs-lookup"><span data-stu-id="a13b4-115">If you do not provide an alias for an expression in a row constructor, the Entity Framework will try to generate one.</span></span> <span data-ttu-id="a13b4-116">Para obtener más información, vea la sección "Reglas de alias" del tema [Identificadores](identifiers-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="a13b4-116">For more information, see the "Aliasing Rules" section of the [Identifiers](identifiers-entity-sql.md) topic.</span></span>  
  
 <span data-ttu-id="a13b4-117">Las reglas siguientes se aplican a expresiones que usan alias en un constructor ROW:</span><span class="sxs-lookup"><span data-stu-id="a13b4-117">The following rules apply to expression aliasing in a row constructor:</span></span>  
  
- <span data-ttu-id="a13b4-118">Las expresiones en un constructor ROW no pueden hacer referencia a otros alias del mismo constructor.</span><span class="sxs-lookup"><span data-stu-id="a13b4-118">Expressions in a row constructor cannot refer to other aliases in the same constructor.</span></span>  
  
- <span data-ttu-id="a13b4-119">Dos expresiones en el mismo constructor ROW no pueden tener el mismo alias.</span><span class="sxs-lookup"><span data-stu-id="a13b4-119">Two expressions in the same row constructor cannot have the same alias.</span></span>  
  
 <span data-ttu-id="a13b4-120">Para obtener más información sobre los constructores de consultas, vea [construir tipos](constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a13b4-120">For more information about query constructors, see [Constructing Types](constructing-types-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a13b4-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a13b4-121">Example</span></span>  

 <span data-ttu-id="a13b4-122">La consulta de Entity SQL siguiente utiliza el operador ROW para construir registros anónimos escritos estructuralmente.</span><span class="sxs-lookup"><span data-stu-id="a13b4-122">The following Entity SQL query uses the ROW operator to construct anonymous, structurally typed records.</span></span> <span data-ttu-id="a13b4-123">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="a13b4-123">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a13b4-124">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a13b4-124">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="a13b4-125">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="a13b4-125">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="a13b4-126">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a13b4-126">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ROW](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#row)]  
  
## <a name="see-also"></a><span data-ttu-id="a13b4-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a13b4-127">See also</span></span>

- [<span data-ttu-id="a13b4-128">Tipos de constructores</span><span class="sxs-lookup"><span data-stu-id="a13b4-128">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="a13b4-129">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a13b4-129">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="a13b4-130">Definiciones de tipos</span><span class="sxs-lookup"><span data-stu-id="a13b4-130">Type Definitions</span></span>](type-definitions-entity-sql.md)
