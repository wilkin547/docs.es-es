---
title: Consultar conjuntos de datos (LINQ to DataSet)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4f1b1a70025dc81bdf99c636b65c23d373e73a80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="querying-datasets-linq-to-dataset"></a>Consultar conjuntos de datos (LINQ to DataSet)
Después de rellenar un objeto <xref:System.Data.DataSet> con datos se puede empezar a realizar consultas sobre él. Formular consultas con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] es similar a usar [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] contra otros orígenes de datos habilitados para [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]. Recuerde, no obstante, que cuando se usa [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] consultas con un <xref:System.Data.DataSet> objeto que está consultando una enumeración de <xref:System.Data.DataRow> objetos, en lugar de una enumeración de un tipo personalizado. Esto significa que puede utilizar cualquiera de los miembros de la <xref:System.Data.DataRow> clase en su [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] consultas. Esto permite crear consultas amplias y complejas.  
  
 Al igual que con otras implementaciones de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], puede crear [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consultas de dos formas diferentes: sintaxis de expresión consulta y sintaxis de consultas basadas en métodos. Para obtener más información acerca de estas dos formas, consulte [Introducción a LINQ](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9). Puede usar la sintaxis de expresión de consulta o la sintaxis de consulta basada en métodos para realizar consultas en tablas únicas en un <xref:System.Data.DataSet>, en tablas múltiples en un <xref:System.Data.DataSet> o en tablas en un <xref:System.Data.DataSet> con tipo.  
  
## <a name="in-this-section"></a>En esta sección  
 [Consultas de tabla única](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 Describe cómo realizar consultas en una sola tabla.  
  
 [Consultas entre tablas](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 Describe cómo realizar consultas entre tablas.  
  
 [Consultar conjuntos de datos con tipo](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 Describe cómo consultar objetos <xref:System.Data.DataSet> con tipo.  
  
## <a name="see-also"></a>Vea también  
 [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [Para cargar datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
