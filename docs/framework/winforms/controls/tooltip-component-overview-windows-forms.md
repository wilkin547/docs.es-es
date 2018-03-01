---
title: "Información general sobre el componente ToolTip (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fce1cb5750197e52461b4883f1238325fa10fc5e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="tooltip-component-overview-windows-forms"></a>Información general sobre el componente ToolTip (formularios Windows Forms)
El componente <xref:System.Windows.Forms.ToolTip> de Windows Forms muestra texto cuando el usuario apunta a otros controles. Un componente Tooltip se puede asociar con cualquier control. Un ejemplo del uso de este componente: para ahorrar espacio en un formulario, puede mostrar un pequeño icono en un botón y utilizar un componente ToolTip para explicar la función del botón.  
  
## <a name="working-with-the-tooltip-component"></a>Trabajar con el componente ToolTip  
 A <xref:System.Windows.Forms.ToolTip> componente proporciona un `ToolTip` propiedad para varios controles en un formulario Windows Forms o en otro contenedor. Por ejemplo, si coloca uno <xref:System.Windows.Forms.ToolTip> componente en un formulario, puede mostrar "Escriba aquí el nombre" para un <xref:System.Windows.Forms.TextBox> controlar y "Haga clic aquí para guardar los cambios" para un <xref:System.Windows.Forms.Button> control.  
  
 Los métodos principales de la <xref:System.Windows.Forms.ToolTip> componente <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> y <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>. Puede usar el <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método para establecer la información sobre herramientas muestra para los controles. Para obtener más información, consulte [Cómo: establecer información sobre herramientas para controles en un formulario Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md). Las propiedades claves son <xref:System.Windows.Forms.ToolTip.Active%2A>, que debe establecerse en `true` para la información sobre herramientas que se muestre y <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, que establece el período de tiempo que se muestra la cadena de información sobre herramientas, cuánto tiempo debe apuntar el usuario en el control de la información sobre herramientas que se muestre y cómo tiempo que toma de la siguiente ventana de información sobre herramientas que aparezca. Para obtener más información, consulte [Cómo: cambiar el retardo del componente ToolTip de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolTip>  
 [Establecer información sobre herramientas en controles de Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [Cambiar el retardo del componente ToolTip de Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
