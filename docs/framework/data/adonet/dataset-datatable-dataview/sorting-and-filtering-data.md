---
title: "Ordenar y filtrar datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Ordenar y filtrar datos
La <xref:System.Data.DataView> proporciona varias formas de ordenación y filtrado de datos en una <xref:System.Data.DataTable>:  
  
-   Mediante la propiedad <xref:System.Data.DataView.Sort%2A> puede especificar criterios simples o múltiples de ordenación de columnas e incluir parámetros ASC \(ascendente\) y DESC \(descendente\).  
  
-   Mediante la propiedad <xref:System.Data.DataView.ApplyDefaultSort%2A> puede crear automáticamente un criterio de ordenación, en orden ascendente, basado en la columna o columnas de clave principal de la tabla.  <xref:System.Data.DataView.ApplyDefaultSort%2A> solo se aplica cuando la propiedad **Sort** es una referencia nula o una cadena vacía y cuando la tabla tiene definida una clave principal.  
  
-   Mediante la propiedad <xref:System.Data.DataView.RowFilter%2A> puede especificar subconjuntos de filas basándose en sus valores de columna.  Para obtener detalles acerca de las expresiones válidas para la propiedad **RowFilter**, vea la información de referencia para la propiedad <xref:System.Data.DataColumn.Expression%2A> de la clase <xref:System.Data.DataColumn>.  
  
     Si desea devolver los resultados de una consulta determinada en los datos, en lugar de proporcionar una vista dinámica de un subconjunto de los datos, para conseguir el máximo rendimiento utilice los métodos <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> de la **DataView** en lugar de establecer la propiedad **RowFilter**.  El establecimiento de la propiedad **RowFilter** hace que se recompile el índice de los datos, lo que agrega sobrecarga a la aplicación y reduce el rendimiento.  La propiedad **RowFilter** es más idónea en una aplicación enlazada a datos donde un control enlazado muestra resultados filtrados.  Los métodos **Find** y **FindRows** aprovechan el índice actual, sin necesidad de volver a crearlo.  Para obtener más información sobre los métodos **Find** y **FindRows**, vea [Buscar filas](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).  
  
-   Mediante la propiedad <xref:System.Data.DataView.RowStateFilter%2A> puede especificar las versiones de fila que desea ver.  La **DataView** administra implícitamente qué versión de fila exponer, dependiendo del **RowState** de la fila subyacente.  Por ejemplo, si el **RowStateFilter** está establecido como **DataViewRowState.Deleted**, la **DataView** expone la versión de fila **Original** de todas las filas **Deleted** porque no hay ninguna versión de fila **Current**.  Mediante la propiedad **RowVersion** de la **DataRowView** puede determinar qué versión de una fila se está exponiendo.  
  
     En la siguiente tabla se muestran las opciones de **DataViewRowState**.  
  
    |Opciones de DataViewRowState|Descripción|  
    |----------------------------------|-----------------|  
    |**CurrentRows**|La versión de fila **Current** de todas las filas **Unchanged**, **Added** y **Modified**.  Este es el valor predeterminado.|  
    |**Agregado**|La versión de fila **Current** de todas las filas **Added**.|  
    |**Deleted**|La versión de fila **Original** de todas las filas **Deleted**.|  
    |**ModifiedCurrent**|La versión de fila **Current** de todas las filas **Modified**.|  
    |**ModifiedOriginal**|La versión de fila **Original** de todas las filas **Modified**.|  
    |**Ninguna**|Ninguna fila.|  
    |**OriginalRows**|La versión de fila **Original** de todas las filas **Unchanged**, **Modified** y **Deleted**.|  
    |**Sin cambios**|La versión de fila **Current** de todas las filas **Unchanged**.|  
  
 Para obtener más información sobre estados y versiones de fila, vea [Estados de fila y versiones de fila](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
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
  
## Vea también  
 <xref:System.Data.DataViewRowState>   
 <xref:System.Data.DataColumn.Expression%2A?displayProperty=fullName>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)