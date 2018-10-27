---
title: Modificar objetos DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 3b1e0cbfc6118ad9ca670f5d91183b78b2c99d89
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2018
ms.locfileid: "49453036"
---
# <a name="modifying-dataviews"></a>Modificar objetos DataView
Puede utilizar <xref:System.Data.DataView> para agregar, eliminar o modificar filas de datos de la tabla subyacente. La capacidad para usar el **DataView** modificar datos en la tabla subyacente se controla estableciendo una de las tres propiedades booleanas de la **DataView**. Dichas propiedades son <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> y <xref:System.Data.DataView.AllowDelete%2A>. Se establecen en **true** de forma predeterminada.  
  
 Si **AllowNew** es **true**, puede usar el <xref:System.Data.DataView.AddNew%2A> método de la **DataView** para crear un nuevo <xref:System.Data.DataRowView>. Observe que una nueva fila no se agregó realmente al subyacente <xref:System.Data.DataTable> hasta que el <xref:System.Data.DataRowView.EndEdit%2A> método de la **DataRowView** se llama. Si el <xref:System.Data.DataRowView.CancelEdit%2A> método de la **DataRowView** es llamado, se descartará la nueva fila. Tenga en cuenta también que puede editar sólo una **DataRowView** a la vez. Si se llama a la **AddNew** o **BeginEdit** método de la **DataRowView** mientras exista una fila pendiente, **EndEdit** se llama implícitamente en el fila pendiente. Cuando **EndEdit** es llamado, se aplican los cambios subyacente **DataTable** y más adelante se pueden confirmar o rechazar mediante los **AcceptChanges** o  **RejectChanges** métodos de la **DataTable**, **DataSet**, o **DataRow** objeto. Si **AllowNew** es **false**, se produce una excepción si se llama a la **AddNew** método de la **DataRowView**.  
  
 Si **AllowEdit** es **true**, puede modificar el contenido de un **DataRow** a través de la **DataRowView**. Puede confirmar los cambios realizados en la fila subyacente mediante **DataRowView.EndEdit** o rechazar los cambios mediante **DataRowView.CancelEdit**. Tenga en cuenta que sólo puede modificar una fila cada vez. Si se llama a la **AddNew** o **BeginEdit** métodos de la **DataRowView** mientras exista una fila pendiente, **EndEdit** se llama implícitamente en la fila pendiente. Cuando **EndEdit** se llama, los cambios propuestos se colocan en el **actual** versión de fila de subyacente **DataRow** y más adelante se pueden confirmar o rechazar mediante los  **AcceptChanges** o **RejectChanges** métodos de la **DataTable**, **DataSet**, o **DataRow** objeto. Si **AllowEdit** es **false**, se produce una excepción si intenta modificar un valor en el **DataView**.  
  
 Cuando una existente **DataRowView** se está editando, eventos de subyacente **DataTable** seguirán provocándose con los cambios propuestos. Tenga en cuenta que si se llama a **EndEdit** o **CancelEdit** en subyacente **DataRow**, pendientes los cambios se aplicarán o se cancelarán independientemente  **EndEdit** o **CancelEdit** se llama en el **DataRowView**.  
  
 Si **AllowDelete** es **true**, puede eliminar las filas de la **DataView** utilizando el **eliminar** método de la **DataView**  o **DataRowView** objeto y las filas se eliminan de subyacente **DataTable**. Más tarde puede confirmar o rechazar las eliminaciones mediante **AcceptChanges** o **RejectChanges** respectivamente. Si **AllowDelete** es **false**, se produce una excepción si se llama a la **eliminar** método de la **DataView** o  **DataRowView**.  
  
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
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
