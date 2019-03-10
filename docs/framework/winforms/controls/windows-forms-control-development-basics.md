---
title: Fundamentos de desarrollo de controles de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
ms.openlocfilehash: 6a7009ead6ceba58c17579835d03254f259f8e51
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723076"
---
# <a name="windows-forms-control-development-basics"></a>Fundamentos de desarrollo de controles de formularios Windows Forms
Un control de Windows Forms es una clase que deriva directa o indirectamente de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. En la lista siguiente se describe escenarios comunes para desarrollar controles de formularios Windows Forms:  
  
-   Combinación de controles existentes para crear un control compuesto.  
  
     Los controles compuestos encapsulan una interfaz de usuario que se puede reutilizar como un control. Un ejemplo de un control compuesto es un control que consta de un cuadro de texto y un botón Restablecer. Los diseñadores visuales ofrecen una compatibilidad enriquecida para crear controles compuestos. Para crear un control compuesto, derive de <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>. La clase base <xref:System.Windows.Forms.UserControl> proporciona enrutamiento de teclado para los controles secundarios y permite a los controles secundarios para que funcione como un grupo. Para obtener más información, vea [Desarrollar un control de formularios Windows Forms compuesto](developing-a-composite-windows-forms-control.md).  
  
-   Ampliación de un control existente para personalizarlo o agregar a su funcionalidad.  
  
     Un botón cuyo color no se puede cambiar y un botón que tiene una propiedad adicional que realiza el seguimiento de cuántas veces se ha hecho clic son ejemplos de controles extendidos. Puede personalizar cualquier control de Windows Forms derivados de él y reemplazar o agregando propiedades, métodos y eventos.  
  
-   Creación de un control que no se combina ni extender los controles existentes.  
  
     En este escenario, derive el control de la clase base <xref:System.Windows.Forms.Control>. Puede agregar, así como invalidar las propiedades, métodos y eventos de la clase base. Para empezar, vea [Cómo: Desarrollar un Control de formularios de Windows Simple](how-to-develop-a-simple-windows-forms-control.md).  
  
 La clase base para controles de Windows Forms, <xref:System.Windows.Forms.Control>, proporciona la infraestructura necesaria para la presentación visual en aplicaciones de cliente basada en Windows. <xref:System.Windows.Forms.Control> Proporciona un identificador de ventana, controla el enrutamiento de mensajes y proporciona los eventos de interfaz de eventos del mouse y teclado, así como muchos otros usuarios. Proporciona un diseño avanzado y tiene propiedades específicas de presentación visual, como <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>y muchos otros. Además, proporciona seguridad, compatibilidad para subprocesos e interoperabilidad con controles ActiveX. Dado que la clase base proporciona gran parte de la infraestructura, es relativamente fácil desarrollar sus propios controles de Windows Forms.  
  
## <a name="see-also"></a>Vea también
- [Cómo: Desarrollar un Control de formularios de Windows Simple](how-to-develop-a-simple-windows-forms-control.md)
- [Desarrollar un control de formularios Windows Forms compuesto](developing-a-composite-windows-forms-control.md)
- [Cómo: Crear un Control de Windows Forms que muestre el progreso](how-to-create-a-windows-forms-control-that-shows-progress.md)
- [Variedades de controles personalizados](varieties-of-custom-controls.md)
