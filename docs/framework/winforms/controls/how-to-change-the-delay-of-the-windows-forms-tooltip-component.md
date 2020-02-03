---
title: Cambiar el retraso del componente ToolTip
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
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746586"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>Cómo: Cambiar el retardo del componente ToolTip de formularios Windows Forms
Hay varios valores de retraso que puede establecer para un componente de <xref:System.Windows.Forms.ToolTip> de Windows Forms. La unidad de medida para todas estas propiedades es de milisegundos. La propiedad <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> determina cuánto tiempo debe apuntar el usuario al control asociado para que aparezca la cadena de información sobre herramientas. La propiedad <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> establece el número de milisegundos que tardan en aparecer las siguientes cadenas de información sobre herramientas cuando el mouse se mueve de un control asociado a la información sobre herramientas a otro. La propiedad <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> determina la cantidad de tiempo que se muestra la cadena de información sobre herramientas. Puede establecer estos valores individualmente o estableciendo el valor de la propiedad <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>; las demás propiedades de retraso se establecen en función del valor asignado a la propiedad <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>. Por ejemplo, cuando <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> está establecido en un valor N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> se establece en N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> se establece en el valor de <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> dividido entre cinco (o N/5) y <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> se establece en un valor que es cinco veces el valor de la propiedad <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> (o cantidad 5 veces).  
  
### <a name="to-set-the-delay"></a>Para establecer el retraso  
  
1. Establezca las siguientes propiedades como se muestra en este ejemplo.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Información general sobre el componente ToolTip](tooltip-component-overview-windows-forms.md)
- [Establecer información sobre herramientas en controles de Windows Forms en tiempo de diseño](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [ToolTip (componente)](tooltip-component-windows-forms.md)
