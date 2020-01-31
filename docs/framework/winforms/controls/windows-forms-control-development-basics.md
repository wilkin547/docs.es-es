---
title: Aspectos básicos para desarrollar controles
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
ms.openlocfilehash: fab0a76e2f9fdb7e2f89e9d6a10dd9c522a6d8e1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739922"
---
# <a name="windows-forms-control-development-basics"></a>Fundamentos de desarrollo de controles de Windows Forms
Un control Windows Forms es una clase que deriva directa o indirectamente de <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. En la lista siguiente se describen escenarios comunes para desarrollar controles de Windows Forms:  
  
- Combinar controles existentes para crear un control compuesto.  
  
     Los controles compuestos encapsulan una interfaz de usuario que se puede reutilizar como control. Un ejemplo de un control compuesto es un control que consta de un cuadro de texto y un botón de restablecimiento. Los diseñadores visuales ofrecen compatibilidad enriquecida para crear controles compuestos. Para crear un control compuesto, derive de <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>. La clase base <xref:System.Windows.Forms.UserControl> proporciona el enrutamiento de teclado para los controles secundarios y permite que los controles secundarios funcionen como un grupo. Para obtener más información, vea [Desarrollar un control de formularios Windows Forms compuesto](developing-a-composite-windows-forms-control.md).  
  
- Extender un control existente para personalizarlo o agregarlo a su funcionalidad.  
  
     Un botón cuyo color no se puede cambiar y un botón que tiene una propiedad adicional que realiza un seguimiento del número de veces que se ha realizado el clic son ejemplos de controles extendidos. Puede personalizar cualquier control de Windows Forms derivando de él e invalidando o agregando propiedades, métodos y eventos.  
  
- Crear un control que no combine ni extienda los controles existentes.  
  
     En este escenario, derive el control de la clase base <xref:System.Windows.Forms.Control>. Puede Agregar e invalidar propiedades, métodos y eventos de la clase base. Para empezar, consulte [Cómo: desarrollar un control de Windows Forms simple](how-to-develop-a-simple-windows-forms-control.md).  
  
 La clase base para los controles de Windows Forms, <xref:System.Windows.Forms.Control>, proporciona la infraestructura necesaria para la presentación visual en aplicaciones basadas en Windows del cliente. <xref:System.Windows.Forms.Control> proporciona un identificador de ventana, controla el enrutamiento de mensajes y proporciona eventos del mouse y del teclado, así como muchos otros eventos de la interfaz de usuario. Proporciona un diseño avanzado y tiene propiedades específicas para la presentación visual, como <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>y muchas otras. Además, proporciona compatibilidad con la seguridad, los subprocesos y la interoperabilidad con los controles ActiveX. Dado que la clase base proporciona gran parte de la infraestructura, es relativamente fácil desarrollar sus propios controles de Windows Forms.  
  
## <a name="see-also"></a>Vea también

- [Desarrollar un control de formularios Windows Forms sencillo](how-to-develop-a-simple-windows-forms-control.md)
- [Desarrollar un control de formularios Windows Forms compuesto](developing-a-composite-windows-forms-control.md)
- [Crear un control de formularios Windows Forms que muestre el progreso](how-to-create-a-windows-forms-control-that-shows-progress.md)
- [Variedades de controles personalizados](varieties-of-custom-controls.md)
