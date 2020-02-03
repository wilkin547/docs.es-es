---
title: Agrupar controles RadioButton para que funcionen como un conjunto
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: c4b37c84bf0f93837b91c743c7681d39fd83a659
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732954"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>Cómo: Agrupar controles RadioButton de formularios Windows Forms para que funcionen como un conjunto
Windows Forms <xref:System.Windows.Forms.RadioButton> controles están diseñados para proporcionar a los usuarios una opción entre dos o más configuraciones, de las cuales solo se puede asignar una a un procedimiento u objeto. Por ejemplo, un grupo de <xref:System.Windows.Forms.RadioButton> controles puede mostrar una selección de operadores de paquetes para un pedido, pero solo se usará uno de los operadores. Por lo tanto, solo se puede seleccionar una <xref:System.Windows.Forms.RadioButton> cada vez, incluso si forma parte de un grupo funcional.  
  
 Para agrupar los botones de radio, puede dibujarlos dentro de un contenedor como, por ejemplo, un control de <xref:System.Windows.Forms.Panel>, un control de <xref:System.Windows.Forms.GroupBox> o un formulario. Todos los botones de radio que se agregan directamente a un formulario se convierten en un grupo. Para agregar grupos independientes, debe colocarlos dentro de paneles o cuadros de grupo. Para obtener más información sobre los paneles o cuadros de grupo, vea información general sobre el [control panel](panel-control-overview-windows-forms.md) o [información general sobre el control GroupBox](groupbox-control-overview-windows-forms.md).  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>Para agrupar los controles RadioButton como un conjunto para que funcionen de forma independiente de otros conjuntos  
  
1. Arrastre un control <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel> desde la pestaña **Windows Forms** del **cuadro de herramientas** hasta el formulario.  
  
2. Dibuje controles <xref:System.Windows.Forms.RadioButton> en el control <xref:System.Windows.Forms.GroupBox> o <xref:System.Windows.Forms.Panel>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.RadioButton>
- [Información general sobre el control RadioButton](radiobutton-control-overview-windows-forms.md)
- [Información general del control Panel](panel-control-overview-windows-forms.md)
- [Información general sobre el control GroupBox](groupbox-control-overview-windows-forms.md)
- [Información general sobre el control CheckBox](checkbox-control-overview-windows-forms.md)
- [RadioButton (control)](radiobutton-control-windows-forms.md)
