---
title: "Consultas entre tablas (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Consultas entre tablas (LINQ to DataSet)
Además de realizar consultas a una tabla única, también se pueden efectuar consultas entre tablas en [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Esto se consigue mediante una *combinación*.  Una combinación es la asociación de objetos en un origen de datos con objetos que comparten un atributo común en otro origen de datos, como un identificador de contacto o de producto.  En la programación orientada a objetos, las relaciones entre dichos objetos son relativamente fáciles de navegar debido a que cada uno de ellos tiene un miembro que hace referencia a otro. Sin embargo, en tablas de bases de datos externas, navegar por relaciones no es tan sencillo.  Las tablas de bases de datos no contienen relaciones integradas. En estos casos, la operación de combinación se puede usar para hacer coincidir elementos de cada origen.  Por ejemplo, con dos tablas que contienen información de producto y de ventas, se puede utilizar una operación de combinación para hacer coincidir información de ventas y producto del mismo pedido de ventas.  
  
 El marco de trabajo [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] proporciona dos operadores de combinación, <xref:System.Linq.Enumerable.Join%2A> y <xref:System.Linq.Enumerable.GroupJoin%2A>. Estos operadores efectúan *combinaciones de igualdad*: es decir, combinaciones que hacen coincidir dos orígenes de datos únicamente cuando sus claves son iguales.  \(por el contrario, [!INCLUDE[tsql](../../../../includes/tsql-md.md)] admite operadores de combinación distintos de `equals`, como el operador `less than`\).  
  
 En cuanto a las bases de datos relacionales, <xref:System.Linq.Enumerable.Join%2A> implementa una combinación interna.  Una combinación interna es un tipo de combinación en la que solamente se devuelven los objetos que tienen una correspondencia en el conjunto de datos opuesto.  
  
 Los operadores <xref:System.Linq.Enumerable.GroupJoin%2A> no tienen ningún equivalente directo para las bases de datos relacionales; implementan un supraconjunto de combinaciones internas y combinaciones externas izquierdas. Una combinación externa izquierda es una combinación que devuelve cada uno de los elementos de la primera colección \(izquierda\) aunque no tenga ningún elemento correlacionado en la segunda colección.  
  
 Para obtener más información sobre combinaciones, vea [Join Operations](../../../../ocs/visual-basic/programming-guide/concepts/linq/join-operations.md).  
  
## Ejemplo  
 El ejemplo siguiente realiza una combinación tradicional de las tablas `SalesOrderHeader` y `SalesOrderDetail` de la base de datos de ejemplo AdventureWorks para obtener pedidos en línea del mes de agosto.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## Vea también  
 [Consultar DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)   
 [Consultas de tabla única](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)   
 [Consultar DataSets con establecimiento de tipos](../../../../docs/framework/data/adonet/querying-typed-datasets.md)   
 [Join Operations](../../../../ocs/visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [Ejemplos de LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)