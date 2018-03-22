---
title: Constructor de tipos con nombre (Entity SQL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: b572d09b812d43fa64e30a3058da9af01d29b747
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="b764c-102">Constructor de tipos con nombre (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b764c-102">Named Type Constructor (Entity SQL)</span></span>
<span data-ttu-id="b764c-103">Se usa para crear instancias de los tipos nominales del modelo conceptual como los tipos de entidad o los tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="b764c-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b764c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b764c-104">Syntax</span></span>  
  
```  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="b764c-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b764c-105">Arguments</span></span>  
 `identifier`  
 <span data-ttu-id="b764c-106">Valor que es un identificador simple o incluido entre comillas.</span><span class="sxs-lookup"><span data-stu-id="b764c-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="b764c-107">Para obtener más información, vea [identificadores](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="b764c-107">For more information see, [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="b764c-108">Atributos del tipo que se suponen que conservan el mismo orden que cuando aparecen en la declaración del tipo.</span><span class="sxs-lookup"><span data-stu-id="b764c-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b764c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b764c-109">Return Value</span></span>  
 <span data-ttu-id="b764c-110">Instancias de tipos complejos con nombre y de tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="b764c-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b764c-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b764c-111">Remarks</span></span>  
 <span data-ttu-id="b764c-112">En los ejemplos siguientes se muestra cómo crear tipos nominales y complejos:</span><span class="sxs-lookup"><span data-stu-id="b764c-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="b764c-113">La expresión siguiente crea una instancia de un tipo `Person` :</span><span class="sxs-lookup"><span data-stu-id="b764c-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="b764c-114">La expresión siguiente crea una instancia de un tipo complejo:</span><span class="sxs-lookup"><span data-stu-id="b764c-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="b764c-115">La expresión siguiente crea una instancia de un tipo complejo anidado:</span><span class="sxs-lookup"><span data-stu-id="b764c-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="b764c-116">La expresión siguiente crea una instancia de una entidad con un tipo complejo anidado:</span><span class="sxs-lookup"><span data-stu-id="b764c-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="b764c-117">En el ejemplo siguiente se muestra cómo inicializar una propiedad de un tipo complejo en NULL:`MyModel.ZipCode(‘98118’, null)`</span><span class="sxs-lookup"><span data-stu-id="b764c-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="b764c-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b764c-118">Example</span></span>  
 <span data-ttu-id="b764c-119">La consulta de Entity SQL siguiente usa el constructor de tipos con nombre para crear una instancia de un tipo del modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="b764c-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="b764c-120">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="b764c-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b764c-121">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b764c-121">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="b764c-122">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b764c-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="b764c-123">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b764c-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAMED_TYPE_CONSTRUCTOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="b764c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b764c-124">See Also</span></span>  
 [<span data-ttu-id="b764c-125">Tipos de constructores</span><span class="sxs-lookup"><span data-stu-id="b764c-125">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [<span data-ttu-id="b764c-126">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b764c-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
