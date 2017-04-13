---
title: "Modificar objetos DataView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Modificar objetos DataView
Puede utilizar <xref:System.Data.DataView> para agregar, eliminar o modificar filas de datos de la tabla subyacente.  La posibilidad de utilizar **DataView** para modificar los datos de la tabla subyacente se controla estableciendo una de las tres propiedades booleanas de **DataView**.  Dichas propiedades son <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> y <xref:System.Data.DataView.AllowDelete%2A>.  Están establecidas como **true** de forma predeterminada.  
  
 Si **AllowNew** tiene el valor **true**, puede utilizar el método <xref:System.Data.DataView.AddNew%2A> de la **DataView** para crear una nueva <xref:System.Data.DataRowView>.  Tenga en cuenta que no se agrega realmente una nueva fila a la <xref:System.Data.DataTable> subyacente hasta que se llama al método <xref:System.Data.DataRowView.EndEdit%2A> de la **DataRowView**.  Si se llama al método <xref:System.Data.DataRowView.CancelEdit%2A> de la **DataRowView**, se descartará la nueva fila.  Tenga en cuenta también que sólo puede modificar una **DataRowView** cada vez.  Si se llama al método **AddNew** o **BeginEdit** de la **DataRowView** mientras hay una fila pendiente, se llamará implícitamente a **EndEdit** en la fila pendiente.  Cuando se llama a **EndEdit** se aplican los cambios a la **DataTable** subyacente; más tarde se pueden confirmar o rechazar mediante los métodos **AcceptChanges** o **RejectChanges** del objeto **DataTable**, **DataSet** o **DataRow**.  Cuando **AllowNew** tiene el valor **false**, se iniciará una excepción si llama al método **AddNew** de la **DataRowView**.  
  
 Si **AllowEdit** tiene el valor **true**, puede modificar el contenido de la **DataRow** mediante **DataRowView**.  Puede confirmar los cambios realizados en la fila subyacente mediante **DataRowView.EndEdit** o rechazarlos con **DataRowView.CancelEdit**.  Tenga en cuenta que sólo puede modificar una fila cada vez.  Si se llama a los métodos **AddNew** o **BeginEdit** de la **DataRowView** mientras hay una fila pendiente, se llamará implícitamente a **EndEdit** en la fila pendiente.  Cuando se llama a **EndEdit**, los cambios propuestos se ponen en la versión de fila **Current** de la **DataRow** subyacente; más tarde se pueden confirmar o rechazar mediante los métodos **AcceptChanges** o **RejectChanges** del objeto **DataTable**, **DataSet** o **DataRow**.  Cuando **AllowEdit** tiene el valor **false**, se iniciará una excepción si intenta modificar un valor de la **DataRowView**.  
  
 Cuando se está modificando una **DataRowView** existente, seguirán provocándose eventos con los cambios propuestos de la **DataTable** subyacente.  Tenga en cuenta que si llama a **EndEdit** o a **CancelEdit** en la **DataRow** subyacente, los cambios pendientes se aplicarán o se cancelarán independientemente de que se llame o no a **EndEdit** o a **CancelEdit** en la **DataRowView**.  
  
 Si **AllowDelete** tiene el valor **true**, puede eliminar filas en la **DataView** mediante el método **Delete** del objeto **DataView** o **DataRowView** y las filas se eliminarán de la **DataTable** subyacente.  Más tarde puede confirmar o rechazar las eliminaciones mediante **AcceptChanges** o **RejectChanges**, respectivamente.  Cuando **AllowDelete** tiene el valor **false**, se iniciará una excepción si llama al método **Delete** del objeto **DataView** o **DataRowView**.  
  
 En el siguiente ejemplo de código se deshabilita el uso de **DataView** para eliminar filas y se agrega una nueva fila a la tabla subyacente mediante la **DataView**.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## Vea también  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 <xref:System.Data.DataRowView>   
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)