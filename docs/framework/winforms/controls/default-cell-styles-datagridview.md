---
title: "C&#243;mo: Establecer estilos de celdas y formatos de datos predeterminados en el control DataGridView de formularios Windows Forms mediante el dise&#241;ador | Microsoft Docs"
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
  - "celdas, establecer estilos"
  - "datos [Windows Forms], establecer formatos"
  - "formatos de datos"
  - "DataGridView (control) [Windows Forms], estilos de celda"
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Establecer estilos de celdas y formatos de datos predeterminados en el control DataGridView de formularios Windows Forms mediante el dise&#241;ador
El control <xref:System.Windows.Forms.DataGridView> le permite especificar estilos de celda predeterminados y formatos de datos de celda para todo el control, para columnas determinadas, para encabezados de filas y columnas, y para filas alternas para crear un efecto de doble carta.  Los estilos predeterminados establecidos para todo el control se reemplazan por los estilos predeterminados establecidos para las columnas y las filas alternas.  Además, los estilos que se establecen en el código para filas y celdas individuales reemplazan los estilos predeterminados.  
  
 Para obtener más información sobre herencia de estilos de celda, vea [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  Para establecer los estilos para filas alternas, vea [Cómo: Establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el diseñador](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md).  
  
 También puede establecer estilos mediante la propiedad <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> para afectar a todas las filas que se agregarán al control.  Para obtener más información sobre la plantilla de filas, vea [Cómo: Utilizar la plantilla de filas para personalizar filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md).  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.DataGridView>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para establecer los estilos predeterminados para todas las celdas en el control  
  
1.  Seleccione el control <xref:System.Windows.Forms.DataGridView> en el diseñador.  
  
2.  En la ventana **Propiedades**, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) situado junto a la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>.  Aparecerá el cuadro de diálogo **Generador de CellStyle**.  
  
3.  Defina el estilo estableciendo las propiedades, utilizando el panel **Vista previa** para confirmar sus opciones.  
  
> [!NOTE]
>  Si están habilitados los estilos visuales, se aplica el estilo automáticamente a los encabezados de columna y de fila del tema activo \(excepto para <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>\) reemplazando los valores de propiedad <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>.  
>   
>  Puede establecer estilos de celda para varios controles <xref:System.Windows.Forms.DataGridView> seleccionados mediante el diseñador, pero sólo si tienen valores idénticos para la propiedad de estilo de la celda que desea modificar.  Si cualquier estilo de celda es diferente de esta propiedad, las ventanas **Propiedades** del cuadro de diálogo **Generador de CellStyle** estarán en blanco.  
  
### Para establecer los estilos predeterminados para las celdas de columnas individuales  
  
1.  Haga clic con el botón secundario del mouse en el control <xref:System.Windows.Forms.DataGridView> en el diseñador y elija **Editar columnas**.  
  
2.  Seleccione una columna en la lista **Columnas seleccionadas**.  
  
3.  En la ventana **Propiedades de columna**, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) situado junto a la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>.  Aparecerá el cuadro de diálogo **Generador de CellStyle**.  
  
4.  Defina el estilo estableciendo las propiedades, utilizando el panel **Vista previa** para confirmar sus opciones.  
  
### Para dar formato a los datos de las celdas  
  
1.  Utilice uno de los procedimientos anteriores para mostrar un cuadro de diálogo **Generador de CellStyle** relacionado con una propiedad de estilo de celda predeterminada.  
  
2.  En la ventana **Generador de CellStyle**, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) situado junto a la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>.  Aparecerá el cuadro de diálogo **Cadena de formato**.  
  
3.  Seleccione un tipo de formato y, a continuación, modifique los detalles del tipo \(como el número de decimales que se van a mostrar\), mediante el cuadro **Muestra** para confirmar la elección.  
  
4.  Si está enlazando el control <xref:System.Windows.Forms.DataGridView> a un origen de datos que es probable que contenga valores nulos, rellene el cuadro de texto **Valor nulo**.  Este valor se muestra cuando el valor de la celda es igual a una referencia nula \(`Nothing` en Visual Basic\) o <xref:System.DBNull.Value?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=fullName>   
 [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el diseñador](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)