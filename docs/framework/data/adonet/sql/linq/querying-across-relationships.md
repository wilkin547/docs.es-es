---
title: Realizar consultas en varias relaciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 297878d0-685b-4c01-b2e0-9d731b7322bc
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a347818818fe7c6e15535fd0c2c24548c52e57d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="querying-across-relationships"></a><span data-ttu-id="0b126-102">Realizar consultas en varias relaciones</span><span class="sxs-lookup"><span data-stu-id="0b126-102">Querying Across Relationships</span></span>
<span data-ttu-id="0b126-103">Las referencias a otros objetos o colecciones de otros objetos en sus definiciones de clase se corresponden directamente con relaciones de clave externa en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0b126-103">References to other objects or collections of other objects in your class definitions directly correspond to foreign-key relationships in the database.</span></span> <span data-ttu-id="0b126-104">Puede utilizar estas relaciones cuando realice consultas utilizando la notación de punto para tener acceso a las propiedades de la relación y navegar entre los objetos.</span><span class="sxs-lookup"><span data-stu-id="0b126-104">You can use these relationships when you query by using dot notation to access the relationship properties and navigate from one object to another.</span></span> <span data-ttu-id="0b126-105">Estas operaciones de acceso se convierten en combinaciones más complejas o subconsultas correlacionadas en el código SQL equivalente.</span><span class="sxs-lookup"><span data-stu-id="0b126-105">These access operations translate to more complex joins or correlated subqueries in the equivalent SQL.</span></span>  
  
 <span data-ttu-id="0b126-106">Por ejemplo, la consulta siguiente navega de pedidos a clientes como una manera de restringir los resultados a sólo los pedidos de los clientes de Londres.</span><span class="sxs-lookup"><span data-stu-id="0b126-106">For example, the following query navigates from orders to customers as a way to restrict the results to only those orders for customers located in London.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#3)]
 [!code-vb[DLinqQueryConcepts#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#3)]  
  
 <span data-ttu-id="0b126-107">Si no existieran propiedades de relación tendría que escribirlas manualmente como *combinaciones*, tal y como lo haría en una consulta SQL, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b126-107">If relationship properties did not exist you would have to write them manually as *joins*, just as you would do in a SQL query, as in the following code:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#4)]
 [!code-vb[DLinqQueryConcepts#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#4)]  
  
 <span data-ttu-id="0b126-108">Puede usar el *relación* propiedad que se va a definir esta relación concreta una vez.</span><span class="sxs-lookup"><span data-stu-id="0b126-108">You can use the *relationship* property to define this particular relationship one time.</span></span> <span data-ttu-id="0b126-109">Después, puede utilizar la sintaxis de punto más apropiada.</span><span class="sxs-lookup"><span data-stu-id="0b126-109">You can then use the more convenient dot syntax.</span></span> <span data-ttu-id="0b126-110">Sin embargo, la existencia de las propiedades de relación es más importante porque los modelos de objetos específicos del dominio se definen normalmente como jerarquías o gráficos.</span><span class="sxs-lookup"><span data-stu-id="0b126-110">But relationship properties exist more importantly because domain-specific object models are typically defined as hierarchies or graphs.</span></span> <span data-ttu-id="0b126-111">Los objetos para los que programa tienen referencias a otros objetos.</span><span class="sxs-lookup"><span data-stu-id="0b126-111">The objects that you program against have references to other objects.</span></span> <span data-ttu-id="0b126-112">Es una mera coincidencia que las relaciones de objeto a objeto se correspondan con tipos de relaciones de clave externa en las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="0b126-112">It is only a happy coincidence that object-to-object relationships correspond to foreign-key-styled relationships in databases.</span></span> <span data-ttu-id="0b126-113">Por ello, el acceso de propiedad proporciona una manera apropiada de escribir combinaciones.</span><span class="sxs-lookup"><span data-stu-id="0b126-113">Property access then provides a convenient way to write joins.</span></span>  
  
 <span data-ttu-id="0b126-114">A este respecto, las propiedades de relación son más importantes en el lado de los resultados de una consulta que como parte de la propia consulta.</span><span class="sxs-lookup"><span data-stu-id="0b126-114">With regard to this, relationship properties are more important on the results side of a query than as part of the query itself.</span></span> <span data-ttu-id="0b126-115">Una vez que la consulta ha recuperado los datos sobre un cliente determinado, la definición de clase indica que los clientes tienen pedidos.</span><span class="sxs-lookup"><span data-stu-id="0b126-115">After the query has retrieved data about a particular customer, the class definition indicates that customers have orders.</span></span> <span data-ttu-id="0b126-116">En otras palabras, se espera que la propiedad `Orders` de un cliente determinado sea una colección que se llena con todos los pedidos de ese cliente.</span><span class="sxs-lookup"><span data-stu-id="0b126-116">In other words, you expect the `Orders` property of a particular customer to be a collection that is populated with all the orders from that customer.</span></span> <span data-ttu-id="0b126-117">De hecho, esa era su intención cuando definió las clases de esta manera.</span><span class="sxs-lookup"><span data-stu-id="0b126-117">That is in fact the contract you declared by defining the classes in this manner.</span></span> <span data-ttu-id="0b126-118">Espera ver allí los pedidos aun cuando la consulta no los ha solicitado.</span><span class="sxs-lookup"><span data-stu-id="0b126-118">You expect to see the orders there even if the query did not request orders.</span></span> <span data-ttu-id="0b126-119">Espera que su modelo de objetos refleje lo que en realidad se encuentra en una extensión en memoria de la base de datos, con los objetos relacionados inmediatamente disponibles.</span><span class="sxs-lookup"><span data-stu-id="0b126-119">You expect your object model to maintain an illusion that it is an in-memory extension of the database with related objects immediately available.</span></span>  
  
 <span data-ttu-id="0b126-120">Ahora que tiene las relaciones, puede escribir consultas haciendo referencia a las propiedades de relación definidas en las clases.</span><span class="sxs-lookup"><span data-stu-id="0b126-120">Now that you have relationships, you can write queries by referring to the relationship properties defined in your classes.</span></span> <span data-ttu-id="0b126-121">Estas referencias de relación se corresponden con las relaciones de clave externa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0b126-121">These relationship references correspond to foreign-key relationships in the database.</span></span> <span data-ttu-id="0b126-122">Las operaciones que utilizan estas relaciones se convierten en combinaciones más complejas en el código SQL equivalente.</span><span class="sxs-lookup"><span data-stu-id="0b126-122">Operations that use these relationships translate to more complex joins in the equivalent SQL.</span></span> <span data-ttu-id="0b126-123">Siempre y cuando haya definido una relación (mediante el atributo <xref:System.Data.Linq.Mapping.AssociationAttribute> ), no tiene que codificar una combinación explícita en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b126-123">As long as you have defined a relationship (using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute), you do not have to code an explicit join in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 <span data-ttu-id="0b126-124">Para ayudar a mantener esta ilusión, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implementa una técnica denominada *carga aplazada*.</span><span class="sxs-lookup"><span data-stu-id="0b126-124">To help maintain this illusion, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implements a technique called *deferred loading*.</span></span> <span data-ttu-id="0b126-125">Para obtener más información, consulte [ejecución diferida frente a carga inmediata](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="0b126-125">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
 <span data-ttu-id="0b126-126">Considere la siguiente consulta SQL para proyectar una lista de `CustomerID` - `OrderID` pares:</span><span class="sxs-lookup"><span data-stu-id="0b126-126">Consider the following SQL query to project a list of `CustomerID`-`OrderID` pairs:</span></span>  
  
```  
SELECT t0.CustomerID, t1.OrderID  
FROM   Customers AS t0 INNER JOIN  
          Orders AS t1 ON t0.CustomerID = t1.CustomerID  
WHERE  (t0.City = @p0)  
```  
  
 <span data-ttu-id="0b126-127">Para obtener los mismos resultados en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], utilice la referencia de propiedad `Orders` que ya existe en la clase `Customer`.</span><span class="sxs-lookup"><span data-stu-id="0b126-127">To obtain the same results by using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you use the `Orders` property reference already existing in the `Customer` class.</span></span> <span data-ttu-id="0b126-128">El `Orders` referencia proporciona la información necesaria para ejecutar la consulta y proyectar el `CustomerID` - `OrderID` pares, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b126-128">The `Orders` reference provides the necessary information to execute the query and project the `CustomerID`-`OrderID` pairs, as in the following code:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#5)]
 [!code-vb[DLinqQueryConcepts#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#5)]  
  
 <span data-ttu-id="0b126-129">También puede hacer lo contrario.</span><span class="sxs-lookup"><span data-stu-id="0b126-129">You can also do the reverse.</span></span> <span data-ttu-id="0b126-130">Es decir, puede consultar `Orders` y utilizar su referencia de relación `Customer` para tener acceso a información sobre el objeto `Customer` asociado.</span><span class="sxs-lookup"><span data-stu-id="0b126-130">That is, you can query `Orders` and use its `Customer` relationship reference to access information about the associated `Customer` object.</span></span> <span data-ttu-id="0b126-131">El código siguiente proyecta los mismos `CustomerID` - `OrderID` pares como antes, pero esta vez consultando `Orders` en lugar de `Customers`.</span><span class="sxs-lookup"><span data-stu-id="0b126-131">The following code projects the same `CustomerID`-`OrderID` pairs as before, but this time by querying `Orders` instead of `Customers`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#6)]
 [!code-vb[DLinqQueryConcepts#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0b126-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b126-132">See Also</span></span>  
 [<span data-ttu-id="0b126-133">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="0b126-133">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
