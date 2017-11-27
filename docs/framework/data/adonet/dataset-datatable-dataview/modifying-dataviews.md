---
title: Modificar objetos DataView
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0a8478e9b21c6c2abdc02677305e468109e7b9fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="modifying-dataviews"></a>Modificar objetos DataView
Puede utilizar <xref:System.Data.DataView> para agregar, eliminar o modificar filas de datos de la tabla subyacente. La capacidad para usar el **DataView** modificar datos en la tabla subyacente se controla estableciendo una de las tres propiedades booleanas de la **DataView**. Dichas propiedades son <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> y <xref:System.Data.DataView.AllowDelete%2A>. Se establecen al **true** de forma predeterminada.  
  
 Si **AllowNew** es **true**, puede usar el <xref:System.Data.DataView.AddNew%2A> método de la **DataView** para crear un nuevo <xref:System.Data.DataRowView>. Tenga en cuenta que una nueva fila no se agrega realmente a subyacente <xref:System.Data.DataTable> hasta que el <xref:System.Data.DataRowView.EndEdit%2A> método de la **DataRowView** se llama. Si el <xref:System.Data.DataRowView.CancelEdit%2A> método de la **DataRowView** es llama, se descartará la nueva fila. Tenga en cuenta también que se puede editar sólo uno **DataRowView** a la vez. Si se llama a la **AddNew** o **BeginEdit** método de la **DataRowView** mientras hay una fila pendiente, **EndEdit** se llamará implícitamente en el fila pendiente. Cuando **EndEdit** es llama, los cambios se aplican al subyacente **DataTable** y más tarde se pueden confirmar o rechazar mediante los **AcceptChanges** o  **RejectChanges** métodos de la **DataTable**, **conjunto de datos**, o **DataRow** objeto. Si **AllowNew** es **false**, se produce una excepción si se llama a la **AddNew** método de la **DataRowView**.  
  
 Si **AllowEdit** es **true**, puede modificar el contenido de un **DataRow** a través de la **DataRowView**. Puede confirmar los cambios en la fila subyacente mediante **DataRowView.EndEdit** o rechazar los cambios mediante **DataRowView.CancelEdit**. Tenga en cuenta que sólo puede modificar una fila cada vez. Si se llama a la **AddNew** o **BeginEdit** métodos de la **DataRowView** mientras hay una fila pendiente, **EndEdit** se llamará implícitamente en la fila pendiente. Cuando **EndEdit** se llama, los cambios propuestos se colocan en la **actual** versión de fila de subyacente **DataRow** y más tarde se pueden confirmar o rechazar mediante los  **AcceptChanges** o **RejectChanges** métodos de la **DataTable**, **conjunto de datos**, o **DataRow** objeto. Si **AllowEdit** es **false**, se produce una excepción si intenta modificar un valor en el **DataView**.  
  
 Cuando una existente **DataRowView** se está editando, eventos de subyacente **DataTable** seguirán provocándose con los cambios propuestos. Tenga en cuenta que si se llama a **EndEdit** o **CancelEdit** en subyacente **DataRow**, pendiente cambios se aplicarán o se cancelarán independientemente de si  **EndEdit** o **CancelEdit** se llama en el **DataRowView**.  
  
 Si **AllowDelete** es **true**, puede eliminar filas de la **DataView** mediante el uso de la **eliminar** método de la **DataView**  o **DataRowView** objeto y las filas se eliminan de subyacente **DataTable**. Más tarde puede confirmar o rechazar las eliminaciones mediante **AcceptChanges** o **RejectChanges** respectivamente. Si **AllowDelete** es **false**, se produce una excepción si se llama a la **eliminar** método de la **DataView** o  **DataRowView**.  
  
 En el ejemplo de código siguiente se deshabilita el uso de la **DataView** para eliminar filas y se agrega una nueva fila a la tabla subyacente mediante la **DataView**.  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [Objetos DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
