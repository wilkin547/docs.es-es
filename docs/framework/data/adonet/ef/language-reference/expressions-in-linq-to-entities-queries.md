---
title: "Expresiones en consultas de LINQ to Entities | Microsoft Docs"
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
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Expresiones en consultas de LINQ to Entities
Una expresión es un fragmento de código que se puede evaluar como un valor, objeto, método o espacio de nombres único.  Las expresiones pueden contener un valor literal, una llamada a un método, un operador y sus operandos, o un nombre simple.  Los nombres simples pueden ser el nombre de una variable, el miembro de un tipo, el parámetro de un método, un espacio de nombres o un tipo.  Las expresiones pueden utilizar operadores que a su vez utilizan otras expresiones como parámetros, o llamadas a métodos cuyos parámetros son a su vez otras llamadas a métodos.  Por consiguiente, las expresiones pueden ser de muy simples a muy complejas.  
  
 En las consultas de [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], las expresiones pueden contener cualquier elemento permitido por los tipos dentro del espacio de nombres <xref:System.Linq.Expressions>, incluyéndose las expresiones lambda.  Las expresiones que se pueden utilizar en las consultas de [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] son un supraconjunto de las expresiones que se pueden utilizar para consultar [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].  Las expresiones que forman parte de consultas en [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] están limitadas por las operaciones admitidas por `ObjectQuery<T>` y el origen de datos subyacente.  
  
 En el ejemplo siguiente, la comparación en la cláusula `Where` es una expresión:  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  Las estructuras de un lenguaje concreto, como `unchecked`de C\#, no tienen ningún significado en [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  
  
## En esta sección  
 [Expresiones constantes](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [Expresiones de comparación](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [Comparaciones de NULL](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [Expresiones de inicialización](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [Navigation Properties](http://msdn.microsoft.com/es-es/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
  
## Vea también  
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)