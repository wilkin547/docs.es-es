---
title: "C&#243;mo: Agregar tablas y columnas al control DataGrid de Windows Forms | Microsoft Docs"
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
  - "columnas [Windows Forms], agregar a un control DataGrid"
  - "DataGrid (control) [Windows Forms], agregar tablas y columnas"
  - "tablas [Windows Forms], agregar a un control DataGrid"
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Agregar tablas y columnas al control DataGrid de Windows Forms
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>, este control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Para mostrar datos en el control <xref:System.Windows.Forms.DataGrid> de formularios Windows Forms en formato de tablas y columnas, puede crear objetos **DataGridTableStyle** y agregarlos al objeto **GridTableStylesCollection**, al que se obtiene acceso a través de la propiedad **TableStyles** del control <xref:System.Windows.Forms.DataGrid>.  Cada tabla muestra el contenido de la tabla de datos que se haya especificado en la propiedad **MappingName** del objeto **DataGridTableStyle**.  De forma predeterminada, un estilo de tabla sin estilos de columna especificados mostrará todas las columnas que contenga la tabla de datos.  Para restringir las columnas de la tabla que aparecen puede agregar objetos **DataGridColumnStyle** al objeto **GridColumnStylesCollection**, al que se tiene acceso mediante la propiedad **GridColumnStyles** de cada objeto **DataGridTableStyle**.  
  
### Para agregar una tabla y una columna a un control DataGrid mediante programación  
  
1.  Para mostrar los datos de la tabla, deberá enlazar en primer lugar el control <xref:System.Windows.Forms.DataGrid> a un conjunto de datos.  Para obtener más información, vea [Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
    > [!CAUTION]
    >  Cuando especifique estilos de columna mediante programación, cree siempre objetos **DataGridColumnStyle** y agréguelos al objeto **GridColumnStylesCollection** antes de agregar objetos **DataGridTableStyle** al objeto **GridTableStylesCollection**.  Cuando agregue un objeto **DataGridTableStyle** vacío a la colección, se crearán automáticamente objetos **DataGridColumnStyle**.  En consecuencia, se producirá una excepción si intenta agregar nuevos objetos **DataGridColumnStyle** con valores **MappingName** duplicados al objeto **GridColumnStylesCollection**.  
  
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
  
3.  Declare un nuevo estilo de columna y establezca su nombre de asignación y demás propiedades.  
  
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
  
4.  Llame al método **Add** del objeto **GridColumnStylesCollection** para agregar la columna al estilo de tabla.  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  Llame al método **Add** del objeto **GridTableStylesCollection** para agregar el estilo de tabla a la cuadrícula de datos.  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## Vea también  
 [Control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)