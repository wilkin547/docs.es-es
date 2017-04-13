---
title: "C&#243;mo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "columnas [Windows Forms], eliminar de cuadrículas de datos"
  - "columnas [Windows Forms], ocultar"
  - "cuadrículas de datos, eliminar columnas"
  - "cuadrículas de datos, ocultar columnas"
  - "DataGrid (control) [Windows Forms], eliminar columnas"
  - "DataGrid (control) [Windows Forms], ocultar columnas"
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>, este control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Para eliminar u ocultar columnas del control <xref:System.Windows.Forms.DataGrid> de los formularios Windows Forms mediante programación, puede utilizar los métodos y las propiedades de los objetos <xref:System.Windows.Forms.GridColumnStylesCollection> y <xref:System.Windows.Forms.DataGridColumnStyle>, que son miembros de la clase <xref:System.Windows.Forms.DataGridTableStyle>.  
  
 Las columnas eliminadas u ocultas siguen existiendo en el origen de datos al que está enlazada la cuadrícula, y se puede obtener acceso a ellas mediante programación.  No son visibles sólo en la cuadrícula de datos.  
  
> [!NOTE]
>  Si la aplicación no obtiene acceso a determinadas columnas de datos y no desea mostrarlas en la cuadrícula de datos, probablemente no será necesario incluirlas en el origen de datos en primer lugar.  
  
### Para eliminar una columna del control DataGrid mediante programación  
  
1.  En el área de declaraciones del formulario, declare una instancia nueva de la clase <xref:System.Windows.Forms.DataGridTableStyle>.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=fullName> en la tabla del origen de datos a la que desee aplicar el estilo.  En el ejemplo siguiente se utiliza la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=fullName> y se da por supuesto que esta propiedad está ya definida.  
  
3.  Agregue el nuevo objeto <xref:System.Windows.Forms.DataGridTableStyle> a la colección de estilos de tabla de la cuadrícula de datos.  
  
4.  Llame al método <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> de la colección <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> del control <xref:System.Windows.Forms.DataGrid> y especifique el índice de la columna que desea eliminar.  
  
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
  
### Para ocultar una columna en el control DataGrid mediante programación  
  
1.  En el área de declaraciones del formulario, declare una instancia nueva de la clase <xref:System.Windows.Forms.DataGridTableStyle>.  
  
2.  Defina la propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> de <xref:System.Windows.Forms.DataGridTableStyle> con la tabla del origen de datos a la que desee aplicar el estilo.  En el ejemplo siguiente se utiliza la propiedad <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=fullName> y se da por supuesto que esta propiedad está ya definida.  
  
3.  Agregue el nuevo objeto <xref:System.Windows.Forms.DataGridTableStyle> a la colección de estilos de tabla de la cuadrícula de datos.  
  
4.  Oculte la columna estableciendo la propiedad `Width`  en 0, especificando el índice de columna de la columna que desea ocultar.  
  
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
  
## Vea también  
 [Cómo: Cambiar los datos mostrados en tiempo de ejecución en el control DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)   
 [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)