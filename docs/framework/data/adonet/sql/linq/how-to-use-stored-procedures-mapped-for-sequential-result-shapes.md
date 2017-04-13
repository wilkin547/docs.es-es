---
title: "C&#243;mo: Usar procedimientos almacenados asignados para formas de resultados secuenciales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Usar procedimientos almacenados asignados para formas de resultados secuenciales
Este tipo de procedimiento almacenado puede generar más de una forma de resultado, pero se sabe en qué orden se devuelven los resultados.  Compare este escenario con el escenario donde no se sabe el orden de los resultados devueltos.  Para obtener más información, consulta [Cómo: Usar procedimientos almacenados asignados para formas de resultados múltiples](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).  
  
## Ejemplo  
 A continuación se muestra el código T\-SQL de un procedimiento almacenado que devuelve varias formas de resultados secuencialmente:  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## Ejemplo  
 Usaría código similar al siguiente para ejecutar este procedimiento almacenado.  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## Vea también  
 [Procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)