---
title: Modificar objetos DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 8e3a3f92fe8ecc94a041fbcb1540bae18a41dbef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203688"
---
# <a name="modifying-dataviews"></a>Modificar objetos DataView

Puede utilizar <xref:System.Data.DataView> para agregar, eliminar o modificar filas de datos de la tabla subyacente. La capacidad de usar **DataView** para modificar los datos de la tabla subyacente se controla estableciendo una de las tres propiedades booleanas de **DataView**. Dichas propiedades son <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> y <xref:System.Data.DataView.AllowDelete%2A>. Se establecen en **true** de forma predeterminada.  
  
 Si **AllowNew** es **true**, puede usar el <xref:System.Data.DataView.AddNew%2A> método de **DataView** para crear un nuevo <xref:System.Data.DataRowView> . Tenga en cuenta que una nueva fila no se agrega realmente al subyacente <xref:System.Data.DataTable> hasta que <xref:System.Data.DataRowView.EndEdit%2A> se llama al método de la **DataRowView** . Si <xref:System.Data.DataRowView.CancelEdit%2A> se llama al método de la **DataRowView** , se descarta la nueva fila. Tenga en cuenta también que solo puede editar una **DataRowView** a la vez. Si llama al método **AddNew** o **BeginEdit** de la **DataRowView** mientras hay una fila pendiente, se llamará implícitamente a **EndEdit** en la fila pendiente. Cuando se llama a **EndEdit** , los cambios se aplican a la **DataTable** subyacente y, posteriormente, se pueden confirmar o rechazar mediante los métodos **AcceptChanges** o **RejectChanges** del objeto **DataTable**, **DataSet**o **DataRow** . Si **AllowNew** es **false**, se produce una excepción si se llama al método **AddNew** de la **DataRowView**.  
  
 Si **AllowEdit** es **true**, puede modificar el contenido de una **DataRow** a través de la **DataRowView**. Puede confirmar los cambios en la fila subyacente mediante **DataRowView. EndEdit** o rechazar los cambios mediante **DataRowView. CancelEdit**. Tenga en cuenta que sólo puede modificar una fila cada vez. Si llama a los métodos **AddNew** o **BeginEdit** de la **DataRowView** mientras hay una fila pendiente, se llamará implícitamente a **EndEdit** en la fila pendiente. Cuando se llama a **EndEdit** , los cambios propuestos se colocan en la versión de fila **actual** de la **DataRow** subyacente y, posteriormente, se pueden confirmar o rechazar mediante los métodos **AcceptChanges** o **RejectChanges** del objeto **DataTable**, **DataSet**o **DataRow** . Si **AllowEdit** es **false**, se produce una excepción si se intenta modificar un valor en **DataView**.  
  
 Cuando se edita una **DataRowView** existente, los eventos de la **DataTable** subyacente se seguirán generando con los cambios propuestos. Tenga en cuenta que si llama a **EndEdit** o **CancelEdit** en la **DataRow**subyacente, los cambios pendientes se aplicarán o cancelarán independientemente de si se llama a **EndEdit** o a **CancelEdit** en la **DataRowView**.  
  
 Si **AllowDelete** es **true**, puede eliminar filas de **DataView** mediante el método **Delete** del objeto **DataView** o **DataRowView** , y las filas se eliminarán de la **DataTable**subyacente. Más adelante puede confirmar o rechazar las eliminaciones mediante **AcceptChanges** o **RejectChanges** , respectivamente. Si **AllowDelete** es **false**, se produce una excepción si se llama al método **Delete** de **DataView** o **DataRowView**.  
  
 En el ejemplo de código siguiente se deshabilita el uso de **DataView** para eliminar filas y se agrega una nueva fila a la tabla subyacente mediante **DataView**.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [Objetos DataView](dataviews.md)
- [Información general de ADO.NET](../ado-net-overview.md)
