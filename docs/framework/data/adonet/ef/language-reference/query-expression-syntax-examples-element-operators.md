---
title: "Ejemplos de sintaxis de expresiones de consulta: operadores de elementos | Microsoft Docs"
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
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Ejemplos de sintaxis de expresiones de consulta: operadores de elementos
Los ejemplos de este tema muestran cómo se utiliza el método <xref:System.Linq.Enumerable.First%2A> para consultar el [modelo AdventureWorks Sales](http://msdn.microsoft.com/es-es/f16cd988-673f-4376-b034-129ca93c7832) con la sintaxis de las expresiones de consulta.  El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.  
  
 Los ejemplos de este tema utilizan las siguientes instrucciones `using`\/`Imports`:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## First  
  
### Ejemplo  
 En el ejemplo siguiente se usa el método <xref:System.Linq.Enumerable.First%2A> para devolver el primer contacto cuyo nombre es "Brooke".  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## Vea también  
 [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)