---
title: "Tutorial: Crear un control DataGridView sin enlazar en formularios Windows Forms | Microsoft Docs"
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
  - "datos [Windows Forms], mostrar sin enlace a origen de datos"
  - "datos [Windows Forms], sin enlazar"
  - "DataGridView (control) [Windows Forms], mostrar datos sin enlace a origen de datos"
  - "DataGridView (control) [Windows Forms], datos sin enlazar"
  - "tutoriales [Windows Forms], DataGridView (control)"
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Tutorial: Crear un control DataGridView sin enlazar en formularios Windows Forms
Quizá desee mostrar frecuentemente datos en formato de tabla que no tienen su origen en una base de datos.  Por ejemplo, quizá desear mostrar el contenido de una matriz bidimensional de tipo String.  La clase <xref:System.Windows.Forms.DataGridView> proporciona una manera fácil y muy personalizable de mostrar los datos sin enlazarse a un origen de datos.  Este tutorial muestra cómo rellenar un control <xref:System.Windows.Forms.DataGridView> y administrar la agregación y eliminación de filas en modo "sin enlazar".  De forma predeterminada, el usuario puede agregar nuevas filas.  Para impedir que se agreguen filas, establezca la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> en `false`.  
  
 Para copiar el código de este tema como un listado sencillo, vea [Cómo: Crear un control DataGridView no enlazado en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## Crear el formulario  
  
#### Para utilizar un control DataGridView sin enlazar  
  
1.  Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene las declaraciones de variable siguientes y el método `Main`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2.  Implemente un método `SetupLayout` en la definición de clase del formulario para configurar el diseño del formulario.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3.  Cree un método `SetupDataGridView` para configurar las columnas y propiedades de <xref:System.Windows.Forms.DataGridView>.  
  
     Este método primero agrega el control <xref:System.Windows.Forms.DataGridView> a la colección <xref:System.Windows.Forms.Control.Controls%2A> del formulario.  Luego, establece el número de columnas que se va a mostrar utilizando la propiedad <xref:System.Windows.Forms.DataGridView.ColumnCount%2A>.  Para establecer el estilo predeterminado de los encabezados de columna, establezca las propiedades: <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> del <xref:System.Windows.Forms.DataGridViewCellStyle> devuelto por la propiedad <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>.  
  
     Se establecerán las propiedades de diseño y apariencia y, a continuación, se asignarán los nombres de columna.  Cuando este método devuelve el control al sistema, el control <xref:System.Windows.Forms.DataGridView> está listo para rellenarse.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4.  Cree un método `PopulateDataGridView` para agregar las filas al control <xref:System.Windows.Forms.DataGridView>.  
  
     Cada fila representa una canción y su información asociada.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5.  Con los métodos de utilidad en contexto, puede asociar controladores de eventos.  
  
     Controlará los eventos <xref:System.Windows.Forms.Control.Click> de los botones **Agregar** y **Eliminar**, el evento <xref:System.Windows.Forms.Form.Load> del formulario y el evento <xref:System.Windows.Forms.DataGridView.CellFormatting> del control <xref:System.Windows.Forms.DataGridView>.  
  
     Cuando se provoca el evento <xref:System.Windows.Forms.Control.Click> del botón **Agregar**, se agrega una nueva fila vacía a <xref:System.Windows.Forms.DataGridView>.  
  
     Cuando se provoca el evento <xref:System.Windows.Forms.Control.Click> del botón **Eliminar**, se elimina la fila seleccionada, a no ser que sea la fila para nuevos registros, que permite al usuario agregar nuevas filas.  Esta fila siempre es la última fila del control <xref:System.Windows.Forms.DataGridView>.  
  
     Cuando se provoca el evento <xref:System.Windows.Forms.Form.Load> del formulario, se llama a los métodos de utilidad `SetupLayout`, `SetupDataGridView` y `PopulateDataGridView`.  
  
     Cuando se provoca el evento <xref:System.Windows.Forms.DataGridView.CellFormatting>, se da formato de fecha larga a todas las celdas de la columna `Date`, a no ser que no se pueda analizar el valor de la celda.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### Para comprobar el formulario  
  
-   Presione F5 para ejecutar la aplicación.  
  
     Aparecerá un control <xref:System.Windows.Forms.DataGridView> que muestra las canciones enumeradas en `PopulateDataGridView`.  Puede agregar nuevas filas con el botón **Agregar fila** o eliminar las filas seleccionadas con el botón **Eliminar fila**.  El control <xref:System.Windows.Forms.DataGridView> independiente es el almacén de datos y sus datos son independientes de cualquier origen externo, como un <xref:System.Data.DataSet> o una matriz.  
  
## Pasos siguientes  
 Esta aplicación proporciona conocimientos básicos sobre las funciones del control <xref:System.Windows.Forms.DataGridView>.  Puede personalizar la apariencia y el comportamiento del control <xref:System.Windows.Forms.DataGridView> de varias formas:  
  
-   Cambie los estilos de borde y encabezado.  Para obtener más información, vea [Cómo: Cambiar los estilos de borde y línea de la cuadrícula en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Permita o restringa los datos proporcionados por el usuario al control <xref:System.Windows.Forms.DataGridView>.  Para obtener más información, vea [Cómo: Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md) y [Cómo: Crear columnas de sólo lectura en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Compruebe si los datos proporcionados por el usuario tienen errores relacionados con base de datos.  Para obtener más información, vea [Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Controle conjuntos de grandes volúmenes de datos utilizando el modo virtual.  Para obtener más información, vea [Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalice la apariencia de las celdas.  Para obtener más información, vea [Cómo: Personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 [Mostrar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Crear un control DataGridView no enlazado en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)   
 [Modos de presentación de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)