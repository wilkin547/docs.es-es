---
title: Ordenar y filtrar datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: ade08deca909b32090b7d2d7cf8c6ba9ce9e7679
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43538688"
---
# <a name="sorting-and-filtering-data"></a>Ordenar y filtrar datos
La <xref:System.Data.DataView> proporciona varias formas de ordenación y filtrado de datos en una <xref:System.Data.DataTable>:  
  
-   Mediante la propiedad <xref:System.Data.DataView.Sort%2A> puede especificar criterios simples o múltiples de ordenación de columnas e incluir parámetros ASC (ascendente) y DESC (descendente).  
  
-   Mediante la propiedad <xref:System.Data.DataView.ApplyDefaultSort%2A> puede crear automáticamente un criterio de ordenación, en orden ascendente, basado en la columna o columnas de clave principal de la tabla. <xref:System.Data.DataView.ApplyDefaultSort%2A> solo se aplica cuando el **ordenación** propiedad es una referencia nula o una cadena vacía, y cuando la tabla tiene definida una clave principal.  
  
-   Mediante la propiedad <xref:System.Data.DataView.RowFilter%2A> puede especificar subconjuntos de filas basándose en sus valores de columna. Para obtener más información sobre las expresiones válidas para la **RowFilter** propiedad, vea la información de referencia para la <xref:System.Data.DataColumn.Expression%2A> propiedad de la <xref:System.Data.DataColumn> clase.  
  
     Si desea devolver los resultados de una consulta determinada en los datos, en lugar de proporcionar una vista dinámica de un subconjunto de los datos, usen el <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> métodos de la **DataView** para lograr un mejor rendimiento en lugar de establecer el **RowFilter** propiedad. Establecer el **RowFilter** propiedad vuelve a generar el índice de los datos, agrega sobrecarga a la aplicación y reduce el rendimiento. El **RowFilter** propiedad se utiliza mejor en una aplicación enlazada a datos donde un control enlazado muestra resultados filtrados. El **buscar** y **FindRows** métodos aprovechan el índice actual, sin necesidad de volver a generar. Para obtener más información sobre la **buscar** y **FindRows** métodos, vea [buscar filas](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).  
  
-   Mediante la propiedad <xref:System.Data.DataView.RowStateFilter%2A> puede especificar las versiones de fila que desea ver. El **DataView** administra implícitamente qué versión de fila exponer, dependiendo del **RowState** de la fila subyacente. Por ejemplo, si la **RowStateFilter** está establecido en **DataViewRowState.Deleted**, **DataView** expone el **Original** versión de fila de todos los **Deleted** filas porque no hay ningún **actual** versión de fila. Puede determinar qué versión de una fila que se va a se expone mediante el uso de la **RowVersion** propiedad de la **DataRowView**.  
  
     En la tabla siguiente se muestra las opciones para **DataViewRowState**.  
  
    |Opciones de DataViewRowState|Descripción|  
    |------------------------------|-----------------|  
    |**CurrentRows**|El **actual** versión de fila de todos los **Unchanged**, **Added**, y **Modified** filas. Este es el valor predeterminado.|  
    |**Agregado**|El **actual** versión de fila de todos los **Added** filas.|  
    |**Eliminado**|El **Original** versión de fila de todos los **Deleted** filas.|  
    |**ModifiedCurrent**|El **actual** versión de fila de todos los **Modified** filas.|  
    |**ModifiedOriginal**|El **Original** versión de fila de todos los **Modified** filas.|  
    |**Ninguno**|Ninguna fila.|  
    |**OriginalRows**|El **Original** versión de fila de todos los **Unchanged**, **Modified**, y **Deleted** filas.|  
    |**sin cambios**|El **actual** versión de fila de todos los **Unchanged** filas.|  
  
 Para obtener más información sobre los Estados de fila y las versiones de fila, vea [Estados de fila y las versiones de fila](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 En el siguiente ejemplo de código se crea una vista que muestra todos los productos cuyo número de unidades en existencia es menor o igual que el nivel de nuevo pedido, ordenados en primer lugar por id. de proveedor y después por nombre de producto.  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataViewRowState>  
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [Objetos DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
