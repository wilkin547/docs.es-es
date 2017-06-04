---
title: "C&#243;mo: Usar procedimientos almacenados que toman par&#225;metros | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Usar procedimientos almacenados que toman par&#225;metros
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] asigna los parámetros de salida a parámetros de referencia y, para los tipos de valor, declara el parámetro como que acepta valores NULL.  
  
 Para obtener un ejemplo de cómo utilizar un parámetro de entrada en una consulta que devuelve un conjunto de filas, vea [Cómo: Devolver conjuntos de filas](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza un parámetro de entrada único \(el identificador de cliente\) y se devuelve un parámetro de salida \(las ventas totales para ese cliente\).  
  
```  
CREATE PROCEDURE [dbo].[CustOrderTotal]   
@CustomerID nchar(5),  
@TotalSales money OUTPUT  
AS  
SELECT @TotalSales = SUM(OD.UNITPRICE*(1-OD.DISCOUNT) * OD.QUANTITY)  
FROM ORDERS O, "ORDER DETAILS" OD  
where O.CUSTOMERID = @CustomerID AND O.ORDERID = OD.ORDERID  
```  
  
 [!code-csharp[DLinqSprox#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#2)]
 [!code-vb[DLinqSprox#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#2)]  
  
## Ejemplo  
 La llamada a este procedimiento almacenado sería como sigue:  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## Vea también  
 [Procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)   
 [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Utilizar tipos que aceptan valores NULL](../Topic/Using%20Nullable%20Types%20\(C%23%20Programming%20Guide\).md)   
 [Tipos de valor que aceptan valores NULL](../Topic/Nullable%20Value%20Types%20\(Visual%20Basic\).md)