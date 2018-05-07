---
title: 'Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: 6541ffff1149e5df13c43ee392ffa8b221c8407d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Mediante programación puede eliminar u ocultar columnas en los formularios Windows Forms <xref:System.Windows.Forms.DataGrid> control mediante el uso de las propiedades y métodos de la <xref:System.Windows.Forms.GridColumnStylesCollection> y <xref:System.Windows.Forms.DataGridColumnStyle> objetos (que son miembros de la <xref:System.Windows.Forms.DataGridTableStyle> clase).  
  
 Las columnas eliminadas u ocultas siguen existan en el origen de datos se enlaza a la cuadrícula y todavía son accesibles mediante programación. Simplemente ya no son visibles en la cuadrícula de datos.  
  
> [!NOTE]
>  Si la aplicación no tiene acceso a determinadas columnas de datos y no desea que se muestren en la cuadrícula de datos, probablemente no es necesario incluir en el origen de datos en primer lugar.  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>Para eliminar una columna de la cuadrícula de datos mediante programación  
  
1.  En el área de declaraciones del formulario, declare una nueva instancia de la <xref:System.Windows.Forms.DataGridTableStyle> clase.  
  
2.  Establecer el <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> propiedad a la tabla de origen de datos que desea aplicar el estilo. En el ejemplo siguiente se usa el <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> propiedad, que se supone que ya se ha establecido.  
  
3.  Agregue el nuevo <xref:System.Windows.Forms.DataGridTableStyle> objeto a la colección de estilos de tabla del control datagrid.  
  
4.  Llame a la <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> método de la <xref:System.Windows.Forms.DataGrid>del <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> colección, que especifica el índice de columna de la columna que se va a eliminar.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>Para ocultar una columna en la cuadrícula de datos mediante programación  
  
1.  En el área de declaraciones del formulario, declare una nueva instancia de la <xref:System.Windows.Forms.DataGridTableStyle> clase.  
  
2.  Establecer el <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> propiedad de la <xref:System.Windows.Forms.DataGridTableStyle> a la tabla de origen de datos que desea aplicar el estilo. El siguiente ejemplo de código utiliza el <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> propiedad, que se supone que ya se ha establecido.  
  
3.  Agregue el nuevo <xref:System.Windows.Forms.DataGridTableStyle> objeto a la colección de estilos de tabla del control datagrid.  
  
4.  Ocultar la columna estableciendo su `Width` propiedad en 0, que especifica el índice de columna de la columna que desea ocultar.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Cómo: Cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)  
 [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
