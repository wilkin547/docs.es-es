---
title: 'Cómo: Cambiar el retardo del componente ToolTip de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 20dcd941b142daa672312edb618a1c3e4597442d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530434"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>Cómo: Cambiar el retardo del componente ToolTip de formularios Windows Forms
Hay varios valores de retraso que se pueden establecer para un formulario Windows Forms <xref:System.Windows.Forms.ToolTip> componente. La unidad de medida para todas estas propiedades es milisegundos. El <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> propiedad determina cuánto tiempo debe apuntar el usuario en el control asociado para que aparezca en la cadena de información sobre herramientas. El <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> propiedad establece el número de milisegundos que tardan en aparecer cuando el mouse se desplace desde un control asociado a la información sobre herramientas a otra subsiguientes cadenas de información sobre herramientas. El <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> propiedad determina el período de tiempo que se muestra la cadena de información sobre herramientas. Puede establecer estos valores individualmente, o estableciendo el valor de la <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> propiedad; el retraso de otro propiedades se establecen basándose en el valor asignado a la <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> propiedad. Por ejemplo, cuando <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> se establece en un valor N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> se establece en N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> se establece en el valor de <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> dividido por cinco (o N/5) y <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> se establece en un valor que es cinco veces el valor de la <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> propiedad (o 5N).  
  
### <a name="to-set-the-delay"></a>Para establecer el retraso  
  
1.  Establezca las siguientes propiedades tal como se muestra en este ejemplo.  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [Establecer información sobre herramientas en controles de Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [ToolTip (componente)](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
