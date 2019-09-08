---
title: Consultar conjuntos de datos (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: 79a9b320fbdbfecc3f7d531d992b1529873871a5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783051"
---
# <a name="querying-datasets-linq-to-dataset"></a>Consultar conjuntos de datos (LINQ to DataSet)
Después de rellenar un objeto <xref:System.Data.DataSet> con datos se puede empezar a realizar consultas sobre él. La formulación de consultas con LINQ to DataSet es similar a [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] usar en [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]otros orígenes de datos habilitados para. No obstante, recuerde que cuando utiliza [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] consultas en un <xref:System.Data.DataSet> objeto, está consultando una enumeración de <xref:System.Data.DataRow> objetos, en lugar de una enumeración de un tipo personalizado. Esto significa que puede usar cualquiera de los miembros de la <xref:System.Data.DataRow> clase [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] en las consultas. Esto permite crear consultas amplias y complejas.  
  
 Al igual que con otras implementaciones de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], puede crear LINQ to DataSet consultas de dos formas diferentes: sintaxis de expresiones de consulta y sintaxis de consulta basada en métodos. Puede usar la sintaxis de expresión de consulta o la sintaxis de consulta basada en métodos para realizar consultas en tablas únicas en un <xref:System.Data.DataSet>, en tablas múltiples en un <xref:System.Data.DataSet> o en tablas en un <xref:System.Data.DataSet> con tipo.  
  
## <a name="in-this-section"></a>En esta sección  
 [Consultas de tabla única](single-table-queries-linq-to-dataset.md)  
 Describe cómo realizar consultas en una sola tabla.  
  
 [Consultas entre tablas](cross-table-queries-linq-to-dataset.md)  
 Describe cómo realizar consultas entre tablas.  
  
 [Consultar objetos DataSet con tipo](querying-typed-datasets.md)  
 Describe cómo consultar objetos <xref:System.Data.DataSet> con tipo.  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de LINQ to DataSet](linq-to-dataset-examples.md)
- [Carga de datos en un conjunto de datos](loading-data-into-a-dataset.md)
