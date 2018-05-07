---
title: Fundamentos de desarrollo de controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
ms.openlocfilehash: b455912468376d2f5de0ac1f30b4fcab5bb93309
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-control-development-basics"></a>Fundamentos de desarrollo de controles de formularios Windows Forms
Un control de formularios Windows Forms es una clase que deriva directa o indirectamente de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. En la lista siguiente se describe escenarios comunes para desarrollar controles de formularios Windows Forms:  
  
-   Combinación de controles existentes para crear un control compuesto.  
  
     Controles compuestos encapsulan una interfaz de usuario que se puede reutilizar como un control. Un ejemplo de un control compuesto es un control que consta de un cuadro de texto y un botón Restablecer. Los diseñadores visuales ofrecen compatibilidad enriquecida para crear controles compuestos. Para crear un control compuesto, derive de <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>. La clase base <xref:System.Windows.Forms.UserControl> proporciona el enrutamiento de teclado para secundarios controlan y permite a los controles secundarios para que funcione como un grupo. Para obtener más información, vea [Desarrollar un control de formularios Windows Forms compuesto](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md).  
  
-   Extender un control existente para personalizarlo o para agregarlos a su funcionalidad.  
  
     Un botón cuyo color no se puede cambiar y un botón que tiene una propiedad adicional que realiza el seguimiento de cuántas veces se ha hecho clic son ejemplos de controles extendidos. Puede personalizar cualquier control de formularios Windows Forms derivados de él y reemplazando o agregando propiedades, métodos y eventos.  
  
-   Crear un control que no lo hace, se combinan o ampliar los controles existentes.  
  
     En este escenario, derive el control de la clase base <xref:System.Windows.Forms.Control>. Puede agregar, así como invalidar las propiedades, métodos y eventos de la clase base. Para empezar, vea [Cómo: desarrollar un Control de Windows Forms Simple](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).  
  
 La clase base para los controles de formularios Windows Forms, <xref:System.Windows.Forms.Control>, proporciona la infraestructura necesaria para la presentación visual en aplicaciones basadas en Windows del lado cliente. <xref:System.Windows.Forms.Control> Proporciona un identificador de ventana, controla el enrutamiento de mensajes y proporciona eventos de teclado y mouse (ratón), así como muchos otro usuario eventos de interfaz. Proporciona diseño avanzado y tiene propiedades específicas de presentación visual, como <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>y muchas otras. Además, proporciona seguridad, compatibilidad para subprocesos e interoperabilidad con controles ActiveX. Dado que la clase base proporciona gran parte de la infraestructura, es relativamente fácil desarrollar sus propios controles de Windows Forms.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar un control de formularios Windows Forms sencillo](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)  
 [Desarrollar un control de formularios Windows Forms compuesto](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)  
 [Crear un control de formularios Windows Forms que muestre el progreso](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)  
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
