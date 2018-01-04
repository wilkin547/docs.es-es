---
title: "Información general sobre el control FlowLayoutPanel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7eafe31bec86a969a12661c9f5629b2d55e3e3d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="flowlayoutpanel-control-overview"></a>Información general sobre el control FlowLayoutPanel
El control <xref:System.Windows.Forms.FlowLayoutPanel> organiza su contenido en una dirección de flujo horizontal o vertical. Puede ajustar el contenido del control de una fila a la siguiente, o de una columna a la siguiente. También puede recortar el contenido en lugar de ajustarlo.  
  
 Puede especificar la dirección de flujo estableciendo el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>. El control <xref:System.Windows.Forms.FlowLayoutPanel> invierte correctamente su dirección de flujo en diseños de derecha a izquierda (RTL). También puede especificar si el contenido del control <xref:System.Windows.Forms.FlowLayoutPanel> se ajustará o se recortará estableciendo el valor de la propiedad <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A>.  
  
 El control <xref:System.Windows.Forms.FlowLayoutPanel> ajusta automáticamente su tamaño al contenido cuando la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A> se establece en `true`. También proporciona un **FlowBreak** propiedad a sus controles secundarios. Al establecer el valor de la propiedad FlowBreak en `true` , el control <xref:System.Windows.Forms.FlowLayoutPanel> deja de distribuir los controles en la dirección del flujo actual y ajusta a la siguiente fila o columna.  
  
 Cualquier control de Windows Forms puede ser un control secundario del control <xref:System.Windows.Forms.FlowLayoutPanel>, incluidas otras instancias de <xref:System.Windows.Forms.FlowLayoutPanel>. Con esta funcionalidad, puede construir diseños sofisticados que se adapten a las dimensiones del formulario en tiempo de ejecución.  
  
 Consulte también [Tutorial: organizar controles en Windows Forms mediante FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [FlowLayoutPanel (control)](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-windows-forms.md)
