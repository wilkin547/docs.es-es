---
title: "Consultar DataSets (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Consultar DataSets (LINQ to DataSet)
Después de rellenar un objeto <xref:System.Data.DataSet> con datos se puede empezar a realizar consultas sobre él.  Formular consultas con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] es similar a usar [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] contra otros orígenes de datos habilitados para [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].  No obstante, recuerde que cuando use las consultas de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] en un objeto <xref:System.Data.DataSet> estará consultando una enumeración de objetos <xref:System.Data.DataRow> en lugar de una enumeración de un tipo personalizado.  Esto significa que puede usar cualquier de los miembros de la clase <xref:System.Data.DataRow> en sus consultas de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].  Esto permite crear consultas amplias y complejas.  
  
 Al igual que con otras implementaciones de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], puede crear consultas de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] de dos formas diferentes: sintaxis de expresión de consulta y sintaxis de consulta basada en métodos.  Para obtener más información acerca de estas formas, vea [Getting Started with LINQ](http://msdn.microsoft.com/es-es/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9). Puede usar la sintaxis de expresión de consulta o la sintaxis de consulta basada en métodos para realizar consultas en tablas únicas en un <xref:System.Data.DataSet>, en varias tablas en un <xref:System.Data.DataSet> o en tablas en un <xref:System.Data.DataSet> con tipo.  
  
## En esta sección  
 [Consultas de tabla única](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 Describe cómo realizar consultas en una sola tabla.  
  
 [Consultas entre tablas](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 Describe cómo realizar consultas entre tablas.  
  
 [Consultar DataSets con establecimiento de tipos](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 Describe cómo consultar objetos <xref:System.Data.DataSet> con tipo.  
  
## Vea también  
 [Ejemplos de LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)   
 [Cargar datos en DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)