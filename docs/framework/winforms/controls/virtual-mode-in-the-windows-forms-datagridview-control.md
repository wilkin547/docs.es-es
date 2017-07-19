---
title: "Modo virtual del control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "DataGridView (control) [Windows Forms], modo virtual"
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Modo virtual del control DataGridView de formularios Windows Forms
Con el modo virtual, puede administrar la interacción entre el control <xref:System.Windows.Forms.DataGridView> y una caché de datos personalizada.  Para implementar el modo virtual, establezca la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> en `true` y controle uno o más de los eventos descritos en este tema.  Normalmente se controlará por lo menos el evento `CellValueNeeded`, que habilita los valores de búsqueda del control en la caché de datos.  
  
## Modo de enlace y modo virtual  
 El modo virtual sólo es necesario cuando necesita complementar o reemplazar el modo de enlace.  En modo de enlace, se establece la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A> y el control carga automáticamente los datos del origen especificado y envía los cambios de nuevo al usuario.  Puede controlar las columnas enlazadas que se van a mostrar, y el mismo origen de datos controla normalmente operaciones tales como la ordenación.  
  
## Complementar el modo de enlace  
 Para complementar el modo de enlace, muestre las columnas sin enlazar junto con las columnas enlazadas.  Este procedimiento a veces se denomina "modo mixto" y es útil para mostrar, por ejemplo, valores calculados o controles de interfaz del usuario.  
  
 Dado que las columnas sin enlazar están fuera del origen de datos, las omiten las operaciones de ordenación del origen de datos.  Por consiguiente, cuando habilita la ordenación en modo mixto, debe administrar los datos sin enlazar en una caché local e implementar el modo virtual para dejar que el control <xref:System.Windows.Forms.DataGridView> interactúe con él.  
  
 Para obtener más información sobre el uso del modo virtual para mantener los valores de las columnas sin enlazar, vea los ejemplos en los temas de referencia de la propiedad <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=fullName> y de la clase <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=fullName>.  
  
## Reemplazar el modo de enlace  
 Si el modo de enlace no satisface las necesidades de rendimiento, puede administrar todos los datos en una caché personalizada a través de los controladores de eventos en modo virtual.  Por ejemplo, puede utilizar el modo virtual para implementar un mecanismo de carga de datos Just\-in\-time \(JIT\) que recupere sólo los datos de una base de datos en red que sean necesarios para obtener un rendimiento óptimo.  Este escenario resulta particularmente útil al trabajar con grandes cantidades de datos en una conexión de red lenta, o con equipos cliente que tienen una cantidad limitada de RAM o de espacio de almacenamiento.  
  
 Para obtener más información sobre cómo utilizar el modo virtual en un escenario Just\-in\-time, vea [Implementar el modo virtual mediante la carga de datos Just\-In\-Time en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## Eventos en modo virtual  
 Si los datos son de sólo lectura, el evento `CellValueNeeded` puede ser el único evento que necesite controlar.  Los eventos en modo virtual adicionales permiten habilitar la funcionalidad concreta como modificaciones del usuario, adición o eliminación de filas y las transacciones de fila.  
  
 Asimismo, también son útiles en modo virtual algunos eventos <xref:System.Windows.Forms.DataGridView> estándar \(como los eventos que tienen lugar cuando los usuarios agregan o eliminan filas, o cuando los valores de celda se modifican, analizan, validan o reciben formato\).  También se pueden controlar eventos que permiten mantener valores que normalmente no están almacenados en un origen de datos enlazado, como el texto de la información sobre herramientas de celdas, texto de error de celdas y filas, datos de menús contextuales de filas y celdas, y datos de alto de filas.  
  
 Para obtener más información sobre cómo implementar el modo virtual para administrar los datos de lectura y escritura con un ámbito de confirmación de fila, vea [Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
 Para obtener un ejemplo que implementa el modo virtual con un ámbito de confirmación de celda, vea el tema de referencia de la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
 Los eventos siguientes sólo aparecen cuando la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> se establece en `true`.  
  
|Evento|Descripción|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Lo utiliza el control para recuperar un valor de celda de la caché de datos para su presentación.  Este evento sólo tiene lugar en aquellas celdas de columnas sin enlazar.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Lo utiliza el control para confirmar los datos proporcionados por el usuario para una celda a la caché de datos.  Este evento sólo tiene lugar en aquellas celdas de columnas sin enlazar.<br /><br /> Llame al método <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> cuando se modifique un valor en caché fuera de un controlador de evento <xref:System.Windows.Forms.DataGridView.CellValuePushed> para asegurar que se muestra el valor actual en el control y para aplicar los modos de tamaño automáticos actualmente en vigor.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Lo utiliza el control para indicar la necesidad de una nueva fila en la caché de datos.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Lo utiliza el control para determinar si una fila tiene algún cambio sin confirmar.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Lo utiliza el control para indicar que una fila debería revertir a sus valores almacenados en memoria caché.|  
  
 Los eventos siguientes son útiles en modo virtual, pero se pueden utilizar sin tener en cuenta el valor de la configuración de la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
|Eventos|Descripción|  
|-------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Lo utiliza el control para indicar cuándo se eliminan o se agregan filas, permitiéndole actualizar la caché de datos en consecuencia.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Lo utiliza el control para dar formato a los valores de celda para su presentación y para analizar y validar los datos proporcionados por el usuario.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Lo utiliza el control para recuperar el texto de información sobre herramientas de la celda cuando se establece la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A> o la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> es `true`.<br /><br /> Se muestra la información sobre herramientas de la celda únicamente cuando el valor de propiedad <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> es `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Lo utiliza el control para recuperar el texto de error de la fila o celda cuando se establece la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A> o la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> es `true`.<br /><br /> Llame al método <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> o al método <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> cuando cambie el texto de error de la fila o celda para asegurar que se muestra el valor actual en el control.<br /><br /> Se muestran los glifos de error de la celda y fila cuando los valores de propiedad <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> y <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> son `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Lo utiliza el control para recuperar un <xref:System.Windows.Forms.ContextMenuStrip> de la celda o fila cuando se establece la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A> del control o la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> es `true`.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|La utiliza el control para recuperar o almacenar información del alto de fila en la caché de datos.  Llame al método <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> cuando cambie la información de alto de fila almacenada en la memoria caché fuera de un controlador de eventos <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> para asegurar que se utiliza el valor actual al mostrar el control.|  
  
## Procedimientos recomendados en modo virtual  
 Si está implementando en modo virtual con objeto de trabajar eficazmente con grandes cantidades de datos, también deseará asegurar que está trabajando eficazmente con el mismo control <xref:System.Windows.Forms.DataGridView>.  Para obtener más información sobre el uso eficaz de estilos de celda, ajustes automáticos de tamaño, selecciones y uso compartido de filas, vea [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>   
 [Ajuste del rendimiento del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)   
 [Implementar el modo virtual mediante la carga de datos Just\-In\-Time en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)