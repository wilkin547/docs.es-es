---
title: "C&#243;mo: Devolver conjuntos de filas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Devolver conjuntos de filas
Este ejemplo devuelve un conjunto de filas de la base de datos e incluye un parámetro de entrada para filtrar el resultado.  
  
 Al ejecutar un procedimiento almacenado que devuelve un conjunto de filas, se utiliza una clase de *resultado* que almacena los resultados devueltos del procedimiento almacenado.  Para obtener más información, consulta [Analizar el código fuente de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).  
  
## Ejemplo  
 El ejemplo siguiente representa un procedimiento almacenado que devuelve filas de clientes y utiliza un parámetro de entrada para devolver sólo aquellas filas en las que figura "London" como la ciudad del cliente.  En el ejemplo se supone que hay una clase `CustomersByCityResult` enumerable.  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## Vea también  
 [Procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)   
 [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)