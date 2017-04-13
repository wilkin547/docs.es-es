---
title: "C&#243;mo: Almacenar y volver a usar consultas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a012bd79-1809-45e3-adea-0229532396cc
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Almacenar y volver a usar consultas
Cuando una aplicación ejecuta muchas veces consultas que tienen una estructura similar, a menudo se mejora el rendimiento si se compila la consulta una vez y se ejecuta varias veces con parámetros diferentes.  Por ejemplo, una aplicación podría tener que recuperar todos los clientes que están en una ciudad determinada, que es especificada por el usuario en un formulario en tiempo de ejecución.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite el uso de *consultas compiladas* para este propósito.  
  
> [!NOTE]
>  Este patrón de utilización representa el uso más común de las consultas compiladas,  pero también son posibles otros enfoques.  Por ejemplo, las consultas compiladas se pueden almacenar como miembros estáticos en una clase parcial que extiende el código generado por el diseñador.  
  
## Ejemplo  
 En muchos escenarios podrían reutilizarse las consultas entre límites de subprocesos.  En tales casos, almacenar las consultas compiladas en variables estáticas es particularmente eficaz.  En el ejemplo de código siguiente se da por supuesto que hay una clase `Queries` diseñada para almacenar las consultas compiladas y que hay una clase Northwind que representa un objeto <xref:System.Data.Linq.DataContext> fuertemente tipado.  
  
 [!code-csharp[DLinqQuerying#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#6)]
 [!code-vb[DLinqQuerying#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#6)]  
  
 [!code-csharp[DLinqQuerying#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#7)]
 [!code-vb[DLinqQuerying#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#7)]  
  
## Ejemplo  
 En estos momentos, no se pueden almacenar \(en variables estáticas\) las consultas que devuelven un *tipo anónimo* porque el tipo no tiene un nombre que se pueda proporcionar como argumento genérico.  En el ejemplo siguiente se muestra cómo se puede solucionar el problema creando un tipo que pueda representar el resultado y, a continuación, cómo se utiliza como argumento genérico.  
  
 [!code-csharp[DLinqQuerying#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#8)]
 [!code-vb[DLinqQuerying#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#8)]  
  
## Vea también  
 <xref:System.Data.Linq.CompiledQuery>   
 [Conceptos de consulta](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)   
 [Consultar la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)