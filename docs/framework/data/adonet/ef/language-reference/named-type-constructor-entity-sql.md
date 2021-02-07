---
description: 'Más información sobre: constructor de tipos con nombre (Entity SQL)'
title: Constructor de tipos con nombre (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: e5ec811f814898661cf8de28de1fb8406647332d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696547"
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="23fcf-103">Constructor de tipos con nombre (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="23fcf-103">Named Type Constructor (Entity SQL)</span></span>

<span data-ttu-id="23fcf-104">Se usa para crear instancias de los tipos nominales del modelo conceptual como los tipos de entidad o los tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="23fcf-104">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23fcf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23fcf-105">Syntax</span></span>  
  
```sql  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="23fcf-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="23fcf-106">Arguments</span></span>  

 `identifier`  
 <span data-ttu-id="23fcf-107">Valor que es un identificador simple o incluido entre comillas.</span><span class="sxs-lookup"><span data-stu-id="23fcf-107">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="23fcf-108">Para obtener más información, vea [identificadores](identifiers-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="23fcf-108">For more information see, [Identifiers](identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="23fcf-109">Atributos del tipo que se suponen que conservan el mismo orden que cuando aparecen en la declaración del tipo.</span><span class="sxs-lookup"><span data-stu-id="23fcf-109">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23fcf-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="23fcf-110">Return Value</span></span>  

 <span data-ttu-id="23fcf-111">Instancias de tipos complejos con nombre y de tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="23fcf-111">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23fcf-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="23fcf-112">Remarks</span></span>  

 <span data-ttu-id="23fcf-113">En los ejemplos siguientes se muestra cómo crear tipos nominales y complejos:</span><span class="sxs-lookup"><span data-stu-id="23fcf-113">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="23fcf-114">La expresión siguiente crea una instancia de un tipo `Person` :</span><span class="sxs-lookup"><span data-stu-id="23fcf-114">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="23fcf-115">La expresión siguiente crea una instancia de un tipo complejo:</span><span class="sxs-lookup"><span data-stu-id="23fcf-115">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="23fcf-116">La expresión siguiente crea una instancia de un tipo complejo anidado:</span><span class="sxs-lookup"><span data-stu-id="23fcf-116">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="23fcf-117">La expresión siguiente crea una instancia de una entidad con un tipo complejo anidado:</span><span class="sxs-lookup"><span data-stu-id="23fcf-117">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="23fcf-118">En el ejemplo siguiente se muestra cómo inicializar una propiedad de un tipo complejo en NULL:`MyModel.ZipCode(‘98118’, null)`</span><span class="sxs-lookup"><span data-stu-id="23fcf-118">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="23fcf-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="23fcf-119">Example</span></span>  

 <span data-ttu-id="23fcf-120">La consulta de Entity SQL siguiente usa el constructor de tipos con nombre para crear una instancia de un tipo del modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="23fcf-120">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="23fcf-121">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="23fcf-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="23fcf-122">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="23fcf-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="23fcf-123">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="23fcf-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="23fcf-124">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="23fcf-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NAMED_TYPE_CONSTRUCTOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="23fcf-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="23fcf-125">See also</span></span>

- [<span data-ttu-id="23fcf-126">Tipos de constructores</span><span class="sxs-lookup"><span data-stu-id="23fcf-126">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="23fcf-127">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="23fcf-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
