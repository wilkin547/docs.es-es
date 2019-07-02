---
title: Consultar conjuntos de datos (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: ec4ee345835294499f7ac9f665a9b79e2efc0f64
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504655"
---
# <a name="querying-datasets-linq-to-dataset"></a>Consultar conjuntos de datos (LINQ to DataSet)
Después de rellenar un objeto <xref:System.Data.DataSet> con datos se puede empezar a realizar consultas sobre él. Formulación de consultas con LINQ to DataSet es similar a usar [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] con otros [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-orígenes de datos habilitados. Recuerde, no obstante, que cuando usas [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] consultas sobre un <xref:System.Data.DataSet> objeto que está consultando una enumeración de <xref:System.Data.DataRow> objetos, en lugar de una enumeración de un tipo personalizado. Esto significa que puede usar cualquiera de los miembros de la <xref:System.Data.DataRow> clase en su [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] consultas. Esto permite crear consultas amplias y complejas.  
  
 Igual que con otras implementaciones de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], puede crear LINQ a consultas de conjunto de datos de dos formas diferentes: sintaxis de expresiones y la sintaxis de consulta basada en métodos de consulta. Puede usar la sintaxis de expresión de consulta o la sintaxis de consulta basada en métodos para realizar consultas en tablas únicas en un <xref:System.Data.DataSet>, en tablas múltiples en un <xref:System.Data.DataSet> o en tablas en un <xref:System.Data.DataSet> con tipo.  
  
## <a name="in-this-section"></a>En esta sección  
 [Consultas de tabla única](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 Describe cómo realizar consultas en una sola tabla.  
  
 [Consultas entre tablas](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)  
 Describe cómo realizar consultas entre tablas.  
  
 [Consultar objetos DataSet con tipo](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 Describe cómo consultar objetos <xref:System.Data.DataSet> con tipo.  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [Carga de datos en un conjunto de datos](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
