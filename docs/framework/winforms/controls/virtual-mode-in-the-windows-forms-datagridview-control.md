---
title: Modo virtual en el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
ms.openlocfilehash: 0d82f0fc9946e5b61ea171f2f5d2ab5690db0c71
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745446"
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Modo virtual del control DataGridView de formularios Windows Forms
Con el modo virtual, puede administrar la interacción entre el control <xref:System.Windows.Forms.DataGridView> y una memoria caché de datos personalizada. Para implementar el modo virtual, establezca la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> en `true` y controle uno o varios de los eventos descritos en este tema. Normalmente, se controla al menos el evento `CellValueNeeded`, lo que permite al control buscar valores en la memoria caché de datos.  
  
## <a name="bound-mode-and-virtual-mode"></a>Modo enlazado y modo virtual  
 El modo virtual solo es necesario cuando se necesita complementar o reemplazar el modo enlazado. En el modo de enlace, establezca la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A> y el control cargará automáticamente los datos desde el origen especificado y enviará de nuevo los cambios del usuario. Puede controlar qué columnas enlazadas se muestran y el propio origen de datos controla normalmente operaciones como la ordenación.  
  
## <a name="supplementing-bound-mode"></a>Modo de enlace complementario  
 Puede complementar el modo de enlace mostrando columnas sin enlazar junto con las columnas enlazadas. Esto se denomina a veces "modo mixto" y es útil para mostrar elementos como valores calculados o controles de interfaz de usuario (IU).  
  
 Dado que las columnas sin enlazar están fuera del origen de datos, las operaciones de ordenación del origen de datos las omiten. Por lo tanto, al habilitar la ordenación en modo mixto, debe administrar los datos sin enlazar en una memoria caché local e implementar el modo virtual para permitir que el control de <xref:System.Windows.Forms.DataGridView> interactúe con él.  
  
 Para obtener más información sobre el uso del modo virtual para mantener los valores de las columnas sin enlazar, vea los ejemplos de la propiedad <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> y los temas de referencia de la clase <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>.  
  
## <a name="replacing-bound-mode"></a>Reemplazar el modo enlazado  
 Si el modo de enlace no satisface sus necesidades de rendimiento, puede administrar todos los datos en una memoria caché personalizada a través de los controladores de eventos de modo virtual. Por ejemplo, puede usar el modo virtual para implementar un mecanismo de carga de datos Just-in-Time que recupere solo tantos datos de una base de datos en red como sea necesario para un rendimiento óptimo. Este escenario es especialmente útil cuando se trabaja con grandes cantidades de datos a través de una conexión de red lenta o con equipos cliente que tienen una cantidad limitada de memoria RAM o espacio de almacenamiento.  
  
 Para obtener más información sobre el uso del modo virtual en un escenario Just-in-Time, vea [implementar el modo virtual con la carga de datos Just-in-Time en el control DataGridView Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## <a name="virtual-mode-events"></a>Eventos de modo virtual  
 Si los datos son de solo lectura, el evento de `CellValueNeeded` puede ser el único que deberá controlar. Los eventos de modo virtual adicionales permiten habilitar funciones específicas, como ediciones de usuario, adiciones y eliminaciones de filas y transacciones de nivel de fila.  
  
 Algunos eventos de <xref:System.Windows.Forms.DataGridView> estándar (como los eventos que se producen cuando los usuarios agregan o eliminan filas, o cuando los valores de celda se editan, analizan, validan o formatean) también son útiles en el modo virtual. También puede controlar eventos que permiten mantener valores que normalmente no se almacenan en un origen de datos enlazado, como texto de información sobre herramientas de celda, texto de error de celda y fila, datos de menú contextual de celda y fila y datos de alto de fila.  
  
 Para obtener más información sobre cómo implementar el modo virtual para administrar datos de lectura y escritura con un ámbito de confirmación de nivel de fila, vea [Tutorial: implementar el modo virtual en el control DataGridView de Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).  
  
 Para obtener un ejemplo en el que se implementa el modo virtual con un ámbito de confirmación de nivel de celda, vea el tema de referencia de la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
 Los eventos siguientes solo se producen cuando la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> está establecida en `true`.  
  
|Event|Descripción|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Lo utiliza el control para recuperar un valor de celda de la memoria caché de datos para su presentación. Este evento solo se produce para las celdas de columnas sin enlazar.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Lo utiliza el control para confirmar la entrada del usuario para una celda en la memoria caché de datos. Este evento solo se produce para las celdas de columnas sin enlazar.<br /><br /> Llame al método <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> cuando cambie un valor almacenado en memoria caché fuera de un controlador de eventos <xref:System.Windows.Forms.DataGridView.CellValuePushed> para asegurarse de que el valor actual se muestra en el control y para aplicar los modos de ajuste automático de tamaño actualmente en vigor.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Lo utiliza el control para indicar la necesidad de una nueva fila en la memoria caché de datos.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Lo utiliza el control para determinar si una fila tiene cambios sin confirmar.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Lo utiliza el control para indicar que una fila debe volver a sus valores almacenados en caché.|  
  
 Los eventos siguientes son útiles en el modo virtual, pero se pueden usar independientemente del valor de la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
|eventos|Descripción|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Lo utiliza el control para indicar cuándo se eliminan o se agregan filas, lo que le permite actualizar la memoria caché de datos según corresponda.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Lo utiliza el control para dar formato a los valores de celda para su presentación y para analizar y validar los datos proporcionados por el usuario.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Lo utiliza el control para recuperar el texto de información sobre herramientas de la celda cuando se establece la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A> o se `true`la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.<br /><br /> La información sobre herramientas de celda solo se muestra cuando se `true`el valor de la propiedad <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A>.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Lo utiliza el control para recuperar el texto de error de celda o fila cuando se establece la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A> o se `true`la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.<br /><br /> Llame al método <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> o al método <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> cuando cambie el texto de error de celda o fila para asegurarse de que el valor actual se muestra en el control.<br /><br /> Los glifos de error de celda y fila se muestran cuando se `true`los valores de la propiedad <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> y <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A>.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Lo utiliza el control para recuperar una celda o fila <xref:System.Windows.Forms.ContextMenuStrip> cuando se establece la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A> del control o se `true`la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|Lo utiliza el control para recuperar o almacenar la información de alto de las filas en la memoria caché de datos. Llame al método <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> cuando cambie la información del alto de las filas almacenadas en caché fuera de un controlador de eventos <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> para asegurarse de que el valor actual se usa en la presentación del control.|  
  
## <a name="best-practices-in-virtual-mode"></a>Prácticas recomendadas en el modo virtual  
 Si va a implementar el modo virtual para trabajar de forma eficaz con grandes cantidades de datos, también querrá asegurarse de que está trabajando de forma eficaz con el <xref:System.Windows.Forms.DataGridView> control. Para obtener más información sobre el uso eficaz de los estilos de celda, el ajuste automático de tamaño, las selecciones y el uso compartido de filas, vea [prácticas recomendadas para escalar el control DataGridView Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Ajuste del rendimiento del control DataGridView en Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Tutorial: Implementar el modo virtual en el control DataGridView de Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
