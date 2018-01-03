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
ms.workload: dotnet
ms.openlocfilehash: 03c2da9f65964a9ed43d1e82abf779b43be733ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="querying-across-relationships"></a>Realizar consultas en varias relaciones
Las referencias a otros objetos o colecciones de otros objetos en sus definiciones de clase se corresponden directamente con relaciones de clave externa en la base de datos. Puede utilizar estas relaciones cuando realice consultas utilizando la notación de punto para tener acceso a las propiedades de la relación y navegar entre los objetos. Estas operaciones de acceso se convierten en combinaciones más complejas o subconsultas correlacionadas en el código SQL equivalente.  
  
 Por ejemplo, la consulta siguiente navega de pedidos a clientes como una manera de restringir los resultados a sólo los pedidos de los clientes de Londres.  
  
 [!code-csharp[DLinqQueryConcepts#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#3)]
 [!code-vb[DLinqQueryConcepts#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#3)]  
  
 Si no existieran propiedades de relación tendría que escribirlas manualmente como *combinaciones*, tal y como lo haría en una consulta SQL, como en el código siguiente:  
  
 [!code-csharp[DLinqQueryConcepts#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#4)]
 [!code-vb[DLinqQueryConcepts#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#4)]  
  
 Puede usar el *relación* propiedad que se va a definir esta relación concreta una vez. Después, puede utilizar la sintaxis de punto más apropiada. Sin embargo, la existencia de las propiedades de relación es más importante porque los modelos de objetos específicos del dominio se definen normalmente como jerarquías o gráficos. Los objetos para los que programa tienen referencias a otros objetos. Es una mera coincidencia que las relaciones de objeto a objeto se correspondan con tipos de relaciones de clave externa en las bases de datos. Por ello, el acceso de propiedad proporciona una manera apropiada de escribir combinaciones.  
  
 A este respecto, las propiedades de relación son más importantes en el lado de los resultados de una consulta que como parte de la propia consulta. Una vez que la consulta ha recuperado los datos sobre un cliente determinado, la definición de clase indica que los clientes tienen pedidos. En otras palabras, se espera que la propiedad `Orders` de un cliente determinado sea una colección que se llena con todos los pedidos de ese cliente. De hecho, esa era su intención cuando definió las clases de esta manera. Espera ver allí los pedidos aun cuando la consulta no los ha solicitado. Espera que su modelo de objetos refleje lo que en realidad se encuentra en una extensión en memoria de la base de datos, con los objetos relacionados inmediatamente disponibles.  
  
 Ahora que tiene las relaciones, puede escribir consultas haciendo referencia a las propiedades de relación definidas en las clases. Estas referencias de relación se corresponden con las relaciones de clave externa de la base de datos. Las operaciones que utilizan estas relaciones se convierten en combinaciones más complejas en el código SQL equivalente. Siempre y cuando haya definido una relación (mediante el atributo <xref:System.Data.Linq.Mapping.AssociationAttribute> ), no tiene que codificar una combinación explícita en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Para ayudar a mantener esta ilusión, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implementa una técnica denominada *carga aplazada*. Para obtener más información, consulte [ejecución diferida frente a carga inmediata](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
 Considere la siguiente consulta SQL para proyectar una lista de `CustomerID` - `OrderID` pares:  
  
```  
SELECT t0.CustomerID, t1.OrderID  
FROM   Customers AS t0 INNER JOIN  
          Orders AS t1 ON t0.CustomerID = t1.CustomerID  
WHERE  (t0.City = @p0)  
```  
  
 Para obtener los mismos resultados en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], utilice la referencia de propiedad `Orders` que ya existe en la clase `Customer`. El `Orders` referencia proporciona la información necesaria para ejecutar la consulta y proyectar el `CustomerID` - `OrderID` pares, como en el código siguiente:  
  
 [!code-csharp[DLinqQueryConcepts#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#5)]
 [!code-vb[DLinqQueryConcepts#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#5)]  
  
 También puede hacer lo contrario. Es decir, puede consultar `Orders` y utilizar su referencia de relación `Customer` para tener acceso a información sobre el objeto `Customer` asociado. El código siguiente proyecta los mismos `CustomerID` - `OrderID` pares como antes, pero esta vez consultando `Orders` en lugar de `Customers`.  
  
 [!code-csharp[DLinqQueryConcepts#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#6)]
 [!code-vb[DLinqQueryConcepts#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#6)]  
  
## <a name="see-also"></a>Vea también  
 [Conceptos sobre consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
