---
title: "Buscar el valor m&#237;nimo en una secuencia num&#233;rica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 78203093-f242-4572-9b31-9495b10926aa
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Buscar el valor m&#237;nimo en una secuencia num&#233;rica
Utilice al operador <xref:System.Linq.Enumerable.Min%2A> para devolver el valor mínimo de una secuencia de valores numéricos.  
  
## Ejemplo  
 En el ejemplo siguiente se busca el precio unitario más bajo de cualquier producto.  
  
 Si ejecuta esta consulta en la base de datos de ejemplo Northwind, el resultado es: `2.5000`.  
  
 [!code-csharp[DLinqQueryExamples#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#9)]
 [!code-vb[DLinqQueryExamples#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#9)]  
  
## Ejemplo  
 En el ejemplo siguiente se busca el importe con flete más bajo de cualquier pedido.  
  
 Si ejecuta esta consulta en la base de datos de ejemplo Northwind, el resultado es: `0.0200`.  
  
 [!code-csharp[DLinqQueryExamples#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#10)]
 [!code-vb[DLinqQueryExamples#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#10)]  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza Min para encontrar los `Products` que tienen el precio unitario más bajo en cada categoría.  El resultado se organiza por categoría.  
  
 [!code-csharp[DLinqQueryExamples#11](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#11)]
 [!code-vb[DLinqQueryExamples#11](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#11)]  
  
 Si ejecuta la consulta anterior en la base de datos de ejemplo Northwind, los resultados se parecerán a los siguientes:  
  
 `1`  
  
 `Guaraná Fantástica`  
  
 `2`  
  
 `Aniseed Syrup`  
  
 `3`  
  
 `Teatime Chocolate Biscuits`  
  
 `4`  
  
 `Geitost`  
  
 `5`  
  
 `Filo Mix`  
  
 `6`  
  
 `Tourtière`  
  
 `7`  
  
 `Longlife Tofu`  
  
 `8`  
  
 `Konbu`  
  
## Vea también  
 [Consultas de agregado](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)   
 [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)