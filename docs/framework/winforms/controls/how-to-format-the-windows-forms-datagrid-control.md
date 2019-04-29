---
title: Procedimiento para dar formato al control DataGrid de formularios Windows Forms
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
ms.openlocfilehash: 8e5c41d6f146e6abef8d7670e6191b587ac86c92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941367"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Procedimiento para dar formato al control DataGrid de formularios Windows Forms
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Aplicar colores diferentes para distintas partes de un <xref:System.Windows.Forms.DataGrid> control puede ayudar a que la información sea más fácil leer e interpretar. Color puede aplicarse a las filas y columnas. Las filas y columnas también se oculta o se muestra a su entera discreción.  
  
 Hay tres aspectos básicos del formato el <xref:System.Windows.Forms.DataGrid> control. Puede establecer propiedades para establecer un estilo predeterminado en el que se muestran los datos. Desde esa base, a continuación, puede personalizar la manera en que se muestren determinadas tablas en tiempo de ejecución. Por último, puede modificar las columnas que se muestran en la cuadrícula de datos, así como los colores y otras opciones de formato se muestra.  
  
 Como paso inicial para dar formato a una cuadrícula de datos, puede establecer las propiedades de la <xref:System.Windows.Forms.DataGrid> propio. Estas opciones de color y el formato forman una base desde la que puede realizar, a continuación, cambia en función de las tablas de datos y las columnas mostradas.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Para establecer un estilo predeterminado para el control DataGrid  
  
1. Establezca las propiedades siguientes según corresponda:  
  
    |Propiedad|Descripción|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|El <xref:System.Windows.Forms.DataGrid.BackColor%2A> propiedad define el color de las filas impares de la cuadrícula. Al establecer el <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> propiedad a un color diferente, todas las demás filas se establece en este nuevo color (filas 1, 3, 5 y así sucesivamente).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|El color de fondo de las filas impares de la cuadrícula (filas 0, 2, 4, 6 y así sucesivamente).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Mientras que la <xref:System.Windows.Forms.DataGrid.BackColor%2A> y <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> propiedades determinan el color de las filas de la cuadrícula, la <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> propiedad determina el color de la área que no, que solo está visible cuando la cuadrícula se desplaza hasta la parte inferior, o si sólo unas pocas filas se encuentran en la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Estilo de borde de la cuadrícula, uno de los <xref:System.Windows.Forms.BorderStyle> valores de enumeración.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|El color de fondo del título de ventana de la cuadrícula que aparece justo encima de la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|La fuente del título en la parte superior de la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|El color de fondo del título de ventana de la cuadrícula.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|La fuente utilizada para mostrar el texto en la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|El color de la fuente que aparecen en los datos de las filas de la cuadrícula de datos.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|El color de las líneas de cuadrícula de la cuadrícula de datos.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|El estilo de las líneas que separan las celdas de la cuadrícula, uno de los <xref:System.Windows.Forms.DataGridLineStyle> valores de enumeración.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|El color de fondo de los encabezados de fila y columna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|La fuente utilizada para los encabezados de columna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|El color de primer plano de los encabezados de columna de la cuadrícula, incluido el texto de encabezado de columna y los glifos más/menos (para expandir las filas cuando se muestran varias tablas relacionadas).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|El color del texto de todos los vínculos en la cuadrícula de datos, incluidos los vínculos a las tablas secundarias, el nombre de la relación y así sucesivamente.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|En una tabla secundaria, este es el color de fondo de las filas primarias.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|En una tabla secundaria, este es el color de primer plano de las filas primarias.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Determina si los nombres de tabla y columna se muestran en la fila primaria, por medio de la <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeración.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Ancho predeterminado (en píxeles) de las columnas de la cuadrícula. Establezca esta propiedad antes de restablecer la <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedades (ya sea por separado, o a través del <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método), o la propiedad no tiene ningún efecto.<br /><br /> No se puede establecer la propiedad en un valor menor que 0.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|El alto de fila (en píxeles) de filas en la cuadrícula. Establezca esta propiedad antes de restablecer la <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedades (ya sea por separado, o a través del <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método), o la propiedad no tiene ningún efecto.<br /><br /> No se puede establecer la propiedad en un valor menor que 0.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|El ancho de los encabezados de fila de la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Cuando se selecciona una celda o fila, este es el color de fondo.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Cuando se selecciona una celda o fila, este es el color de primer plano.|  
  
    > [!NOTE]
    >  Tenga en cuenta que, al personalizar los colores de los controles, que es posible que el control sea inaccesible debido a la elección de color deficiente (por ejemplo, rojo y verde). Utilice los colores disponibles en el **colores del sistema** paleta para evitar este problema.  
  
     Los procedimientos siguientes suponen que el formulario tiene un <xref:System.Windows.Forms.DataGrid> control enlazado a una tabla de datos. Para obtener más información, consulte [enlazar el DataGrid Control de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>Para establecer el estilo de tabla y columna de una tabla de datos mediante programación  
  
1. Cree un nuevo estilo de tabla y establezca sus propiedades.  
  
2. Cree un estilo de columna y establezca sus propiedades.  
  
3. Agregar el estilo de columna a la colección de estilos de columna del estilo de tabla.  
  
4. Agregar el estilo de tabla a la colección de estilos de tabla de la cuadrícula de datos.  
  
5. En el ejemplo siguiente, cree una instancia de un nuevo <xref:System.Windows.Forms.DataGridTableStyle> y establezca su <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> propiedad.  
  
6. Crear una nueva instancia de un **GridColumnStyle** y establezca su **MappingName** (y otras propiedades de diseño y presentación).  
  
7. Repita los pasos del 2 al 6 para cada estilo de columna que desea crear.  
  
     El ejemplo siguiente se muestra cómo un <xref:System.Windows.Forms.DataGridTextBoxColumn> se crea, porque es un nombre que se mostrará en la columna. Además, agrega el estilo de columna la <xref:System.Windows.Forms.GridColumnStylesCollection> del estilo de tabla, y agregar el estilo de tabla a la <xref:System.Windows.Forms.GridTableStylesCollection> de la cuadrícula de datos.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Cómo: Eliminar u ocultar columnas en el Control DataGrid de Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid (control)](datagrid-control-windows-forms.md)
