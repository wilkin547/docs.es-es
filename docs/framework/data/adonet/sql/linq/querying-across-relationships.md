---
title: "Realizar consultas en varias relaciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 297878d0-685b-4c01-b2e0-9d731b7322bc
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Realizar consultas en varias relaciones
Las referencias a otros objetos o colecciones de otros objetos en sus definiciones de clase se corresponden directamente con relaciones de clave externa en la base de datos.  Puede utilizar estas relaciones cuando realice consultas utilizando la notación de punto para tener acceso a las propiedades de la relación y navegar entre los objetos.  Estas operaciones de acceso se convierten en combinaciones más complejas o subconsultas correlacionadas en el código SQL equivalente.  
  
 Por ejemplo, la consulta siguiente navega de pedidos a clientes como una manera de restringir los resultados a sólo los pedidos de los clientes de Londres.  
  
 [!code-csharp[DLinqQueryConcepts#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#3)]
 [!code-vb[DLinqQueryConcepts#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#3)]  
  
 Si no existieran propiedades de relación, tendría que escribirlas manualmente como *combinaciones*, como lo haría en una consulta SQL y como muestra el código siguiente:  
  
 [!code-csharp[DLinqQueryConcepts#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#4)]
 [!code-vb[DLinqQueryConcepts#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#4)]  
  
 Puede utilizar la propiedad de *relación* para definir esta relación concreta una vez.  Después, puede utilizar la sintaxis de punto más apropiada.  Sin embargo, la existencia de las propiedades de relación es más importante porque los modelos de objetos específicos del dominio se definen normalmente como jerarquías o gráficos.  Los objetos para los que programa tienen referencias a otros objetos.  Es una mera coincidencia que las relaciones de objeto a objeto se correspondan con tipos de relaciones de clave externa en las bases de datos.  Por ello, el acceso de propiedad proporciona una manera apropiada de escribir combinaciones.  
  
 A este respecto, las propiedades de relación son más importantes en el lado de los resultados de una consulta que como parte de la propia consulta.  Una vez que la consulta ha recuperado los datos sobre un cliente determinado, la definición de clase indica que los clientes tienen pedidos.  En otras palabras, se espera que la propiedad `Orders` de un cliente determinado sea una colección que se llena con todos los pedidos de ese cliente.  De hecho, esa era su intención cuando definió las clases de esta manera.  Espera ver allí los pedidos aun cuando la consulta no los ha solicitado.  Espera que su modelo de objetos refleje lo que en realidad se encuentra en una extensión en memoria de la base de datos, con los objetos relacionados inmediatamente disponibles.  
  
 Ahora que tiene las relaciones, puede escribir consultas haciendo referencia a las propiedades de relación definidas en las clases.  Estas referencias de relación se corresponden con las relaciones de clave externa de la base de datos.  Las operaciones que utilizan estas relaciones se convierten en combinaciones más complejas en el código SQL equivalente.  Siempre y cuando haya definido una relación \(mediante el atributo <xref:System.Data.Linq.Mapping.AssociationAttribute> \), no tiene que codificar una combinación explícita en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Para ayudar a mantener esta ilusión, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] implementa una técnica denominada *carga aplazada*.  Para obtener más información, consulte [Comparación entre carga aplazada y carga inmediata](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
 Considere la consulta SQL siguiente para proyectar una lista de pares `CustomerID`\-`OrderID`:  
  
```  
SELECT t0.CustomerID, t1.OrderID  
FROM   Customers AS t0 INNER JOIN  
          Orders AS t1 ON t0.CustomerID = t1.CustomerID  
WHERE  (t0.City = @p0)  
```  
  
 Para obtener los mismos resultados en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], utilice la referencia de propiedad `Orders` que ya existe en la clase `Customer`.  La referencia `Orders` proporciona la información necesaria para ejecutar la consulta y proyectar los pares `CustomerID`\-`OrderID`, como en el código siguiente:  
  
 [!code-csharp[DLinqQueryConcepts#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#5)]
 [!code-vb[DLinqQueryConcepts#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#5)]  
  
 También puede hacer lo contrario.  Es decir, puede consultar `Orders` y utilizar su referencia de relación `Customer` para tener acceso a información sobre el objeto `Customer` asociado.  El código siguiente proyecta los mismos pares `CustomerID`\-`OrderID` que antes, pero esta vez se consulta `Orders` en lugar de `Customers`.  
  
 [!code-csharp[DLinqQueryConcepts#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#6)]
 [!code-vb[DLinqQueryConcepts#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#6)]  
  
## Vea también  
 [Conceptos de consulta](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)