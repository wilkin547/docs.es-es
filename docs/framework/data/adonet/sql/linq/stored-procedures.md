---
title: "Procedimientos almacenados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Procedimientos almacenados
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utiliza métodos del modelo de objetos para representar procedimientos almacenados en la base de datos.  Los métodos se designan como procedimientos almacenados aplicando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute> y, si es necesario, el atributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.  Para obtener más información, consulte [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
 Los desarrolladores que utilizan [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] emplearían normalmente [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para asignar procedimientos almacenados. Los temas de esta sección muestran cómo formar estos métodos y cómo llamarlos en una aplicación si es usted quien escribe el código.  
  
## En esta sección  
 [Cómo: Devolver conjuntos de filas](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 Describe cómo devolver filas de datos y cómo utilizar un parámetro de entrada.  
  
 [Cómo: Usar procedimientos almacenados que toman parámetros](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 Describe cómo utilizar parámetros de entrada y de salida.  
  
 [Cómo: Usar procedimientos almacenados asignados para formas de resultados múltiples](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 Describe cómo hacer que se devuelvan varias formas en el mismo procedimiento almacenado.  
  
 [Cómo: Usar procedimientos almacenados asignados para formas de resultados secuenciales](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 Describe cómo obtener varias formas cuando se conoce la secuencia devuelta.  
  
 [Personalizar las operaciones mediante procedimientos almacenados exclusivamente](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 Describe cómo utilizar procedimientos almacenados para implementar operaciones de inserción, actualización y eliminación.  
  
 [Personalizar las operaciones mediante procedimientos almacenados exclusivamente](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 Describe cómo utilizar únicamente procedimientos almacenados para implementar operaciones de inserción, actualización y eliminación.  
  
## Secciones relacionadas  
 [Guía de programación](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Proporciona información sobre cómo crear y utilizar un modelo de objetos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Tutorial: Usar solo procedimientos almacenados \(Visual Basic\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 Incluye procedimientos que muestran cómo utilizar los procedimientos almacenados en Visual Basic.  
  
 [Tutorial: Usar solo procedimientos almacenados \(C\#\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 Incluye procedimientos que muestran cómo utilizar los procedimientos almacenados en C\#.