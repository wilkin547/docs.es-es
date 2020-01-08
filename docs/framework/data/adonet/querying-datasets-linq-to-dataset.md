---
title: Consultar conjuntos de datos (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: bb64abcffdbbcd46dfb11b2564619c565e461436
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634786"
---
# <a name="querying-datasets-linq-to-dataset"></a>Consultar conjuntos de datos (LINQ to DataSet)
Después de rellenar un objeto <xref:System.Data.DataSet> con datos se puede empezar a realizar consultas sobre él. La formulación de consultas con LINQ to DataSet es similar a usar Language-Integrated Query (LINQ) en otros orígenes de datos habilitados para LINQ. No obstante, recuerde que cuando utiliza consultas LINQ sobre un objeto <xref:System.Data.DataSet>, está consultando una enumeración de objetos de <xref:System.Data.DataRow> en lugar de una enumeración de un tipo personalizado. Esto significa que puede usar cualquiera de los miembros de la clase <xref:System.Data.DataRow> en las consultas LINQ. Esto permite crear consultas enriquecidas y complejas.  
  
 Como con otras implementaciones de LINQ, puede crear LINQ to DataSet consultas de dos formas diferentes: sintaxis de expresiones de consulta y sintaxis de consulta basada en métodos. Puede usar la sintaxis de expresión de consulta o la sintaxis de consulta basada en métodos para realizar consultas en tablas únicas en un <xref:System.Data.DataSet>, en tablas múltiples en un <xref:System.Data.DataSet> o en tablas en un <xref:System.Data.DataSet> con tipo.  
  
## <a name="in-this-section"></a>Esta sección  
 [Consultas de tabla única](single-table-queries-linq-to-dataset.md)  
 Describe cómo realizar consultas en una sola tabla.  
  
 [Consultas entre tablas](cross-table-queries-linq-to-dataset.md)  
 Describe cómo realizar consultas entre tablas.  
  
 [Consultar objetos DataSet con tipo](querying-typed-datasets.md)  
 Describe cómo consultar objetos <xref:System.Data.DataSet> con tipo.  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de LINQ to DataSet](linq-to-dataset-examples.md)
- [Carga de datos en un conjunto de datos](loading-data-into-a-dataset.md)
