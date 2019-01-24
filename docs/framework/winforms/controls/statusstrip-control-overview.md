---
title: Información general del control StatusStrip
ms.date: 03/30/2017
f1_keywords:
- StatusStrip
helpviewer_keywords:
- StatusStrip control [Windows Forms], about StatusStrip control
- status bars [Windows Forms], about status bars
ms.assetid: c0d9bcbb-f8b8-46ef-bae2-4146b8c8ce99
ms.openlocfilehash: 9356ca85003987eabf4f62a25acad45d73e144fe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627244"
---
# <a name="statusstrip-control-overview"></a>Información general del control StatusStrip
Un control <xref:System.Windows.Forms.StatusStrip> muestra información sobre un objeto que se visualiza en <xref:System.Windows.Forms.Form>, componentes del objeto o información contextual relativa a esa operación del objeto en la aplicación. Normalmente, un control <xref:System.Windows.Forms.StatusStrip> está formado por objetos <xref:System.Windows.Forms.ToolStripStatusLabel>, cada uno de los cuales muestra texto, un icono o ambos. El control <xref:System.Windows.Forms.StatusStrip> también puede contener los controles <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton> y <xref:System.Windows.Forms.ToolStripProgressBar>.  
  
 El control <xref:System.Windows.Forms.StatusStrip> predeterminado no tiene paneles. Para agregar paneles a <xref:System.Windows.Forms.StatusStrip>, utilice el método <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType>.  
  
 Hay una amplia compatibilidad para controlar elementos <xref:System.Windows.Forms.StatusStrip> y comandos comunes en Visual Studio.  
  
 Consulte también [Editor de colección de elementos StatusStrip](https://msdn.microsoft.com/library/ms233631\(v=vs.110\)), [cuadro de diálogo de tareas de StatusStrip](https://msdn.microsoft.com/library/ms233642\(v=vs.110\)).  
  
 Aunque el control <xref:System.Windows.Forms.StatusStrip> reemplaza y amplía el control <xref:System.Windows.Forms.StatusBar> de versiones anteriores, <xref:System.Windows.Forms.StatusBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, según sea el caso.  
  
### <a name="important-statusstrip-members"></a>Miembros de StatusStrip importantes  
  
|Nombre|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.StatusStrip.CanOverflow%2A>|Obtiene o establece un valor que indica si <xref:System.Windows.Forms.StatusStrip> admite la funcionalidad del desbordamiento.|  
|<xref:System.Windows.Forms.StatusStrip.Stretch%2A>|Obtiene o establece un valor que indica si <xref:System.Windows.Forms.StatusStrip> se expande de punto de conexión a punto de conexión en <xref:System.Windows.Forms.ToolStripContainer>.|  
  
### <a name="important-statusstrip-companion-classes"></a>Clases complementarias importantes de StatusStrip  
  
|Nombre|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|Representa un panel de un control <xref:System.Windows.Forms.StatusStrip>.|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|Muestra un <xref:System.Windows.Forms.ToolStripDropDown> asociado en el que el usuario puede seleccionar un elemento único.|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|Representa un control de dos elementos que son un botón estándar y un menú desplegable.|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|Muestra el estado de finalización de un proceso.|  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>
