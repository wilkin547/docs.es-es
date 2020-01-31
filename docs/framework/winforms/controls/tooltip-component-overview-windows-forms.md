---
title: Información general sobre el componente ToolTip
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 731f7ad0ce6670000d8c3d3e901e1506f7ef470a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741906"
---
# <a name="tooltip-component-overview-windows-forms"></a>Información general sobre el componente ToolTip (formularios Windows Forms)
El componente <xref:System.Windows.Forms.ToolTip> de Windows Forms muestra texto cuando el usuario apunta a otros controles. Un componente Tooltip se puede asociar con cualquier control. Un ejemplo de uso de este componente: para ahorrar espacio en un formulario, puede mostrar un pequeño icono en un botón y usar una información sobre herramientas para explicar la función del botón.  
  
## <a name="working-with-the-tooltip-component"></a>Trabajar con el componente ToolTip  
 Un componente de <xref:System.Windows.Forms.ToolTip> proporciona una propiedad `ToolTip` a varios controles en un Windows Form o en otro contenedor. Por ejemplo, si coloca una <xref:System.Windows.Forms.ToolTip> componente en un formulario, puede mostrar "Escriba aquí su nombre" para un control <xref:System.Windows.Forms.TextBox> y "haga clic aquí para guardar los cambios" de un control <xref:System.Windows.Forms.Button>.  
  
 Los métodos clave del componente <xref:System.Windows.Forms.ToolTip> son <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> y <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>. Puede usar el método <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> para establecer la información sobre herramientas que se muestra para los controles. Para obtener más información, vea [Cómo: establecer información sobre herramientas para controles de Windows Forms en tiempo de diseño](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md). Las propiedades clave son <xref:System.Windows.Forms.ToolTip.Active%2A>, que se deben establecer en `true` para que aparezca la información sobre herramientas y <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, que establece el período de tiempo durante el que se muestra la cadena de información sobre herramientas, cuánto tiempo debe apuntar el usuario al control para que aparezca la información sobre herramientas y cuánto tiempo tardan en aparecer las ventanas de información sobre herramientas posteriores. Para obtener más información, consulte [Cómo: cambiar el retardo del componente de información sobre herramientas de Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolTip>
- [Establecer información sobre herramientas en controles de Windows Forms en tiempo de diseño](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [Cambiar el retardo del componente ToolTip de Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
