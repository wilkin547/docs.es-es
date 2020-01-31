---
title: Eliminar u ocultar columnas en el control DataGrid
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
ms.openlocfilehash: c730be934e9b978bdaf09bc7e668b4318077fba5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743299"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms
> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Puede eliminar u ocultar columnas mediante programación en el control Windows Forms <xref:System.Windows.Forms.DataGrid> mediante las propiedades y los métodos de los objetos <xref:System.Windows.Forms.GridColumnStylesCollection> y <xref:System.Windows.Forms.DataGridColumnStyle> (que son miembros de la clase <xref:System.Windows.Forms.DataGridTableStyle>).  
  
 Las columnas eliminadas u ocultas todavía existen en el origen de datos al que está enlazada la cuadrícula y se puede seguir accediendo a ella mediante programación. Ya no están visibles en el control DataGrid.  
  
> [!NOTE]
> Si la aplicación no tiene acceso a determinadas columnas de datos y no desea que se muestren en el control DataGrid, es probable que no sea necesario incluirlas en el origen de datos en primer lugar.  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>Para eliminar una columna de DataGrid mediante programación  
  
1. En el área declaraciones del formulario, declare una nueva instancia de la clase <xref:System.Windows.Forms.DataGridTableStyle>.  
  
2. Establezca la propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> en la tabla del origen de datos a la que desea aplicar el estilo. En el ejemplo siguiente se usa la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>, que supone que ya está establecida.  
  
3. Agregue el nuevo objeto <xref:System.Windows.Forms.DataGridTableStyle> a la colección de estilos de tabla de DataGrid.  
  
4. Llame al método <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> de la colección <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> del <xref:System.Windows.Forms.DataGrid>, especificando el índice de columna de la columna que se va a eliminar.  
  
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
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>Para ocultar una columna en el control DataGrid mediante programación  
  
1. En el área declaraciones del formulario, declare una nueva instancia de la clase <xref:System.Windows.Forms.DataGridTableStyle>.  
  
2. Establezca la propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> del <xref:System.Windows.Forms.DataGridTableStyle> en la tabla del origen de datos a la que desea aplicar el estilo. En el ejemplo de código siguiente se usa la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>, que supone que ya está establecida.  
  
3. Agregue el nuevo objeto <xref:System.Windows.Forms.DataGridTableStyle> a la colección de estilos de tabla de DataGrid.  
  
4. Oculte la columna estableciendo su `Width` propiedad en 0, especificando el índice de columna de la columna que se va a ocultar.  
  
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

- [Cómo: Cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
