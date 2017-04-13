---
title: "C&#243;mo: Dar formato al control DataGrid de formularios Windows Forms | Microsoft Docs"
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
  - "colores, aplicar a controles DataGrid"
  - "columnas [Windows Forms], DataGrid (control)"
  - "columnas [Windows Forms], aplicar formato en un control DataGrid"
  - "DataGrid (control) [Windows Forms], estilos predeterminados"
  - "DataGrid (control) [Windows Forms], aplicar formato"
  - "dar formato [Windows Forms]"
  - "tablas [Windows Forms], aplicar formato en un control DataGrid"
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Dar formato al control DataGrid de formularios Windows Forms
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>, este control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Aplicar diferentes colores a diversas partes de un control <xref:System.Windows.Forms.DataGrid> puede facilitar la lectura e interpretación de la información que contiene.  Se puede aplicar color a filas y columnas.  Las filas y columnas también se pueden ocultar y mostrar a discreción.  
  
 Hay tres aspectos básicos del formato del control <xref:System.Windows.Forms.DataGrid>.  Puede definir propiedades para establecer un estilo predeterminado con el que mostrar los datos.  Partiendo de esta base, puede personalizar el modo en que se muestran determinadas tablas en tiempo de ejecución.  Finalmente, puede modificar las columnas que se muestran en la cuadrícula de datos, así como los colores y otros aspectos del formato que se muestran.  
  
 Como paso inicial para dar formato a una cuadrícula de datos, se pueden establecer las propiedades del propio control <xref:System.Windows.Forms.DataGrid>.  Estas opciones de color y formato forman una base a partir de la cual puede realizar cambios dependiendo de las tablas de datos y columnas mostradas.  
  
### Para establecer un estilo predeterminado para el control DataGrid  
  
1.  Establezca las siguientes propiedades según corresponda:  
  
    |Propiedad.|Descripción|  
    |----------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|La propiedad <xref:System.Windows.Forms.DataGrid.BackColor%2A> define el color de las filas pares de la cuadrícula.  Cuando se define la propiedad <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> en un color diferente, las filas alternas toman este nuevo color \(filas 1, 3, 5, etc.\).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Color de fondo de las filas pares de la cuadrícula \(filas 0, 2, 4, 6 y etc.\).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Mientras que las propiedades <xref:System.Windows.Forms.DataGrid.BackColor%2A> y <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> determinan el color de las filas de la cuadrícula, la propiedad <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> determina el color del área que no corresponde a las filas, que sólo está visible cuando la cuadrícula se desplaza hasta el final, o si la cuadrícula contiene sólo unas pocas filas.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Estilo de borde de la cuadrícula, uno de los valores de la enumeración <xref:System.Windows.Forms.BorderStyle>.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Color de fondo de la leyenda de la ventana de la cuadrícula que aparece inmediatamente encima de la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Fuente de la leyenda de la parte superior de la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Color de fondo de la leyenda de la ventana de la cuadrícula.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Fuente utilizada para mostrar el texto en la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Color de la fuente que muestran los datos de las filas de la cuadrícula de datos.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Color de las líneas de la cuadrícula de datos.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Estilo de las líneas que separan las celdas de la cuadrícula, uno de los valores de la enumeración <xref:System.Windows.Forms.DataGridLineStyle>.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Color de fondo de los encabezados de fila y columna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Fuente utilizada para los encabezados de columna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Color de primer plano de los encabezados de columna de la cuadrícula, incluido el texto del encabezado de columna y los glifos más y menos \(para expandir las filas cuando se muestren varias tablas relacionadas\).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Color del texto de todos los vínculos de la cuadrícula de datos, incluidos los vínculos a tablas secundarias, el nombre de la relación, etc.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|En una tabla secundaria, éste es el color de fondo de las filas primaria.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|En una tabla secundaria, éste es el color de primer plano de las filas primaria.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Determina si los nombres de tabla y columna se muestran en la fila primaria, por medio de la enumeración <xref:System.Windows.Forms.DataGridParentRowsLabelStyle>.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Ancho predeterminado \(en píxeles\) de las columnas de la cuadrícula.  Defina esta propiedad antes de restablecer las propiedades <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> \(por separado o con el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\), o la propiedad no tendrá efecto.<br /><br /> No se puede definir la propiedad con un valor inferior a 0.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Alto de fila \(en píxeles\) de las filas de la cuadrícula.  Defina esta propiedad antes de restablecer las propiedades <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> \(por separado o con el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\), o la propiedad no tendrá efecto.<br /><br /> No se puede definir la propiedad con un valor inferior a 0.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Ancho de los encabezados de fila de la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Cuando se selecciona una fila o celda, éste es el color de fondo.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Cuando se selecciona una fila o celda, éste es el color de primer plano.|  
  
    > [!NOTE]
    >  Tenga en cuenta que, al personalizar los colores de los controles, es posible que el control quede inaccesible, debido a una elección de color deficiente \(por ejemplo, rojo y verde\).  Utilice los colores disponibles en la paleta **Colores del sistema** para evitar este problema.  
  
     Los procedimientos siguientes suponen que el formulario tiene un control <xref:System.Windows.Forms.DataGrid> enlazado a una tabla de datos.  Para obtener más información, vea [Enlazar el control DataGrid de formularios Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### Para definir el estilo de tabla y columna de una tabla de datos mediante programación  
  
1.  Cree un estilo de tabla nuevo y defina sus propiedades.  
  
2.  Cree un estilo de columna nuevo y defina sus propiedades.  
  
3.  Agregue el estilo de columna a la colección de estilos de columna del estilo de tabla.  
  
4.  Agregue el estilo de tabla a la colección de estilos de tabla de la cuadrícula de datos.  
  
5.  En el ejemplo siguiente, cree una instancia de un nuevo objeto <xref:System.Windows.Forms.DataGridTableStyle> y establezca su propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>.  
  
6.  Cree una instancia nueva de un objeto **GridColumnStyle** y defina su propiedad **MappingName** \(y otras propiedades de diseño y presentación\).  
  
7.  Repita los pasos 2 a 6 para cada estilo de columna que desee crear.  
  
     El ejemplo siguiente muestra cómo se crea un objeto <xref:System.Windows.Forms.DataGridTextBoxColumn>, porque se va a mostrar un nombre en la columna.  De manera adicional, agregue el estilo de columna a la colección <xref:System.Windows.Forms.GridColumnStylesCollection> del estilo de tabla y agregue el estilo de tabla a la colección <xref:System.Windows.Forms.GridTableStylesCollection> de la cuadrícula de datos.  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName   
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName   
       ' to the name of a DataColumn in the DataTable.   
       ' Set the HeaderText and Width properties.   
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to   
       ' the GridTableStylesCollection.   
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName   
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName   
       // to the name of a DataColumn in the DataTable.   
       // Set the HeaderText and Width properties.   
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to   
       // the GridTableStylesCollection.   
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName   
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName   
          // to the name of a DataColumn in the DataTable.   
          // Set the HeaderText and Width properties.   
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to   
          // the GridTableStylesCollection.   
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.GridTableStylesCollection>   
 <xref:System.Windows.Forms.GridColumnStylesCollection>   
 <xref:System.Windows.Forms.DataGrid>   
 [Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [Control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)