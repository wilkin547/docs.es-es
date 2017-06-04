---
title: "Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "DataGridView (control) [Windows Forms], agregar filas para registros nuevos"
  - "DataGridView (control) [Windows Forms], entrada de datos"
  - "filas, registros nuevos"
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms
Cuando utilice un control <xref:System.Windows.Forms.DataGridView> para modificar datos en la aplicación, con frecuencia deseará ofrecer a los usuarios la posibilidad de agregar nuevas filas de datos al almacén de datos.  El control <xref:System.Windows.Forms.DataGridView> admite esta funcionalidad proporcionando una fila para nuevos registros, que siempre se muestra como última fila.  Se marca con un símbolo del asterisco \(\*\) en su encabezado de fila.  En las secciones siguientes se explica todo lo que hay que tener en cuenta cuando se programa con la fila para nuevos registros habilitada.  
  
## Mostrar la fila para los nuevos registros  
 Utilice la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> para indicar si se muestra la fila para los nuevos registros.  El valor predeterminado de esta propiedad es `true`.  
  
 En el caso enlazado a datos, se mostrará la fila para los nuevos registros si la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> del control y la propiedad <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=fullName> del origen de datos son ambos `true`.  Si alguno es `false`, no se mostrará la fila.  
  
## Rellenar la fila para los nuevos registros con datos predeterminados  
 Cuando el usuario selecciona la fila para los nuevos registros como la fila actual, el control <xref:System.Windows.Forms.DataGridView> provoca el evento <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.  
  
 Este evento proporciona acceso al nuevo control <xref:System.Windows.Forms.DataGridViewRow> y le permite rellenar la nueva fila con datos predeterminados.  Para obtener más información, vea [Cómo: Especificar valores predeterminados para nuevas filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md).  
  
## La colección de filas  
 La fila para los nuevos registros se encuentra en la colección <xref:System.Windows.Forms.DataGridView.Rows%2A> del control <xref:System.Windows.Forms.DataGridView> pero se comporta de manera diferente en dos aspectos:  
  
-   La fila para los nuevos registros no se puede quitar mediante programación de la colección <xref:System.Windows.Forms.DataGridView.Rows%2A>.  Se produce una <xref:System.InvalidOperationException> si se intenta.  El usuario tampoco puede eliminar la fila para los nuevos registros.  El método <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=fullName> no quita esta fila de la colección <xref:System.Windows.Forms.DataGridView.Rows%2A>.  
  
-   No se puede agregar ninguna fila después de la fila para los nuevos registros.  Se produce una <xref:System.InvalidOperationException> si se intenta.  Como resultado, la fila para los nuevos registros siempre es la última fila en el control <xref:System.Windows.Forms.DataGridView>.  Los métodos en <xref:System.Windows.Forms.DataGridViewRowCollection> que agregan filas son: <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A> y <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>. Todos ellos llaman internamente a métodos de inserción cuando está presente la fila para los nuevos registros.  
  
## Personalización visual de la fila para los nuevos registros  
 Cuando se crea la fila para los nuevos registros, se basa en la fila especificada por la propiedad <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>.  Los estilos de celda que no se hayan especificado para esta fila se heredan de otras propiedades.  Para obtener más información sobre herencia de estilos de celda, vea [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Los valores iniciales mostrados por las celdas en la fila para los nuevos registros se recuperan de la propiedad <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> de cada celda.  Para las celdas de tipo <xref:System.Windows.Forms.DataGridViewImageCell>, esta propiedad devuelve una imagen del marcador de posición.  En caso contrario, esta propiedad devuelve `null`.  Puede reemplazar esta propiedad para devolver un valor personalizado.  Sin embargo, el controlador de eventos <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> puede reemplazar a estos valores iniciales cuando el foco escribe la fila para los nuevos registros.  
  
 No se exponen públicamente los iconos estándar para el encabezado de esta fila, que son una flecha o un asterisco.  Si desea personalizar los iconos, necesitará crear una clase <xref:System.Windows.Forms.DataGridViewRowHeaderCell> personalizada.  
  
 Los iconos estándar utilizan la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> de <xref:System.Windows.Forms.DataGridViewCellStyle> en uso por la celda del encabezado de fila.  Los iconos estándar no se representan si no hay suficiente espacio para mostrarlos por completo.  
  
 Si la celda del encabezado de fila tiene establecido un valor de cadena, y si no hay suficiente espacio para el texto y el icono, éste se quita primero.  
  
## Ordenar  
 En modo sin enlace, se agregan siempre los nuevos registros al final del control <xref:System.Windows.Forms.DataGridView> aunque el usuario haya ordenado el contenido de <xref:System.Windows.Forms.DataGridView>.  El usuario necesitará aplicar de nuevo la ordenación para que la fila ocupe la posición correcta. Este comportamiento es similar al del control <xref:System.Windows.Forms.ListView>.  
  
 En los modos de enlace a datos y virtuales, el comportamiento de inserción al aplicar una ordenación es dependiente en la implementación del modelo de datos.  En [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], la fila se ordena inmediatamente en la posición correcta.  
  
## Otras notas en la fila para los nuevos registros  
 No puede establecer la propiedad <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> de esta fila en `false`.  Se produce una <xref:System.InvalidOperationException> si se intenta.  
  
 La fila para los nuevos registros siempre se crea en estado no seleccionado.  
  
## Modo virtual  
 Si está implementando el modo virtual, necesitará saber si se necesita una fila de nuevos registros en el modelo de datos y si hay que revertir la adición de la fila.  La implementación exacta de esta funcionalidad depende de la implementación del modelo de datos y de la semántica de la transacción, por ejemplo, si el ámbito de confirmación se encuentra en el nivel de la celda o de la fila.  Para obtener más información, vea [Modo virtual del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=fullName>   
 [Entrada de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Especificar valores predeterminados para nuevas filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)