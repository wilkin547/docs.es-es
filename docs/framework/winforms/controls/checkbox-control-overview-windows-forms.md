---
title: Información general sobre el control CheckBox (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: 003e57db16c35b519d3948fc24e82a94a5c3744d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713454"
---
# <a name="checkbox-control-overview-windows-forms"></a>Información general sobre el control CheckBox (formularios Windows Forms)
El control de Windows Forms <xref:System.Windows.Forms.CheckBox> indica si una condición determinada está activada o desactivada. Normalmente se utiliza para presentar una selección Sí/No o Verdadero/Falso al usuario. Puede utilizar de controles de casilla en grupos para mostrar múltiples opciones de entre las que el usuario puede seleccionar una o más.  
  
 El control de casilla de verificación es similar al control de botón de radio en que cada uno se utiliza para indicar una selección realizada por el usuario. Se diferencian en que se puede seleccionar sólo un botón en un grupo a la vez. Con el control de casilla de verificación, sin embargo, cualquier número de casillas de verificación se puede seleccionar.  
  
 Una casilla de verificación puede estar conectada a los elementos de una base de datos mediante el enlace de datos simple. Se puede agrupar varias casillas de verificación mediante el <xref:System.Windows.Forms.GroupBox> control. Esto es útil para la apariencia visual y también para el diseño de la interfaz de usuario, puesto que los controles agrupados se puedan mover juntos en el Diseñador de formularios. Para obtener más información, consulte [Windows Forms Data Binding](../windows-forms-data-binding.md) y [GroupBox Control](groupbox-control-windows-forms.md).  
  
 El <xref:System.Windows.Forms.CheckBox> control tiene dos propiedades importantes, <xref:System.Windows.Forms.CheckBox.Checked%2A> y <xref:System.Windows.Forms.CheckBox.CheckState%2A>. El <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad devuelve `true` o `false`. El <xref:System.Windows.Forms.CheckBox.CheckState%2A> propiedad devuelve <xref:System.Windows.Forms.CheckState.Checked> o <xref:System.Windows.Forms.CheckState.Unchecked>; o bien, si la <xref:System.Windows.Forms.CheckBox.ThreeState%2A> propiedad está establecida en `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> también pueden devolver <xref:System.Windows.Forms.CheckState.Indeterminate>. En el estado indeterminado, se muestra el cuadro con un aspecto atenuado para indicar que la opción está disponible.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.CheckBox>
- [Cómo: Establecer opciones con controles CheckBox de formularios de Windows](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [Cómo: Responder a Windows Forms clics en casillas](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox (control)](checkbox-control-windows-forms.md)
