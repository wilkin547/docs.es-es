---
title: FUNCTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: 4e06b5bf8a2ca62630666ab3e8ba35f0425e3988
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148040"
---
# <a name="function-entity-sql"></a><span data-ttu-id="af0d6-102">FUNCTION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="af0d6-102">FUNCTION (Entity SQL)</span></span>

<span data-ttu-id="af0d6-103">Define una función en el ámbito de un comando de consulta de Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="af0d6-103">Defines a function in the scope of an Entity SQL query command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af0d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af0d6-104">Syntax</span></span>  
  
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
  
## <a name="arguments"></a><span data-ttu-id="af0d6-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="af0d6-105">Arguments</span></span>  

 `function-name`  
 <span data-ttu-id="af0d6-106">El nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="af0d6-106">Name of the function.</span></span>  
  
 `parameter-name`  
 <span data-ttu-id="af0d6-107">Nombre de un parámetro de la función.</span><span class="sxs-lookup"><span data-stu-id="af0d6-107">Name of a parameter in the function.</span></span>  
  
 `function_expression`  
 <span data-ttu-id="af0d6-108">Una expresión de Entity SQL válida que es la función.</span><span class="sxs-lookup"><span data-stu-id="af0d6-108">A valid Entity SQL expression that is the function.</span></span> <span data-ttu-id="af0d6-109">El comando de la función puede actuar sobre los parámetros `parameter_name` pasados a la función.</span><span class="sxs-lookup"><span data-stu-id="af0d6-109">The command in the function can act on `parameter_name` parameters passed to the function.</span></span>  
  
 `data_type`  
 <span data-ttu-id="af0d6-110">Nombre de un tipo compatible.</span><span class="sxs-lookup"><span data-stu-id="af0d6-110">Name of a supported type.</span></span>  
  
 <span data-ttu-id="af0d6-111">COLECCIÓN (<type_definition `>` )</span><span class="sxs-lookup"><span data-stu-id="af0d6-111">COLLECTION ( <type_definition`>` )</span></span>  
 <span data-ttu-id="af0d6-112">Una expresión que devuelve una colección de tipos, filas o referencias compatibles.</span><span class="sxs-lookup"><span data-stu-id="af0d6-112">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
 <span data-ttu-id="af0d6-113">REF **(** `data_type` **)**</span><span class="sxs-lookup"><span data-stu-id="af0d6-113">REF **(**`data_type`**)**</span></span>  
 <span data-ttu-id="af0d6-114">Una expresión que devuelve una referencia a un tipo de entidad.</span><span class="sxs-lookup"><span data-stu-id="af0d6-114">An expression that returns a reference to an entity type.</span></span>  
  
 <span data-ttu-id="af0d6-115">ROW **(** `row_expression` **)**</span><span class="sxs-lookup"><span data-stu-id="af0d6-115">ROW **(**`row_expression`**)**</span></span>  
 <span data-ttu-id="af0d6-116">Una expresión que devuelve registros anónimos y de tipo estructural a partir de uno o varios valores.</span><span class="sxs-lookup"><span data-stu-id="af0d6-116">An expression that returns anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="af0d6-117">Para obtener más información, consulta [ROW](row-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="af0d6-117">For more information, see [ROW](row-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af0d6-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="af0d6-118">Remarks</span></span>  

 <span data-ttu-id="af0d6-119">Es posible declarar varias funciones inline con el mismo nombre, siempre que sus firmas sean distintas.</span><span class="sxs-lookup"><span data-stu-id="af0d6-119">Multiple functions with the same name can be declared inline, as long as the function signatures are different.</span></span> <span data-ttu-id="af0d6-120">Para obtener más información, consulta [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="af0d6-120">For more information, see [Function Overload Resolution](function-overload-resolution-entity-sql.md).</span></span>  
  
 <span data-ttu-id="af0d6-121">Solo se puede llamar a una función inline en un comando de Entity SQL si dicha función se ha definido en el comando.</span><span class="sxs-lookup"><span data-stu-id="af0d6-121">An inline function can be called in an Entity SQL command only after it has been defined in that command.</span></span> <span data-ttu-id="af0d6-122">Sin embargo, es posible llamar a una función inline dentro de otra función inline antes o después de definir la función llamada.</span><span class="sxs-lookup"><span data-stu-id="af0d6-122">However, an inline function can be called inside another inline function either before or after the called function has been defined.</span></span> <span data-ttu-id="af0d6-123">En el ejemplo siguiente, la función A llama a la función B antes de que esta se haya definido:</span><span class="sxs-lookup"><span data-stu-id="af0d6-123">In the following example, function A calls function B before function B is defined:</span></span>  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 <span data-ttu-id="af0d6-124">Para obtener más información, consulte [Cómo: Llamar a una función definida por el usuario](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="af0d6-124">For more information, see [How to: Call a User-Defined Function](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).</span></span>  
  
 <span data-ttu-id="af0d6-125">Las funciones también se pueden declarar en el modelo.</span><span class="sxs-lookup"><span data-stu-id="af0d6-125">Functions can also be declared in the model itself.</span></span> <span data-ttu-id="af0d6-126">Las funciones declaradas en el modelo se ejecutan de la misma manera que las funciones declaradas inline en el comando.</span><span class="sxs-lookup"><span data-stu-id="af0d6-126">Functions declared in the model are executed in the same way as functions declared inline in the command.</span></span> <span data-ttu-id="af0d6-127">Para obtener más información, vea [funciones definidas por el usuario](user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="af0d6-127">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af0d6-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af0d6-128">Example</span></span>  

 <span data-ttu-id="af0d6-129">El comando siguiente de Entity SQL define una función `Products` que toma un valor entero para filtrar los productos devueltos.</span><span class="sxs-lookup"><span data-stu-id="af0d6-129">The following Entity SQL command defines a function `Products` that takes an integer value to filter the returned products.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION1](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function1)]  
  
## <a name="example"></a><span data-ttu-id="af0d6-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af0d6-130">Example</span></span>  

 <span data-ttu-id="af0d6-131">El comando siguiente de Entity SQL define una función `StringReturnsCollection` que toma una colección de cadenas para filtrar los contactos devueltos.</span><span class="sxs-lookup"><span data-stu-id="af0d6-131">The following Entity SQL command defines a function `StringReturnsCollection` that takes a collection of strings to filter the returned contacts.</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION2](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function2)]  
  
## <a name="see-also"></a><span data-ttu-id="af0d6-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="af0d6-132">See also</span></span>

- [<span data-ttu-id="af0d6-133">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="af0d6-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="af0d6-134">Lenguaje Entity SQL</span><span class="sxs-lookup"><span data-stu-id="af0d6-134">Entity SQL Language</span></span>](entity-sql-language.md)
