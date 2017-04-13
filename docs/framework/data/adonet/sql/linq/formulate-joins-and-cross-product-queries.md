---
title: "Formular uniones y consultas de varios productos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Formular uniones y consultas de varios productos
En los ejemplos siguientes se muestra cómo combinar los resultados procedentes de varias tablas.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la navegación de clave externa en la cláusula `From` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(cláusula `from` en C\#\) para seleccionar todos los pedidos de los clientes de Londres.  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la navegación de clave externa en la cláusula `Where` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(cláusula `where` en C\#\) para aplicar un filtro y obtener los `Products` agotados cuyo `Supplier` se encuentra en Estados Unidos.  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la navegación de clave externa en la cláusula `From` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(cláusula `from` en C\#\) para aplicar un filtro y obtener los empleados de Seattle y una lista de sus áreas.  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la navegación de clave externa en la cláusula `Select` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(cláusula `select` en C\#\) para aplicar un filtro y obtener pares de empleados de tal forma que uno de ellos esté subordinado al otro, siendo ambos de la misma `City`.  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## Ejemplo  
 En el ejemplo siguiente de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] se buscan todos los clientes y pedidos, se comprueba que los pedidos estén asociados a clientes y se garantiza que para cada cliente de la lista se proporciona un nombre de contacto.  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## Ejemplo  
 En el ejemplo siguiente se combinan explícitamente dos tablas y se proyectan los resultados de ambas.  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## Ejemplo  
 En el ejemplo siguiente se combinan explícitamente tres tablas y se proyectan los resultados de cada una de ellas.  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo lograr una `LEFT OUTER JOIN` mediante `DefaultIfEmpty()`.  El método `DefaultIfEmpty()` devuelve null cuando no hay ningún `Order` para `Employee`.  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## Ejemplo  
 En el ejemplo siguiente se proyecta una expresión `let` que es el resultado de una combinación.  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra una `join` con una clave compuesta.  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo construir una `join` de tal forma que una parte acepte valores NULL y la otra no.  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## Vea también  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)