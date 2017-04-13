---
title: "C&#243;mo: Dar formato al control DataGrid de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "columnas [Windows Forms], controles DataGrid"
  - "DataGrid (control) [Windows Forms], estilos predeterminados"
  - "DataGrid (control) [Windows Forms], aplicar formato"
  - "dar formato [Windows Forms]"
  - "tablas [Windows Forms], aplicar formato en un control DataGrid"
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Dar formato al control DataGrid de formularios Windows Forms mediante el Dise&#241;ador
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>, este control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Aplicar diferentes colores a diversas partes de un control <xref:System.Windows.Forms.DataGrid> puede facilitar la lectura e interpretación de la información que contiene.  Se puede aplicar color a filas y columnas.  Las filas y columnas también se pueden ocultar y mostrar a discreción.  
  
 Hay tres aspectos básicos del formato del control <xref:System.Windows.Forms.DataGrid>:  
  
-   Puede definir propiedades para establecer un estilo predeterminado con el que mostrar los datos.  
  
-   Partiendo de esta base, puede personalizar el modo en que se muestran determinadas tablas en tiempo de ejecución.  
  
-   Finalmente, puede modificar las columnas que se muestran en la cuadrícula de datos, así como los colores y otros aspectos del formato que se muestran.  
  
 Como paso inicial para dar formato a una cuadrícula de datos, se pueden establecer las propiedades del propio control <xref:System.Windows.Forms.DataGrid>.  Estas opciones de color y formato forman una base a partir de la cual puede realizar cambios dependiendo de las tablas de datos y columnas mostradas.  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.DataGrid>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  En [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], el control <xref:System.Windows.Forms.DataGrid> no está en el **Cuadro de herramientas** de manera predeterminada.  Para obtener más información, vea [How to: Add Items to the Toolbox](http://msdn.microsoft.com/es-es/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para establecer un estilo predeterminado para el control DataGrid  
  
1.  Seleccione el control <xref:System.Windows.Forms.DataGrid>.  
  
2.  En la ventana **Propiedades**, defina las propiedades siguientes, según corresponda.  
  
    |Propiedad.|Descripción|  
    |----------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|La propiedad `BackColor` define el color de las filas pares de la cuadrícula.  Cuando se define la propiedad <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> en un color diferente, las filas alternas toman este nuevo color \(filas 1, 3, 5, etc.\).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Color de fondo de las filas pares de la cuadrícula \(filas 0, 2, 4, 6 y etc.\).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Mientras que las propiedades <xref:System.Windows.Forms.DataGrid.BackColor%2A> y <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> determinan el color de las filas de la cuadrícula, la propiedad <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> determina el color del área fuera del área de la fila, que sólo está visible cuando la cuadrícula se desplaza hasta el final, o si la cuadrícula contiene sólo unas pocas filas.|  
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
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Color de primer plano de los encabezados de columna de la cuadrícula, incluido el texto del encabezado de columna y los glifos de signo más \(\+\) y menos \(\-\) que expanden y contraen las filas cuando se muestren varias tablas relacionadas.|  
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
    >  Al personalizar los colores de los controles, es posible que el control quede inaccesible, debido a una elección de color deficiente \(por ejemplo, rojo y verde\).  Utilice los colores disponibles en la paleta **Colores del sistema** para evitar este problema.  
  
     El procedimiento siguiente requiere un control <xref:System.Windows.Forms.DataGrid> enlazado a una tabla de datos.  Para obtener más información, vea [Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### Para definir el estilo de tabla y columna de una tabla de datos en tiempo de diseño  
  
1.  Seleccione el control <xref:System.Windows.Forms.DataGrid> del formulario.  
  
2.  En la ventana **Propiedades**, seleccione la propiedad <xref:System.Windows.Forms.DataGrid.TableStyles%2A> y haga clic en el botón de **puntos suspensivos** \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\).  
  
3.  En el cuadro de diálogo **Editor de la colección DataGridTableStyle**, haga clic en **Agregar** para agregar un estilo de tabla a la colección.  
  
     Con el cuadro de diálogo **Editor de la colección DataGridTableStyle**, puede agregar y quitar estilos de tabla, definir propiedades de presentación y diseño, y establecer el nombre de asignación para los estilos de tabla.  
  
4.  Establezca la propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> en el nombre de asignación para cada estilo de tabla.  
  
     El nombre de asignación se utiliza para especificar el estilo de tabla que se debe utilizar con cada tabla.  
  
5.  En el **Editor de la colección DataGridTableStyle**, seleccione la propiedad <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> y haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\).  
  
6.  En el cuadro de diálogo **Editor de la colección DataGridColumnStyle**, agregue estilos de columna al estilo de tabla que ha creado.  
  
     Con el **Editor de la colección DataGridColumnStyle** puede agregar y quitar estilos de columna, definir propiedades de presentación y diseño, y establecer el nombre de asignación y las cadenas de formato para las columnas de datos.  
  
    > [!NOTE]
    >  Para obtener más información sobre cadenas de formato, vea [Aplicar formato a tipos](../../../../docs/standard/base-types/formatting-types.md).  
  
## Vea también  
 <xref:System.Windows.Forms.GridTableStylesCollection>   
 <xref:System.Windows.Forms.GridColumnStylesCollection>   
 <xref:System.Windows.Forms.DataGrid>   
 [Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [Control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)