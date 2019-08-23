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
ms.openlocfilehash: 99acef0a7b29228ddf0406352ff5a88b77294b00
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966669"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Procedimiento para dar formato al control DataGrid de formularios Windows Forms
> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Aplicar distintos colores a varias partes de un <xref:System.Windows.Forms.DataGrid> control puede ayudar a facilitar la lectura y la interpretación de la información. El color se puede aplicar a filas y columnas. Las filas y columnas también se pueden ocultar o mostrar a su discreción.  
  
 Hay tres aspectos básicos del formato del <xref:System.Windows.Forms.DataGrid> control. Puede establecer propiedades para establecer un estilo predeterminado en el que se muestran los datos. A partir de esa base, puede personalizar la forma en que se muestran ciertas tablas en tiempo de ejecución. Por último, puede modificar las columnas que se muestran en la cuadrícula de datos, así como los colores y otros formatos que se muestran.  
  
 Como paso inicial para dar formato a una cuadrícula de datos, puede establecer las propiedades del <xref:System.Windows.Forms.DataGrid> mismo. Estas opciones de color y formato forman una base de la que puede realizar cambios en función de las tablas de datos y las columnas que se muestran.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Para establecer un estilo predeterminado para el control DataGrid  
  
1. Establezca las siguientes propiedades según corresponda:  
  
    |Propiedad|DESCRIPCIÓN|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|La <xref:System.Windows.Forms.DataGrid.BackColor%2A> propiedad define el color de las filas pares de la cuadrícula. Cuando se establece la <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> propiedad en un color diferente, todas las demás filas se establecen en este nuevo color (filas 1, 3, 5, etc.).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Color de fondo de las filas pares de la cuadrícula (filas 0, 2, 4, 6, etc.).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Mientras que <xref:System.Windows.Forms.DataGrid.BackColor%2A> las <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> propiedades y determinan el color de las filas de <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> la cuadrícula, la propiedad determina el color del área nonrow, que solo está visible cuando la cuadrícula se desplaza hasta la parte inferior o si solo hay unas cuantas filas contenidas en la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Estilo de borde de la cuadrícula, uno de <xref:System.Windows.Forms.BorderStyle> los valores de enumeración.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Color de fondo del título de la ventana de la cuadrícula que aparece justo encima de la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Fuente del título en la parte superior de la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Color de fondo del título de la ventana de la cuadrícula.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Fuente utilizada para mostrar el texto en la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Color de la fuente que muestran los datos de las filas de la cuadrícula de datos.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Color de las líneas de cuadrícula de la cuadrícula de datos.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Estilo de las líneas que separan las celdas de la cuadrícula, uno de <xref:System.Windows.Forms.DataGridLineStyle> los valores de enumeración.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Color de fondo de los encabezados de fila y de columna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Fuente utilizada para los encabezados de columna.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Color de primer plano de los encabezados de columna de la cuadrícula, incluido el texto del encabezado de columna y los glifos más/menos (para expandir las filas cuando se muestran varias tablas relacionadas).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Color del texto de todos los vínculos de la cuadrícula de datos, incluidos los vínculos a las tablas secundarias, el nombre de la relación, etc.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|En una tabla secundaria, es el color de fondo de las filas primarias.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|En una tabla secundaria, es el color de primer plano de las filas primarias.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Determina si los nombres de tabla y de columna se muestran en la fila primaria, por medio <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> de la enumeración.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Ancho predeterminado (en píxeles) de las columnas de la cuadrícula. Establezca esta propiedad antes de restablecer las <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedades <xref:System.Windows.Forms.DataGrid.DataMember%2A> y (ya sea por separado o a través <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> del método) o la propiedad no tendrá ningún efecto.<br /><br /> La propiedad no se puede establecer en un valor menor que 0.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Alto de fila (en píxeles) de las filas de la cuadrícula. Establezca esta propiedad antes de restablecer las <xref:System.Windows.Forms.DataGrid.DataSource%2A> propiedades <xref:System.Windows.Forms.DataGrid.DataMember%2A> y (ya sea por separado o a través <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> del método) o la propiedad no tendrá ningún efecto.<br /><br /> La propiedad no se puede establecer en un valor menor que 0.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Ancho de los encabezados de fila de la cuadrícula.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Cuando se selecciona una fila o celda, este es el color de fondo.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Cuando se selecciona una fila o celda, este es el color de primer plano.|  
  
    > [!NOTE]
    > Tenga en cuenta que al personalizar los colores de los controles, es posible hacer que el control sea inaccesible, debido a una opción de color deficiente (por ejemplo, rojo y verde). Use los colores disponibles en la paleta de **colores del sistema** para evitar este problema.  
  
     En los procedimientos siguientes se supone que el <xref:System.Windows.Forms.DataGrid> formulario tiene un control enlazado a una tabla de datos. Para obtener más información, vea [enlazar el control DataGrid de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>Para establecer el estilo de tabla y columna de una tabla de datos mediante programación  
  
1. Cree un nuevo estilo de tabla y establezca sus propiedades.  
  
2. Cree un estilo de columna y establezca sus propiedades.  
  
3. Agregue el estilo de columna a la colección de estilos de columna del estilo de tabla.  
  
4. Agregue el estilo de tabla a la colección de estilos de tabla de la cuadrícula de datos.  
  
5. En el ejemplo siguiente, cree una instancia de un nuevo <xref:System.Windows.Forms.DataGridTableStyle> y establezca su <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> propiedad.  
  
6. Cree una nueva instancia de **GridColumnStyle** y establezca su propiedad **MappingName** (y otras propiedades de presentación y diseño).  
  
7. Repita los pasos del 2 al 6 para cada estilo de columna que desee crear.  
  
     En el ejemplo siguiente se muestra cómo <xref:System.Windows.Forms.DataGridTextBoxColumn> se crea un, porque se muestra un nombre en la columna. Además, se agrega el estilo <xref:System.Windows.Forms.GridColumnStylesCollection> de columna al del estilo de tabla y se agrega el estilo <xref:System.Windows.Forms.GridTableStylesCollection> de tabla al de la cuadrícula de datos.  
  
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
- [Procedimientos: Eliminar u ocultar columnas en el control DataGrid de Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid (control)](datagrid-control-windows-forms.md)
