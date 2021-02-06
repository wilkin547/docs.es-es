---
description: 'Más información sobre: ordenación y filtrado de datos'
title: Ordenar y filtrar datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: a8b74dc13e88f8d5e70bb27291e0e6e34817f0ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651618"
---
# <a name="sorting-and-filtering-data"></a>Ordenar y filtrar datos

La <xref:System.Data.DataView> proporciona varias formas de ordenación y filtrado de datos en una <xref:System.Data.DataTable>:  
  
- Mediante la propiedad <xref:System.Data.DataView.Sort%2A> puede especificar criterios simples o múltiples de ordenación de columnas e incluir parámetros ASC (ascendente) y DESC (descendente).  
  
- Mediante la propiedad <xref:System.Data.DataView.ApplyDefaultSort%2A> puede crear automáticamente un criterio de ordenación, en orden ascendente, basado en la columna o columnas de clave principal de la tabla. <xref:System.Data.DataView.ApplyDefaultSort%2A> solo se aplica cuando la propiedad **Sort** es una referencia nula o una cadena vacía y cuando la tabla tiene definida una clave principal.  
  
- Mediante la propiedad <xref:System.Data.DataView.RowFilter%2A> puede especificar subconjuntos de filas basándose en sus valores de columna. Para obtener más información sobre las expresiones válidas para la propiedad **RowFilter** , vea la información de referencia de la <xref:System.Data.DataColumn.Expression%2A> propiedad de la <xref:System.Data.DataColumn> clase.  
  
     Si desea devolver los resultados de una consulta determinada en los datos, en lugar de proporcionar una vista dinámica de un subconjunto de los datos, use los <xref:System.Data.DataView.Find%2A> métodos o <xref:System.Data.DataView.FindRows%2A> de **DataView** para lograr el mejor rendimiento en lugar de establecer la propiedad **RowFilter** . Al establecer la propiedad **RowFilter** se vuelve a generar el índice de los datos, lo que agrega sobrecarga a la aplicación y reduce el rendimiento. La propiedad **RowFilter** se utiliza mejor en una aplicación enlazada a datos donde un control enlazado muestra resultados filtrados. Los métodos **Find** y **FindRows** aprovechan el índice actual sin necesidad de que se vuelva a generar el índice. Para obtener más información sobre los métodos **Find** y **FindRows** , vea [Buscar filas](finding-rows.md).  
  
- Mediante la propiedad <xref:System.Data.DataView.RowStateFilter%2A> puede especificar las versiones de fila que desea ver. **DataView** administra implícitamente la versión de fila que se va a exponer según el **RowState** de la fila subyacente. Por ejemplo, si el **RowStateFilter** está establecido en **DataViewRowState. Deleted**, la **DataView** expone la versión de fila **original** de todas las filas **eliminadas** porque no hay ninguna versión de fila **actual** . Puede determinar la versión de fila de una fila que se expone mediante la propiedad **rowversion** de la **DataRowView**.  
  
     En la tabla siguiente se muestran las opciones de **DataViewRowState**.  
  
    |Opciones de DataViewRowState|Descripción|  
    |------------------------------|-----------------|  
    |**CurrentRows**|Versión de fila **actual** de todas las filas **sin modificar**, **agregadas** y **modificadas** . Este es el valor predeterminado.|  
    |**Agregado**|Versión de fila **actual** de todas las filas **agregadas** .|  
    |**Eliminado**|La versión de fila **original** de todas las filas **eliminadas** .|  
    |**ModifiedCurrent**|Versión de fila **actual** de todas las filas **modificadas** .|  
    |**ModifiedOriginal**|La versión de fila **original** de todas las filas **modificadas** .|  
    |**Ninguno**|Ninguna fila.|  
    |**OriginalRows**|La versión de fila **original** de todas las filas **sin modificar**, **modificadas** y **eliminadas** .|  
    |**Sin cambios**|Versión de fila **actual** de todas las filas **sin modificar** .|  
  
 Para obtener más información sobre los Estados de fila y las versiones de fila, vea [Estados de fila y versiones](row-states-and-row-versions.md)de fila.  
  
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

- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [Objetos DataView](dataviews.md)
- [Información general de ADO.NET](../ado-net-overview.md)
