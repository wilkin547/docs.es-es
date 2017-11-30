---
title: "Información general sobre el control CheckBox (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a154a3f639102e3f3e2acd62626379e12bbd1344
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="checkbox-control-overview-windows-forms"></a>Información general sobre el control CheckBox (formularios Windows Forms)
El control de Windows Forms <xref:System.Windows.Forms.CheckBox> indica si una condición determinada está activada o desactivada. Normalmente se utiliza para presentar una selección Sí/No o Verdadero/Falso al usuario. Puede utilizar de controles de casilla en grupos para mostrar múltiples opciones de entre las que el usuario puede seleccionar una o más.  
  
 El control de casilla de verificación es similar al control de botón de radio en que cada uno se utiliza para indicar una selección realizada por el usuario. Se diferencian en que se puede seleccionar solo un botón en un grupo de a la vez. Sin embargo, con el control de casilla de verificación, cualquier número de casillas de verificación puede ser seleccionado.  
  
 Una casilla de verificación puede estar conectada a los elementos de una base de datos mediante el enlace de datos simple. También puede agrupar varias casillas de verificación medio el <xref:System.Windows.Forms.GroupBox> control. Esto es útil para la apariencia visual y también para el diseño de la interfaz de usuario, ya que los controles agrupados pueden usarse conjuntamente en el Diseñador de formularios. Para obtener más información, consulte [enlace de datos en formularios Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md) y [GroupBox Control](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md).  
  
 El <xref:System.Windows.Forms.CheckBox> control tiene dos propiedades importantes, <xref:System.Windows.Forms.CheckBox.Checked%2A> y <xref:System.Windows.Forms.CheckBox.CheckState%2A>. El <xref:System.Windows.Forms.CheckBox.Checked%2A> propiedad devuelve `true` o `false`. El <xref:System.Windows.Forms.CheckBox.CheckState%2A> propiedad devuelve <xref:System.Windows.Forms.CheckState.Checked> o <xref:System.Windows.Forms.CheckState.Unchecked>; o bien, si la <xref:System.Windows.Forms.CheckBox.ThreeState%2A> propiedad está establecida en `true`, <xref:System.Windows.Forms.CheckBox.CheckState%2A> también pueden devolver <xref:System.Windows.Forms.CheckState.Indeterminate>. En el estado indeterminado, el cuadro se muestra con un aspecto atenuado para indicar que la opción está disponible.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.CheckBox>  
 [Establecer opciones con los controles CheckBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [Responder a clics en casillas de Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [CheckBox (control)](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
