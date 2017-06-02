---
title: "Introducci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Introducci&#243;n
En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], puede utilizar la tecnología [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] para tener acceso a las bases de datos SQL igual que obtendría acceso a una colección en memoria.  
  
 Por ejemplo, en el código siguiente, se crea el objeto `nw` para representar la base de datos `Northwind`, el destino es la tabla `Customers`, las filas se filtran para `Customers` de `London` y se selecciona para la recuperación una cadena de `CompanyName`.  
  
 Cuando se ejecuta el bucle, se recupera la colección de valores `CompanyName`.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## Pasos siguientes  
 Para obtener algunos ejemplos adicionales, que incluyen también operaciones de inserción y actualización, vea [Qué puede hacer con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).  
  
 Luego, intente realizar algunos tutoriales para obtener experiencia práctica en el uso de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  Consulta [Aprender mediante tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).  
  
 Finalmente, obtenga información para comenzar a trabajar en su propio proyecto de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en [Procedimientos típicos para usar LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).  
  
## Vea también  
 [LINQ a SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md)   
 [Introduction to LINQ](../../../../../../ocs/visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)