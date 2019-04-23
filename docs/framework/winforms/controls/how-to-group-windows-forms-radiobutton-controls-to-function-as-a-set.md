---
title: Procedimiento para agrupar controles RadioButton de formularios Windows Forms para que funcionen como un conjunto
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: 857e61bc89e072aebcf34793d7e8504ece3318c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307276"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Procedimiento para agrupar controles RadioButton de formularios Windows Forms para que funcionen como un conjunto
Windows Forms <xref:System.Windows.Forms.RadioButton> controles están diseñados para proporcionar a los usuarios una opción entre dos o más configuraciones, de los cuales sólo uno puede asignarse a un procedimiento u objeto. Por ejemplo, un grupo de <xref:System.Windows.Forms.RadioButton> controles pueden mostrar una serie de transporte para un pedido, pero solo uno de los transportistas se usará. Por lo tanto, solo un <xref:System.Windows.Forms.RadioButton> a la vez puede seleccionarse, incluso si forma parte de un grupo funcional.  
  
 Agrupar botones de radio, dibuje dentro de un contenedor, como un <xref:System.Windows.Forms.Panel> (control), un <xref:System.Windows.Forms.GroupBox> control o formulario. Todos los botones de radio que se agregan directamente a un grupo de un formulario se convierten en. Para agregar grupos independientes, debe colocarlos dentro de paneles o cuadros de grupo. Para obtener más información acerca de los paneles o cuadros de grupo, consulte [información general del Control Panel](panel-control-overview-windows-forms.md) o [información general del Control GroupBox](groupbox-control-overview-windows-forms.md).  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>Para agrupar controles RadioButton en un conjunto para que funcionen de forma independiente  
  
1. Arrastre un <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> controlar desde la **Windows Forms** ficha la **cuadro de herramientas** hasta el formulario.  
  
2. Dibujar <xref:System.Windows.Forms.RadioButton> a los controles de la <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> control.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.RadioButton>
- [Información general sobre el control RadioButton](radiobutton-control-overview-windows-forms.md)
- [Información general del control Panel](panel-control-overview-windows-forms.md)
- [Información general sobre el control GroupBox](groupbox-control-overview-windows-forms.md)
- [Información general sobre el control CheckBox](checkbox-control-overview-windows-forms.md)
- [RadioButton (control)](radiobutton-control-windows-forms.md)
