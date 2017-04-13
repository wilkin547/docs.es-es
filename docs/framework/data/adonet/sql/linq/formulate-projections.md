---
title: "Formular proyecciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Formular proyecciones
En los ejemplos siguientes se muestra cómo la instrucción `select` en C\# y la instrucción `Select` en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] se puede combinar con otras características para formar proyecciones de consulta.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la cláusula `Select` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(cláusula `select` en C\#\) para devolver una secuencia de nombres de contacto de `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## Ejemplo  
 En el ejemplo siguiente se utilizan la cláusula `Select` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(cláusula `select` en C\#\) y *tipos anónimos* para devolver una secuencia de nombres de contacto y números de teléfono de `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## Ejemplo  
 En el ejemplo siguiente se utilizan la cláusula `Select` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(cláusula `select` en C\#\) y *tipos anónimos* para devolver una secuencia de nombres de contacto y números de teléfono de empleados.  Los campos `FirstName` y `LastName` se combinan en un campo único \(`Name`\) y se cambia el nombre del campo `HomePhone` a `Phone` en la secuencia resultante.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la cláusula `Select` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(cláusula `select` en C\#\) y *tipos anónimos* para devolver una secuencia de todos los `ProductID` y un valor calculado denominado `HalfPrice`.  Este valor se establece en `UnitPrice` dividido entre 2.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la cláusula `Select` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(cláusula `select` en C\#\) y una *instrucción condicional* para devolver una secuencia de nombre de producto y disponibilidad de producto.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la cláusula `Select` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(cláusula `select` en C\#\) y un *tipo conocido* \(Name\) para devolver una secuencia de nombres de empleados.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## Ejemplo  
 En el ejemplo siguiente se utilizan las cláusulas `Select` y `Where` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(`select` y `where` en C\#\) para devolver una *secuencia filtrada* de los nombres de contacto de los clientes de Londres.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## Ejemplo  
 En el ejemplo siguiente se utilizan una cláusula `Select` de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(cláusula `select` en C\#\) y *tipos anónimos* para devolver un *subconjunto con forma* de los datos de clientes.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## Ejemplo  
 En el ejemplo siguiente se utilizan consultas anidadas para devolver estos resultados:  
  
-   Una secuencia de todos los pedidos y sus `OrderID` correspondientes.  
  
-   Una subsecuencia de los elementos del pedido que tienen descuento.  
  
-   La cantidad de dinero que se ahorra si no se incluye el envío en el precio.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## Vea también  
 [Ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)