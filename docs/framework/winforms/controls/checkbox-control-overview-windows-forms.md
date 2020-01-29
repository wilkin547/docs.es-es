---
title: Información general sobre el control CheckBox
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: b42816cf1bc0ce1ab6db0a2a436b17b0d4370d59
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737095"
---
# <a name="checkbox-control-overview-windows-forms"></a>Información general sobre el control CheckBox (formularios Windows Forms)
El control de Windows Forms <xref:System.Windows.Forms.CheckBox> indica si una condición determinada está activada o desactivada. Normalmente se utiliza para presentar una selección Sí/No o Verdadero/Falso al usuario. Puede utilizar de controles de casilla en grupos para mostrar múltiples opciones de entre las que el usuario puede seleccionar una o más.  
  
 El control de casilla es similar al control de botón de radio en que cada se usa para indicar una selección realizada por el usuario. Difieren en que solo se puede seleccionar un botón de radio de un grupo a la vez. Con el control de casilla, sin embargo, se puede seleccionar cualquier número de casillas.  
  
 Una casilla puede estar conectada a elementos de una base de datos mediante el enlace de datos simple. Se pueden agrupar varias casillas mediante el control <xref:System.Windows.Forms.GroupBox>. Esto resulta útil para la apariencia visual y también para el diseño de la interfaz de usuario, ya que los controles agrupados se pueden mover juntos en el diseñador de formularios. Para obtener más información, vea [Windows Forms enlace de datos](../windows-forms-data-binding.md) y el [control GroupBox](groupbox-control-windows-forms.md).  
  
 El control <xref:System.Windows.Forms.CheckBox> tiene dos propiedades importantes, <xref:System.Windows.Forms.CheckBox.Checked%2A> y <xref:System.Windows.Forms.CheckBox.CheckState%2A>. La propiedad <xref:System.Windows.Forms.CheckBox.Checked%2A> devuelve `true` o `false`. La propiedad <xref:System.Windows.Forms.CheckBox.CheckState%2A> devuelve <xref:System.Windows.Forms.CheckState.Checked> o <xref:System.Windows.Forms.CheckState.Unchecked>; o bien, si la propiedad <xref:System.Windows.Forms.CheckBox.ThreeState%2A> está establecida en `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> también puede devolver <xref:System.Windows.Forms.CheckState.Indeterminate>. En el estado indeterminado, el cuadro se muestra con una apariencia atenuada para indicar que la opción no está disponible.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.CheckBox>
- [Establecer opciones con los controles CheckBox de formularios Windows Forms](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [Responder a clics en casillas de Windows Forms](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox (control)](checkbox-control-windows-forms.md)
