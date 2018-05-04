---
title: Agregar un objeto DataTable a un objeto DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
ms.openlocfilehash: 3554790bb65310031b00ca5fb320aa4c111e1e11
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="adding-a-datatable-to-a-dataset"></a>Agregar un objeto DataTable a un objeto DataSet
ADO.NET permite crear objetos <xref:System.Data.DataTable> y agregarlos a un <xref:System.Data.DataSet> existente. Es posible establecer información de restricciones para una <xref:System.Data.DataTable> mediante las propiedades  <xref:System.Data.DataTable.PrimaryKey%2A> y <xref:System.Data.DataColumn.Unique%2A>.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se construye un <xref:System.Data.DataSet>, se agrega un objeto <xref:System.Data.DataTable> nuevo al <xref:System.Data.DataSet> y, a continuación, se agregan tres objetos <xref:System.Data.DataColumn> a la tabla. Por ultimo, el código establece una columna como columna de clave principal.  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a>Distinción de mayúsculas y minúsculas  
 Pueden existir dos o más tablas o relaciones con el mismo nombre, pero que difieran en mayúsculas y minúsculas, en un <xref:System.Data.DataSet>. En estos casos, las referencias a tablas y relaciones por nombre distinguen mayúsculas y minúsculas. Por ejemplo, si la <xref:System.Data.DataSet> **conjunto de datos** contiene tablas **Table1** y **table1**, debe hacer referencia a **Table1** por su nombre como **dataSet.Tables["Table1"]**, y **table1** como **dataSet.Tables["table1"]**. Intentar hacer referencia a cualquiera de las tablas mediante **dataSet.Tables["TABLE1"]** generaría una excepción.  
  
 El comportamiento de distinción entre mayúsculas y minúsculas no se aplica si sólo hay una tabla o relación con un nombre concreto. Por ejemplo, si la <xref:System.Data.DataSet> sólo tiene **Table1**, se puede hacer referencia a él mediante **dataSet.Tables["TABLE1"]**.  
  
> [!NOTE]
>  La propiedad <xref:System.Data.DataSet.CaseSensitive%2A> del <xref:System.Data.DataSet> no afecta a este comportamiento. La propiedad <xref:System.Data.DataSet.CaseSensitive%2A> se aplica a los datos del <xref:System.Data.DataSet> y afecta a la ordenación, la búsqueda, el filtrado, la aplicación de restricciones, etc.  
  
## <a name="namespace-support"></a>Compatibilidad con los espacios de nombres  
 En las versiones de ADO.NET anteriores a la versión 2.0, dos tablas no podían tener el mismo nombre, aunque se encontrasen en espacios de nombres diferentes. Esta limitación se quitó en ADO.NET 2.0. Un <xref:System.Data.DataSet> puede contener dos tablas con el mismo valor de propiedad <xref:System.Data.DataTable.TableName%2A>, pero con valores de propiedad <xref:System.Data.DataTable.Namespace%2A> diferentes.  
  
## <a name="see-also"></a>Vea también  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
