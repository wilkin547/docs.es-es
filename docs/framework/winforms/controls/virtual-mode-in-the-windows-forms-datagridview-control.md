---
title: Modo virtual del control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
ms.openlocfilehash: f284835578221ad1fe859f260e37bb829cd64b2d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124727"
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Modo virtual del control DataGridView de formularios Windows Forms
Con el modo virtual, puede administrar la interacción entre el <xref:System.Windows.Forms.DataGridView> control y una memoria caché de datos personalizados. Para implementar el modo virtual, establezca el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad `true` y controle uno o varios de los eventos descritos en este tema. Normalmente controlará al menos el `CellValueNeeded` eventos, lo que permite el control buscar valores en la caché de datos.  
  
## <a name="bound-mode-and-virtual-mode"></a>Modo de enlace y el modo Virtual  
 Modo virtual sólo es necesario cuando se necesita complementar o reemplazar el modo de enlace. En el modo de enlace, se establecen el <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad y el control automáticamente carga los datos del origen especificado y envía el usuario cambia a ella. Puede controlar cuál de las columnas enlazadas se muestran y el propio origen de datos normalmente controla las operaciones como la ordenación.  
  
## <a name="supplementing-bound-mode"></a>Complementar el modo de enlace  
 Puede complementar el modo de enlace mostrando las columnas sin enlazar junto con las columnas enlazadas. Esto se denomina "modo mixto" y es útil para mostrar cosas como controla los valores calculados o interfaz de usuario (UI).  
  
 Dado que las columnas sin enlazar están fuera del origen de datos, se omiten las operaciones de ordenación del origen de datos. Por lo tanto, al habilitar la ordenación en modo mixto, debe administrar los datos sin enlazar en una caché local e implementar el modo virtual para permitir que el <xref:System.Windows.Forms.DataGridView> control interactuar con él.  
  
 Para obtener más información sobre cómo usar el modo virtual para mantener los valores de columnas sin enlazar, vea los ejemplos en los <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> propiedad y <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> temas de referencia de la clase.  
  
## <a name="replacing-bound-mode"></a>Reemplazar el modo de enlace  
 Si el modo de enlace no satisfacen sus necesidades de rendimiento, puede administrar todos sus datos en una caché personalizada a través de los controladores de eventos de modo virtual. Por ejemplo, puede usar el modo virtual para implementar un mecanismo que recupera solo de carga de datos just-in-time todos los datos de una base de datos en red es necesario para un rendimiento óptimo. Este escenario es especialmente útil cuando se trabaja con grandes cantidades de datos a través de una conexión de red lenta o con los equipos cliente que tienen una cantidad limitada de memoria RAM o espacio de almacenamiento.  
  
 Para obtener más información sobre cómo usar el modo virtual en un escenario just-in-time, vea [implementar el modo Virtual con la carga de datos Just In Time en el DataGridView Control de formularios de Windows](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## <a name="virtual-mode-events"></a>Eventos en modo virtual  
 Si los datos están de solo lectura, el `CellValueNeeded` evento puede ser el único evento, deberá controlar. Eventos de modo virtual adicionales permiten habilitar funciones específicas, como las modificaciones del usuario, adición de fila y la eliminación y las transacciones de nivel de fila.  
  
 Algunos estándar <xref:System.Windows.Forms.DataGridView> eventos (por ejemplo, los eventos que se producen cuando los usuarios agregarán o eliminan filas o cuando los valores de celda se editado, analiza, validados o con formato) son útiles en modo virtual. También puede controlar los eventos que le permiten mantener los valores no suelen almacenados en un origen de datos enlazados, como datos de alto de fila, celda y texto de error de fila, celda y datos de menú contextual de fila y texto de información sobre herramientas de la celda.  
  
 Para obtener más información acerca de cómo implementar el modo virtual para administrar los datos de lectura/escritura con un ámbito de confirmación de nivel de fila, vea [Tutorial: Implementar el modo Virtual en el Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).  
  
 Para obtener un ejemplo que implementa el modo virtual con un ámbito de confirmación de nivel de celda, vea el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> tema de referencia de propiedad.  
  
 Los siguientes eventos se producen solo cuando el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad está establecida en `true`.  
  
|evento|Descripción|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Usa el control para recuperar un valor de celda de la caché de datos para su presentación. Este evento se produce solo para las celdas de las columnas sin enlazar.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Utilizado por el control para confirmar la entrada del usuario para una celda en la caché de datos. Este evento se produce solo para las celdas de las columnas sin enlazar.<br /><br /> Llame a la <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> método cuando se cambia un valor almacenado en caché fuera de un <xref:System.Windows.Forms.DataGridView.CellValuePushed> controlador de eventos para asegurarse de que el valor actual se muestra en el control y aplicar los modos de ajuste de tamaño automático actualmente en vigor.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Utilizado por el control para indicar la necesidad de una nueva fila en la caché de datos.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Usa el control para determinar si una fila tiene cambios sin confirmar.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Utilizado por el control para indicar que una fila debería revertirse a sus valores almacenados en caché.|  
  
 Los eventos siguientes son útiles en modo virtual, pero se puede usar con independencia de la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> configuración de la propiedad.  
  
|Eventos|Descripción|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Usa el control para indicar cuándo se eliminan las filas o agregado, lo que permite actualizar la caché de datos en consecuencia.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Utilizado por el control a los valores de celda de formato para mostrar y para analizar y validar la entrada del usuario.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Utilizado por el control para recuperar el texto de información sobre herramientas de la celda cuando el <xref:System.Windows.Forms.DataGridView.DataSource%2A> se establece la propiedad o el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad es `true`.<br /><br /> Información sobre herramientas de celda se muestra solo cuando el <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> es el valor de propiedad `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Utilizado por el control para recuperar el texto de error de celda o fila cuando la <xref:System.Windows.Forms.DataGridView.DataSource%2A> se establece la propiedad o el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad es `true`.<br /><br /> Llame a la <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> método o la <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> método cuando se cambia el texto de error de celda o fila para asegurarse de que el valor actual se muestra en el control.<br /><br /> Se muestran los glifos de error de fila y celda cuando la <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> y <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> son los valores de propiedad `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Utilizado por el control para recuperar una celda o fila <xref:System.Windows.Forms.ContextMenuStrip> cuando el control <xref:System.Windows.Forms.DataGridView.DataSource%2A> se establece la propiedad o el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad es `true`.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|Utiliza el control para recuperar o almacenar información de alto de fila en la caché de datos. Llame a la <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> método cuando se cambia la información de alto de fila almacenada en caché fuera de un <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> controlador de eventos para asegurarse de que se usa el valor actual en la presentación del control.|  
  
## <a name="best-practices-in-virtual-mode"></a>Procedimientos recomendados en modo Virtual  
 Si está implementando el modo virtual con el fin de trabajar eficazmente con grandes cantidades de datos, también deberá asegurarse de que está trabajando eficazmente con el <xref:System.Windows.Forms.DataGridView> propio control. Para obtener más información sobre el uso eficaz de estilos de celda, ajuste de tamaño automático, las selecciones y compartir filas, vea [mejores prácticas para escalar el DataGridView Control de Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Ajuste del rendimiento del control DataGridView en formularios Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
