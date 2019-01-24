---
title: Procedimiento Agregar tablas y columnas al Control DataGrid de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: be0bb6d3d7b8d8b362653257139e83900dbb2780
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717875"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Procedimiento Agregar tablas y columnas al Control DataGrid de formularios Windows Forms
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Puede mostrar datos en los formularios de Windows <xref:System.Windows.Forms.DataGrid> control en las tablas y columnas mediante la creación de **DataGridTableStyle** objetos y agregarlos a la **GridTableStylesCollection** objeto, que es tiene acceso a través del <xref:System.Windows.Forms.DataGrid> del control **TableStyles** propiedad. Cada tabla muestra el contenido de la tabla de datos se haya especificado en el **DataGridTableStyle** del objeto **MappingName** propiedad. De forma predeterminada, un estilo de tabla sin estilos de columna especificados mostrará todas las columnas dentro de esa tabla de datos. Puede restringir qué columnas de la tabla aparecen agregando **DataGridColumnStyle** objetos a la **GridColumnStylesCollection** objeto, que se accede mediante el  **GridColumnStyles** propiedad de cada uno **DataGridTableStyle** objeto.  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>Para agregar una tabla y columna a un control DataGrid mediante programación  
  
1.  Para mostrar los datos en la tabla, se debe enlazar el <xref:System.Windows.Forms.DataGrid> control a un conjunto de datos. Para obtener más información, vea [Cómo: Enlazar el Control DataGrid de Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
    > [!CAUTION]
    >  Cuando especifique estilos de columna mediante programación, cree siempre **DataGridColumnStyle** objetos y agregarlos a la **GridColumnStylesCollection** objeto antes de agregar  **DataGridTableStyle** objetos a la **GridTableStylesCollection** objeto. Cuando se agrega un valor vacío **DataGridTableStyle** objeto a la colección, **DataGridColumnStyle** los objetos se generan automáticamente para usted. Por lo tanto, se producirá una excepción si intenta agregar nuevo **DataGridColumnStyle** objetos con duplicado **MappingName** valores para el **GridColumnStylesCollection**objeto.  
  
2.  Declare un nuevo estilo de tabla y establezca su nombre de asignación.  
  
    ```vb  
    Dim ts1 As New DataGridTableStyle()  
    ts1.MappingName = "Customers"  
    ```  
  
    ```csharp  
    DataGridTableStyle ts1 = new DataGridTableStyle();  
    ts1.MappingName = "Customers";  
    ```  
  
    ```cpp  
    DataGridTableStyle* ts1 = new DataGridTableStyle();  
    ts1->MappingName = S"Customers";  
    ```  
  
3.  Declare un nuevo estilo de columna y establezca su nombre de asignación y otras propiedades.  
  
    ```vb  
    Dim myDataCol As New DataGridBoolColumn()  
    myDataCol.HeaderText = "My New Column"  
    myDataCol.MappingName = "Current"  
    ```  
  
    ```csharp  
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();  
    myDataCol.HeaderText = "My New Column";  
    myDataCol.MappingName = "Current";  
    ```  
  
    ```cpp  
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();  
    myDataCol->HeaderText = "My New Column";  
    myDataCol->MappingName = "Current";  
    ```  
  
4.  Llame a la **agregar** método de la **GridColumnStylesCollection** objeto va a agregar la columna para el estilo de tabla  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  Llame a la **agregar** método de la **GridTableStylesCollection** objeto va a agregar el estilo de tabla a la cuadrícula de datos.  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## <a name="see-also"></a>Vea también
- [DataGrid (control)](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [Cómo: Eliminar u ocultar columnas en el Control DataGrid de Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
