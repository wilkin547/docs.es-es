---
title: Agrupar controles con el control GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: bb7476c410d2802b5d32cc9842a778f290765e32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736658"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a>Cómo: Agrupar controles con el control GroupBox de formularios Windows Forms
Windows Forms <xref:System.Windows.Forms.GroupBox> controles se usan para agrupar otros controles. Existen tres razones para agrupar los controles:  
  
- Para crear una agrupación visual de elementos de formulario relacionados para una interfaz de usuario clara.  
  
- Para crear la agrupación mediante programación (de botones de radio, por ejemplo).  
  
- Para mover los controles como una unidad en tiempo de diseño.  
  
### <a name="to-create-a-group-of-controls"></a>Para crear un grupo de controles  
  
1. Dibuja un control de <xref:System.Windows.Forms.GroupBox> en un formulario.  
  
2. Agregue otros controles al cuadro de grupo y dibuje cada uno dentro del cuadro de grupo.  
  
     Si tiene controles existentes que desea incluir en un cuadro de grupo, puede seleccionar todos los controles, recortarlos en el portapapeles, seleccionar el control de <xref:System.Windows.Forms.GroupBox> y, a continuación, pegarlos en el cuadro de grupo. También puede arrastrarlos al cuadro de grupo.  
  
3. Establezca la propiedad <xref:System.Windows.Forms.GroupBox.Text%2A> del cuadro de grupo en un título adecuado.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.GroupBox>
- [GroupBox (control)](groupbox-control-windows-forms.md)
