---
title: Constructor de tipos con nombre (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: c673b58ee5811e3d3b74b3744d3f5291888e2253
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197786"
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="6ef45-102">Constructor de tipos con nombre (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6ef45-102">Named Type Constructor (Entity SQL)</span></span>

<span data-ttu-id="6ef45-103">Se usa para crear instancias de los tipos nominales del modelo conceptual como los tipos de entidad o los tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="6ef45-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ef45-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ef45-104">Syntax</span></span>  
  
```sql  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="6ef45-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6ef45-105">Arguments</span></span>  

 `identifier`  
 <span data-ttu-id="6ef45-106">Valor que es un identificador simple o incluido entre comillas.</span><span class="sxs-lookup"><span data-stu-id="6ef45-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="6ef45-107">Para obtener más información, vea [identificadores](identifiers-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="6ef45-107">For more information see, [Identifiers](identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="6ef45-108">Atributos del tipo que se suponen que conservan el mismo orden que cuando aparecen en la declaración del tipo.</span><span class="sxs-lookup"><span data-stu-id="6ef45-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ef45-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6ef45-109">Return Value</span></span>  

 <span data-ttu-id="6ef45-110">Instancias de tipos complejos con nombre y de tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="6ef45-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ef45-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6ef45-111">Remarks</span></span>  

 <span data-ttu-id="6ef45-112">En los ejemplos siguientes se muestra cómo crear tipos nominales y complejos:</span><span class="sxs-lookup"><span data-stu-id="6ef45-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="6ef45-113">La expresión siguiente crea una instancia de un tipo `Person` :</span><span class="sxs-lookup"><span data-stu-id="6ef45-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="6ef45-114">La expresión siguiente crea una instancia de un tipo complejo:</span><span class="sxs-lookup"><span data-stu-id="6ef45-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="6ef45-115">La expresión siguiente crea una instancia de un tipo complejo anidado:</span><span class="sxs-lookup"><span data-stu-id="6ef45-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="6ef45-116">La expresión siguiente crea una instancia de una entidad con un tipo complejo anidado:</span><span class="sxs-lookup"><span data-stu-id="6ef45-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="6ef45-117">En el ejemplo siguiente se muestra cómo inicializar una propiedad de un tipo complejo en NULL:`MyModel.ZipCode(‘98118’, null)`</span><span class="sxs-lookup"><span data-stu-id="6ef45-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ef45-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ef45-118">Example</span></span>  

 <span data-ttu-id="6ef45-119">La consulta de Entity SQL siguiente usa el constructor de tipos con nombre para crear una instancia de un tipo del modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="6ef45-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="6ef45-120">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="6ef45-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6ef45-121">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6ef45-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6ef45-122">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6ef45-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="6ef45-123">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="6ef45-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NAMED_TYPE_CONSTRUCTOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="6ef45-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ef45-124">See also</span></span>

- [<span data-ttu-id="6ef45-125">Tipos de constructores</span><span class="sxs-lookup"><span data-stu-id="6ef45-125">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="6ef45-126">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6ef45-126">Entity SQL Reference</span></span>](entity-sql-reference.md)
