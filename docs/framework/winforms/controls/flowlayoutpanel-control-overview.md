---
title: Información general sobre el control FlowLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
ms.openlocfilehash: 260146cd901fe2b80a73c01060ccd55958cd169e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011325"
---
# <a name="flowlayoutpanel-control-overview"></a>Información general sobre el control FlowLayoutPanel
El control <xref:System.Windows.Forms.FlowLayoutPanel> organiza su contenido en una dirección de flujo horizontal o vertical. Puede ajustar el contenido del control de una fila a la siguiente, o de una columna a la siguiente. También puede recortar el contenido en lugar de ajustarlo.  
  
 Puede especificar la dirección de flujo estableciendo el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>. El control <xref:System.Windows.Forms.FlowLayoutPanel> invierte correctamente su dirección de flujo en diseños de derecha a izquierda (RTL). También puede especificar si el contenido del control <xref:System.Windows.Forms.FlowLayoutPanel> se ajustará o se recortará estableciendo el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A>.  
  
 El control <xref:System.Windows.Forms.FlowLayoutPanel> ajusta automáticamente su tamaño al contenido cuando la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> se establece en `true`. También proporciona un **FlowBreak** propiedad a sus controles secundarios. Al establecer el valor de la propiedad FlowBreak en `true` , el control <xref:System.Windows.Forms.FlowLayoutPanel> deja de distribuir los controles en la dirección del flujo actual y ajusta a la siguiente fila o columna.  
  
 Cualquier control de Windows Forms puede ser un control secundario del control <xref:System.Windows.Forms.FlowLayoutPanel>, incluidas otras instancias de <xref:System.Windows.Forms.FlowLayoutPanel>. Con esta funcionalidad, puede construir diseños sofisticados que se adapten a las dimensiones del formulario en tiempo de ejecución.  
  
 Consulte también [Tutorial: Organizar controles en formularios de Windows Forms mediante FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [FlowLayoutPanel (control)](flowlayoutpanel-control-windows-forms.md)
