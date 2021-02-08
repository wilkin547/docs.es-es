---
description: 'Más información acerca de: función (Entity SQL)'
title: FUNCTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: d61aafce03dc7b82b678f1eb107afb79c6c3ed2f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786321"
---
# <a name="function-entity-sql"></a><span data-ttu-id="a6572-103">FUNCTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a6572-103">FUNCTION (Entity SQL)</span></span>

<span data-ttu-id="a6572-104">Define una función en el ámbito de un comando de consulta de Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="a6572-104">Defines a function in the scope of an Entity SQL query command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6572-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6572-105">Syntax</span></span>  
  
```sql  
FUNCTION function-name  
( [ { parameter_name <type_definition>
        [ ,...n ]  
  ]  
) AS ( function_expression )
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )
                | REF ( data_type )
                | ROW ( row_expression )
        }
```  
  
## <a name="arguments"></a><span data-ttu-id="a6572-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a6572-106">Arguments</span></span>  

 `function-name`  
 <span data-ttu-id="a6572-107">El nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="a6572-107">Name of the function.</span></span>  
  
 `parameter-name`  
 <span data-ttu-id="a6572-108">Nombre de un parámetro de la función.</span><span class="sxs-lookup"><span data-stu-id="a6572-108">Name of a parameter in the function.</span></span>  
  
 `function_expression`  
 <span data-ttu-id="a6572-109">Una expresión de Entity SQL válida que es la función.</span><span class="sxs-lookup"><span data-stu-id="a6572-109">A valid Entity SQL expression that is the function.</span></span> <span data-ttu-id="a6572-110">El comando de la función puede actuar sobre los parámetros `parameter_name` pasados a la función.</span><span class="sxs-lookup"><span data-stu-id="a6572-110">The command in the function can act on `parameter_name` parameters passed to the function.</span></span>  
  
 `data_type`  
 <span data-ttu-id="a6572-111">Nombre de un tipo compatible.</span><span class="sxs-lookup"><span data-stu-id="a6572-111">Name of a supported type.</span></span>  
  
 <span data-ttu-id="a6572-112">COLECCIÓN (<type_definition `>` )</span><span class="sxs-lookup"><span data-stu-id="a6572-112">COLLECTION ( <type_definition`>` )</span></span>  
 <span data-ttu-id="a6572-113">Una expresión que devuelve una colección de tipos, filas o referencias compatibles.</span><span class="sxs-lookup"><span data-stu-id="a6572-113">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
 <span data-ttu-id="a6572-114">REF **(** `data_type` **)**</span><span class="sxs-lookup"><span data-stu-id="a6572-114">REF **(**`data_type`**)**</span></span>  
 <span data-ttu-id="a6572-115">Una expresión que devuelve una referencia a un tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="a6572-115">An expression that returns a reference to an entity type.</span></span>  
  
 <span data-ttu-id="a6572-116">ROW **(** `row_expression` **)**</span><span class="sxs-lookup"><span data-stu-id="a6572-116">ROW **(**`row_expression`**)**</span></span>  
 <span data-ttu-id="a6572-117">Una expresión que devuelve registros anónimos y de tipo estructural a partir de uno o varios valores.</span><span class="sxs-lookup"><span data-stu-id="a6572-117">An expression that returns anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="a6572-118">Para obtener más información, consulta [ROW](row-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a6572-118">For more information, see [ROW](row-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6572-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a6572-119">Remarks</span></span>  

 <span data-ttu-id="a6572-120">Es posible declarar varias funciones inline con el mismo nombre, siempre que sus firmas sean distintas.</span><span class="sxs-lookup"><span data-stu-id="a6572-120">Multiple functions with the same name can be declared inline, as long as the function signatures are different.</span></span> <span data-ttu-id="a6572-121">Para obtener más información, consulta [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a6572-121">For more information, see [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span></span>  
  
 <span data-ttu-id="a6572-122">Solo se puede llamar a una función inline en un comando de Entity SQL si dicha función se ha definido en el comando.</span><span class="sxs-lookup"><span data-stu-id="a6572-122">An inline function can be called in an Entity SQL command only after it has been defined in that command.</span></span> <span data-ttu-id="a6572-123">Sin embargo, es posible llamar a una función inline dentro de otra función inline antes o después de definir la función llamada.</span><span class="sxs-lookup"><span data-stu-id="a6572-123">However, an inline function can be called inside another inline function either before or after the called function has been defined.</span></span> <span data-ttu-id="a6572-124">En el ejemplo siguiente, la función A llama a la función B antes de que esta se haya definido:</span><span class="sxs-lookup"><span data-stu-id="a6572-124">In the following example, function A calls function B before function B is defined:</span></span>  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 <span data-ttu-id="a6572-125">Para obtener más información, consulte [Cómo: Llamar a una función definida por el usuario](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a6572-125">For more information, see [How to: Call a User-Defined Function](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).</span></span>  
  
 <span data-ttu-id="a6572-126">Las funciones también se pueden declarar en el modelo.</span><span class="sxs-lookup"><span data-stu-id="a6572-126">Functions can also be declared in the model itself.</span></span> <span data-ttu-id="a6572-127">Las funciones declaradas en el modelo se ejecutan de la misma manera que las funciones declaradas inline en el comando.</span><span class="sxs-lookup"><span data-stu-id="a6572-127">Functions declared in the model are executed in the same way as functions declared inline in the command.</span></span> <span data-ttu-id="a6572-128">Para obtener más información, vea [funciones definidas por el usuario](user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a6572-128">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6572-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6572-129">Example</span></span>  

 <span data-ttu-id="a6572-130">El comando siguiente de Entity SQL define una función `Products` que toma un valor entero para filtrar los productos devueltos.</span><span class="sxs-lookup"><span data-stu-id="a6572-130">The following Entity SQL command defines a function `Products` that takes an integer value to filter the returned products.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION1](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function1)]  
  
## <a name="example"></a><span data-ttu-id="a6572-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6572-131">Example</span></span>  

 <span data-ttu-id="a6572-132">El comando siguiente de Entity SQL define una función `StringReturnsCollection` que toma una colección de cadenas para filtrar los contactos devueltos.</span><span class="sxs-lookup"><span data-stu-id="a6572-132">The following Entity SQL command defines a function `StringReturnsCollection` that takes a collection of strings to filter the returned contacts.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION2](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function2)]  
  
## <a name="see-also"></a><span data-ttu-id="a6572-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6572-133">See also</span></span>

- [<span data-ttu-id="a6572-134">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a6572-134">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="a6572-135">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a6572-135">Entity SQL Language</span></span>](entity-sql-language.md)
