---
title: Format DataGrid Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: 180f837c7d60f49af880faefc05da262be061d12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182145"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Cómo: Dar formato al control DataGrid de formularios Windows Forms
> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Aplicar diferentes colores a <xref:System.Windows.Forms.DataGrid> varias partes de un control puede ayudar a que la información en él sea más fácil de leer e interpretar. El color se puede aplicar a filas y columnas. Las filas y columnas también se pueden ocultar o mostrar a su discreción.  
  
 Hay tres aspectos básicos <xref:System.Windows.Forms.DataGrid> para dar formato al control. Puede establecer propiedades para establecer un estilo predeterminado en el que se muestran los datos. Desde esa base, puede personalizar la forma en que se muestran determinadas tablas en tiempo de ejecución. Por último, puede modificar qué columnas se muestran en la cuadrícula de datos, así como los colores y otro formato que se muestra.  
  
 Como paso inicial para dar formato a una cuadrícula <xref:System.Windows.Forms.DataGrid> de datos, puede establecer las propiedades del propio. Estas opciones de color y formato forman una base desde la que puede realizar cambios en función de las tablas de datos y las columnas que se muestran.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Para establecer un estilo predeterminado para el DataGrid control  
  
1. Establezca las siguientes propiedades según corresponda:  
  
    |Propiedad|Descripción|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|La <xref:System.Windows.Forms.DataGrid.BackColor%2A> propiedad define el color de las filas par numeradas de la cuadrícula. Cuando se <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> establece la propiedad en un color diferente, cada otra fila se establece en este nuevo color (filas 1, 3, 5, etc.).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|El color de fondo de las filas par de la cuadrícula (filas 0, 2, 4, 6, etc.).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Mientras <xref:System.Windows.Forms.DataGrid.BackColor%2A> que <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> las propiedades y determina el color <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> de las filas de la cuadrícula, la propiedad determina el color del área no fila, que solo es visible cuando la cuadrícula se desplaza a la parte inferior, o si solo unas pocas filas están contenidas en la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|El estilo de borde de <xref:System.Windows.Forms.BorderStyle> la cuadrícula, uno de los valores de enumeración.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|El color de fondo del título de la ventana de la cuadrícula que aparece inmediatamente encima de la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|La fuente del título en la parte superior de la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|El color de fondo del título de la ventana de la cuadrícula.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|La fuente utilizada para mostrar el texto en la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|El color de la fuente mostrada por los datos en las filas de la cuadrícula de datos.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|El color de las líneas de cuadrícula de la cuadrícula de datos.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|El estilo de las líneas que separan las <xref:System.Windows.Forms.DataGridLineStyle> celdas de la cuadrícula, uno de los valores de enumeración.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|El color de fondo de los encabezados de fila y columna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|La fuente utilizada para los encabezados de columna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|El color de primer plano de los encabezados de columna de la cuadrícula, incluido el texto del encabezado de columna y los glifos más/menos (para expandir filas cuando se muestran varias tablas relacionadas).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|El color del texto de todos los vínculos de la cuadrícula de datos, incluidos los vínculos a tablas secundarias, el nombre de la relación, etc.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|En una tabla secundaria, este es el color de fondo de las filas primarias.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|En una tabla secundaria, este es el color de primer plano de las filas primarias.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Determina si los nombres de tabla y columna se muestran <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> en la fila primaria, mediante la enumeración.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Ancho predeterminado (en píxeles) de las columnas de la cuadrícula. Establezca esta propiedad antes <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> de restablecer las propiedades (ya sea por separado o a través del <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método), o la propiedad no tendrá ningún efecto.<br /><br /> La propiedad no se puede establecer en un valor menor que 0.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Altura de fila (en píxeles) de las filas de la cuadrícula. Establezca esta propiedad antes <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> de restablecer las propiedades (ya sea por separado o a través del <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método), o la propiedad no tendrá ningún efecto.<br /><br /> La propiedad no se puede establecer en un valor menor que 0.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|El ancho de los encabezados de fila de la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Cuando se selecciona una fila o celda, este es el color de fondo.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Cuando se selecciona una fila o celda, este es el color de primer plano.|  
  
    > [!NOTE]
    > Tenga en cuenta, al personalizar los colores de los controles, que es posible hacer el control inaccesible, debido a la mala elección de color (por ejemplo, rojo y verde). Utilice los colores disponibles en la paleta **Colores del** sistema para evitar este problema.  
  
     En los procedimientos siguientes <xref:System.Windows.Forms.DataGrid> se supone que el formulario tiene un control enlazado a una tabla de datos. Para obtener más información, vea [Enlazar el control DataGrid de formularios Windows Forms a un origen](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)de datos .  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>Para establecer el estilo de tabla y columna de una tabla de datos mediante programación  
  
1. Cree un nuevo estilo de tabla y establezca sus propiedades.  
  
2. Cree un estilo de columna y establezca sus propiedades.  
  
3. Agregue el estilo de columna a la colección de estilos de columna del estilo de tabla.  
  
4. Agregue el estilo de tabla a la colección de estilos de tabla de la cuadrícula de datos.  
  
5. En el ejemplo siguiente, cree <xref:System.Windows.Forms.DataGridTableStyle> una instancia <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> de un nuevo y establezca su propiedad.  
  
6. Cree una nueva instancia de un **GridColumnStyle** y establezca su **MappingName** (y algunas otras propiedades de diseño y presentación).  
  
7. Repita los pasos del 2 al 6 para cada estilo de columna que desee crear.  
  
     En el ejemplo siguiente <xref:System.Windows.Forms.DataGridTextBoxColumn> se muestra cómo se crea a, porque se va a mostrar un nombre en la columna. Además, agregue el estilo <xref:System.Windows.Forms.GridColumnStylesCollection> de columna al estilo de tabla <xref:System.Windows.Forms.GridTableStylesCollection> y agregue el estilo de tabla a la cuadrícula de datos.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid (control)](datagrid-control-windows-forms.md)
