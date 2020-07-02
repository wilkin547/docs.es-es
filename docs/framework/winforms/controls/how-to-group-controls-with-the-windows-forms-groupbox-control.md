---
title: Agrupar controles con el control GroupBox
description: Aprenda a agrupar controles con el control Windows Forms GroupBox para que pueda crear una agrupación visual de elementos relacionados.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: f84c495a18f4ae5e04367f024a1e2849f1ed59f9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618069"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a>Procedimiento para agrupar controles con el control GroupBox de formularios Windows Forms
Windows Forms <xref:System.Windows.Forms.GroupBox> controles se usan para agrupar otros controles. Existen tres razones para agrupar los controles:  
  
- Para crear una agrupación visual de elementos de formulario relacionados para una interfaz de usuario clara.  
  
- Para crear la agrupación mediante programación (de botones de radio, por ejemplo).  
  
- Para mover los controles como una unidad en tiempo de diseño.  
  
### <a name="to-create-a-group-of-controls"></a>Para crear un grupo de controles  
  
1. Dibuje un <xref:System.Windows.Forms.GroupBox> control en un formulario.  
  
2. Agregue otros controles al cuadro de grupo y dibuje cada uno dentro del cuadro de grupo.  
  
     Si tiene controles existentes que desea incluir en un cuadro de grupo, puede seleccionar todos los controles, recortarlos en el portapapeles, seleccionar el <xref:System.Windows.Forms.GroupBox> control y, a continuación, pegarlos en el cuadro de grupo. También puede arrastrarlos al cuadro de grupo.  
  
3. Establezca la <xref:System.Windows.Forms.GroupBox.Text%2A> propiedad del cuadro de grupo en un título adecuado.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.GroupBox>
- [Control GroupBox](groupbox-control-windows-forms.md)
