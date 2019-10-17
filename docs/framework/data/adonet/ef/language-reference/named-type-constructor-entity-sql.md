---
title: Constructor de tipos con nombre (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: f40adce1a9e031ed0b7cd5d03d9c63db255aa610
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319571"
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="e678b-102">Constructor de tipos con nombre (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e678b-102">Named Type Constructor (Entity SQL)</span></span>
<span data-ttu-id="e678b-103">Se usa para crear instancias de los tipos nominales del modelo conceptual como los tipos de entidad o los tipos complejos.</span><span class="sxs-lookup"><span data-stu-id="e678b-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e678b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e678b-104">Syntax</span></span>  
  
```sql  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="e678b-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e678b-105">Arguments</span></span>  
 `identifier`  
 <span data-ttu-id="e678b-106">Valor que es un identificador simple o incluido entre comillas.</span><span class="sxs-lookup"><span data-stu-id="e678b-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="e678b-107">Para obtener más información, vea [identificadores](identifiers-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="e678b-107">For more information see, [Identifiers](identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="e678b-108">Atributos del tipo que se suponen que conservan el mismo orden que cuando aparecen en la declaración del tipo.</span><span class="sxs-lookup"><span data-stu-id="e678b-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e678b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e678b-109">Return Value</span></span>  
 <span data-ttu-id="e678b-110">Instancias de tipos complejos con nombre y de tipos de entidad.</span><span class="sxs-lookup"><span data-stu-id="e678b-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e678b-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e678b-111">Remarks</span></span>  
 <span data-ttu-id="e678b-112">En los ejemplos siguientes se muestra cómo crear tipos nominales y complejos:</span><span class="sxs-lookup"><span data-stu-id="e678b-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="e678b-113">La expresión siguiente crea una instancia de un tipo `Person` :</span><span class="sxs-lookup"><span data-stu-id="e678b-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="e678b-114">La expresión siguiente crea una instancia de un tipo complejo:</span><span class="sxs-lookup"><span data-stu-id="e678b-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="e678b-115">La expresión siguiente crea una instancia de un tipo complejo anidado:</span><span class="sxs-lookup"><span data-stu-id="e678b-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="e678b-116">La expresión siguiente crea una instancia de una entidad con un tipo complejo anidado:</span><span class="sxs-lookup"><span data-stu-id="e678b-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="e678b-117">En el ejemplo siguiente se muestra cómo inicializar una propiedad de un tipo complejo en NULL:`MyModel.ZipCode(‘98118’, null)`</span><span class="sxs-lookup"><span data-stu-id="e678b-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="e678b-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e678b-118">Example</span></span>  
 <span data-ttu-id="e678b-119">La consulta de Entity SQL siguiente usa el constructor de tipos con nombre para crear una instancia de un tipo del modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="e678b-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="e678b-120">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="e678b-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e678b-121">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e678b-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e678b-122">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e678b-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="e678b-123">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e678b-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NAMED_TYPE_CONSTRUCTOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="e678b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e678b-124">See also</span></span>

- [<span data-ttu-id="e678b-125">Tipos de constructores</span><span class="sxs-lookup"><span data-stu-id="e678b-125">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="e678b-126">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e678b-126">Entity SQL Reference</span></span>](entity-sql-reference.md)
