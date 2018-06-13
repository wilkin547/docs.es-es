---
title: 'Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms'
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
ms.openlocfilehash: fc8161ea29da92f5dcc2e76f956f3fecd6140acc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527724"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Puede mostrar datos en formularios Windows Forms <xref:System.Windows.Forms.DataGrid> control en tablas y columnas mediante la creación de **DataGridTableStyle** objetos y agregándolos a la **GridTableStylesCollection** objeto, que es acceso a través de la <xref:System.Windows.Forms.DataGrid> del control **TableStyles** propiedad. Cada estilo de tabla muestra el contenido de la tabla de datos se haya especificado en el **DataGridTableStyle** del objeto **MappingName** propiedad. De forma predeterminada, un estilo de tabla sin estilos de columna especificados mostrará todas las columnas de esa tabla de datos. Puede restringir las columnas de la tabla que aparecen agregando **DataGridColumnStyle** objetos a la **GridColumnStylesCollection** objeto, que se obtiene acceso a través de la  **GridColumnStyles** propiedad de cada **DataGridTableStyle** objeto.  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>Para agregar una tabla y una columna a un control DataGrid mediante programación  
  
1.  Para mostrar los datos en la tabla, debe enlazar primero el <xref:System.Windows.Forms.DataGrid> control a un conjunto de datos. Para obtener más información, consulte [Cómo: enlazar el DataGrid Control de formularios Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
    > [!CAUTION]
    >  Cuando especifique estilos de columna mediante programación, cree siempre **DataGridColumnStyle** objetos y agréguelos a la **GridColumnStylesCollection** objeto antes de agregar  **DataGridTableStyle** objetos a la **GridTableStylesCollection** objeto. Cuando se agrega vacío **DataGridTableStyle** objeto a la colección, **DataGridColumnStyle** objetos se generan automáticamente para usted. Por lo tanto, se producirá una excepción si intenta agregar nuevos **DataGridColumnStyle** objetos con duplicado **MappingName** valores a la **GridColumnStylesCollection**objeto.  
  
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
  
3.  Declare un nuevo estilo de columna y establezca su nombre de la asignación y otras propiedades.  
  
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
  
4.  Llame a la **agregar** método de la **GridColumnStylesCollection** objeto que se va a agregar la columna en el estilo de tabla  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  Llame a la **agregar** método de la **GridTableStylesCollection** va a agregar el estilo de tabla a la cuadrícula de datos.  
  
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
 [DataGrid (control)](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
