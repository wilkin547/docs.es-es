---
title: "Ejemplos de sintaxis de consulta basada en m&#233;todos: Agrupaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Ejemplos de sintaxis de consulta basada en m&#233;todos: Agrupaci&#243;n
Los ejemplos de este tema muestran cómo se utiliza el método `GroupBy` para consultar el [modelo AdventureWorks Sales](http://msdn.microsoft.com/es-es/f16cd988-673f-4376-b034-129ca93c7832) utilizando la sintaxis de consulta basada en métodos.  El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail de la base de datos de ejemplo AdventureWorks.  
  
 Los ejemplos de este tema utilizan las siguientes instrucciones `using`\/`Imports`:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza el método `GroupBy` para devolver objetos `Address` agrupados por código postal.  Los resultados se proyectan en un tipo anónimo.  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza el método `GroupBy` para devolver objetos `Contact` agrupados por la primera letra del apellido del contacto.  Los resultados se ordenan también por la primera letra del apellido y se proyectan en un tipo anónimo.  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza el método `GroupBy` para devolver objetos `SalesOrderHeader` agrupados por identificador de cliente.  También se devuelve el número de ventas para cada cliente.  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## Vea también  
 [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)