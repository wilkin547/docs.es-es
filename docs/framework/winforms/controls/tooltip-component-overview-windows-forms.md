---
title: Información general sobre el componente ToolTip (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 33a66e8ab5c8b09c5ed3dcf9dc60810a42d4d05d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724042"
---
# <a name="tooltip-component-overview-windows-forms"></a>Información general sobre el componente ToolTip (formularios Windows Forms)
El componente <xref:System.Windows.Forms.ToolTip> de Windows Forms muestra texto cuando el usuario apunta a otros controles. Un componente Tooltip se puede asociar con cualquier control. Un ejemplo del uso de este componente: para ahorrar espacio en un formulario, puede mostrar un pequeño icono en un botón y utilizar un componente ToolTip para explicar la función del botón.  
  
## <a name="working-with-the-tooltip-component"></a>Trabajar con el componente ToolTip  
 Un <xref:System.Windows.Forms.ToolTip> componente proporciona una `ToolTip` propiedad para varios controles en un formulario de Windows o en otro contenedor. Por ejemplo, si coloca uno <xref:System.Windows.Forms.ToolTip> componente en un formulario, puede mostrar "Escriba aquí su nombre" para un <xref:System.Windows.Forms.TextBox> controlar y "Haga clic aquí para guardar los cambios" para un <xref:System.Windows.Forms.Button> control.  
  
 Los métodos clave de la <xref:System.Windows.Forms.ToolTip> componente son <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> y <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>. Puede usar el <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método para establecer la información sobre herramientas muestra para los controles. Para obtener más información, vea [Cómo: Establecer componentes ToolTip en controles de Windows Forms en tiempo de diseño](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md). Las propiedades claves son <xref:System.Windows.Forms.ToolTip.Active%2A>, que debe establecerse en `true` para la información sobre herramientas que se muestre y <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, que establece el período de tiempo que se muestra la cadena de información sobre herramientas, ¿cuánto tiempo debe apuntar el usuario en el control de la información sobre herramientas que se muestre y el modo de tiempo que toma de las ventanas que aparezca información sobre herramientas posteriores. Para obtener más información, vea [Cómo: Cambiar el retardo del componente ToolTip de formularios Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ToolTip>
- [Cómo: Establecer componentes ToolTip en controles de Windows Forms en tiempo de diseño](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [Cómo: Cambiar el retardo del componente ToolTip de formularios Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
