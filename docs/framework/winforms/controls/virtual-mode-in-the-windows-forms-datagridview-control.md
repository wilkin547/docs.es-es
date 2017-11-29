---
title: Modo virtual del control DataGridView de formularios Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10c6afbcde22a82e6227ce1d95d57749bee1a88c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Modo virtual del control DataGridView de formularios Windows Forms
Con el modo virtual, puede administrar la interacción entre el <xref:System.Windows.Forms.DataGridView> control y una memoria caché de datos personalizados. Para implementar el modo virtual, establezca la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad `true` y administrar uno o varios de los eventos descritos en este tema. Normalmente controlará por lo menos el `CellValueNeeded` eventos, lo que permite el control buscar valores en la caché de datos.  
  
## <a name="bound-mode-and-virtual-mode"></a>Modo de enlace y el modo Virtual  
 Modo virtual solo es necesario cuando necesita complementar o reemplazar el modo de enlace. En el modo de enlace, establezca la <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad y el control automáticamente carga los datos del origen especificado y envía el usuario cambia volver a él. Puede controlar cuáles de las columnas enlazadas se muestran y el propio origen de datos normalmente controla las operaciones como la ordenación.  
  
## <a name="supplementing-bound-mode"></a>Complementar el modo de enlace  
 También puede complementar el modo de enlace mostrando las columnas sin enlazar junto con las columnas enlazadas. Esto se denomina "modo mixto" y es útil para mostrar cosas como controla valores calculados o interfaz de usuario (UI).  
  
 Dado que las columnas sin enlazar están fuera del origen de datos, se omiten las operaciones de ordenación del origen de datos. Por lo tanto, al habilitar la ordenación en modo mixto, debe administrar los datos sin enlazar en una caché local e implementar el modo virtual para permitir que el <xref:System.Windows.Forms.DataGridView> control interactuar con él.  
  
 Para obtener más información sobre cómo usar el modo virtual para mantener los valores de columnas sin enlazar, vea los ejemplos en la <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> propiedad y <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> temas de referencia de la clase.  
  
## <a name="replacing-bound-mode"></a>Reemplazar el modo de enlace  
 Si el modo de enlace no satisfacen sus necesidades de rendimiento, puede administrar todos los datos en una caché personalizada a través de los controladores de eventos de modo virtual. Por ejemplo, puede utilizar el modo virtual para implementar una carga mecanismo que recupera solo de datos just-in-time tantos datos desde una base de datos en red como sea necesario para un rendimiento óptimo. Este escenario es especialmente útil cuando se trabaja con grandes cantidades de datos a través de una conexión de red lenta o con equipos cliente que tienen una cantidad limitada de RAM o espacio de almacenamiento.  
  
 Para obtener más información acerca de cómo utilizar el modo virtual en un escenario de just-in-time, vea [implementar el modo Virtual con la carga de datos Just en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## <a name="virtual-mode-events"></a>Eventos de modo virtual  
 Si los datos son de solo lectura, el `CellValueNeeded` evento puede ser el único evento que debe controlar. Eventos de modo virtual adicionales permiten habilitar la funcionalidad concreta como modificaciones del usuario, adición de fila y eliminación y las transacciones de nivel de fila.  
  
 Algunos estándar <xref:System.Windows.Forms.DataGridView> eventos (como eventos que se producen cuando los usuarios agregarán o eliminan filas o cuando los valores de celda se editado, analizar, validar o con formato) son útiles en modo virtual. También puede controlar los eventos que le permiten mantener valores que normalmente no están almacenados en un origen de datos enlazados, como el texto de información sobre herramientas de la celda, celda y texto de error de fila, celda y datos de menú contextual de fila y datos de alto de fila.  
  
 Para obtener más información acerca de cómo implementar el modo virtual para administrar los datos de lectura/escritura con un ámbito de confirmación de nivel de fila, vea [Tutorial: implementar el modo Virtual en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
 Para obtener un ejemplo que implementa el modo virtual con un ámbito de confirmación de nivel de celda, vea el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> tema de referencia de propiedad.  
  
 Los siguientes eventos se producen solo cuando la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad está establecida en `true`.  
  
|Evento|Descripción|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Utilizados por el control para recuperar un valor de celda de la caché de datos para su presentación. Este evento sólo se produce para las celdas de las columnas sin enlazar.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Utiliza el control para confirmar proporcionados por el usuario para una celda en la caché de datos. Este evento sólo se produce para las celdas de las columnas sin enlazar.<br /><br /> Llame a la <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> método cuando se cambia un valor almacenado en caché fuera de un <xref:System.Windows.Forms.DataGridView.CellValuePushed> controlador de eventos para asegurarse de que el valor actual se muestra en el control y para aplicar los modos de ajuste automático de tamaño actualmente en vigor.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Utiliza el control para indicar la necesidad de una nueva fila en la caché de datos.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Utilizados por el control para determinar si una fila tiene cambios sin confirmar.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Utiliza el control para indicar que una fila debería revertir a sus valores almacenados en caché.|  
  
 Los eventos siguientes son útiles en modo virtual, pero puede utilizarse con independencia de la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> configuración de la propiedad.  
  
|Eventos|Descripción|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Utilizados por el control para indicar cuándo se eliminan filas o agregado, permitiéndole actualizar la caché de datos en consecuencia.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Utilizados por el control para valores de formato de celda para su presentación y para analizar y validar los proporcionados por el usuario.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Utiliza el control para recuperar el texto de información sobre herramientas de la celda cuando el <xref:System.Windows.Forms.DataGridView.DataSource%2A> se establece la propiedad o el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad es `true`.<br /><br /> Información sobre herramientas de celda se muestra solo cuando la <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> es el valor de la propiedad `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Utiliza el control para recuperar el texto de error de celda o fila cuando la <xref:System.Windows.Forms.DataGridView.DataSource%2A> se establece la propiedad o el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad es `true`.<br /><br /> Llame a la <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> método o la <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> método cuando se cambia el texto de error de celda o fila para asegurarse de que el valor actual se muestra en el control.<br /><br /> Se muestran los glifos de error de fila y celda cuando la <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> y <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> valores de propiedad son `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Utiliza el control para recuperar una celda o fila <xref:System.Windows.Forms.ContextMenuStrip> cuando el control <xref:System.Windows.Forms.DataGridView.DataSource%2A> se establece la propiedad o el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad es `true`.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|Usar el control para recuperar o almacenar información de alto de fila en la caché de datos. Llame a la <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> método cuando se cambia la información de alto de fila en caché fuera de un <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> controlador de eventos para asegurarse de que se usa el valor actual en la presentación del control.|  
  
## <a name="best-practices-in-virtual-mode"></a>Procedimientos recomendados en modo Virtual  
 Si está implementando el modo virtual para poder trabajar eficazmente con grandes cantidades de datos, también deberá asegurarse de que está trabajando eficazmente con el <xref:System.Windows.Forms.DataGridView> propio control. Para obtener más información sobre el uso eficaz de estilos de celda, ajuste automático de tamaño, selecciones y uso compartido de filas, vea [procedimientos recomendados para ajustar la escala del DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 [Ajuste del rendimiento del control DataGridView en Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Tutorial: Implementar el modo virtual en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 [Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
