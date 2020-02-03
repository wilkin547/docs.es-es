---
title: Información general sobre el componente Timer
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 83b52d395cdc3e3357bcf83517eab258a5c8ae08
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742774"
---
# <a name="timer-component-overview-windows-forms"></a>Información general sobre el componente Timer (Windows Forms)
El componente <xref:System.Windows.Forms.Timer> de Windows Forms produce un evento a intervalos regulares. Este componente está diseñado para un entorno de Windows Forms. Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="key-properties-methods-and-events"></a>Propiedades, métodos y eventos clave  
 La longitud de los intervalos se define mediante la propiedad <xref:System.Windows.Forms.Timer.Interval%2A>, cuyo valor se encuentra en milisegundos. Cuando el componente está habilitado, el evento de <xref:System.Windows.Forms.Timer.Tick> se genera cada intervalo. Aquí es donde agregaría el código que se va a ejecutar. Para obtener más información, consulte [Cómo: ejecutar procedimientos a intervalos establecidos con el componente Timer de Windows Forms](run-procedures-at-set-intervals-with-wf-timer-component.md). Los métodos clave del componente <xref:System.Windows.Forms.Timer> son <xref:System.Windows.Forms.Timer.Start%2A> y <xref:System.Windows.Forms.Timer.Stop%2A>, lo que activa y desactiva el temporizador. Cuando el temporizador se desactiva, se restablece; no hay ninguna manera de pausar un componente de <xref:System.Windows.Forms.Timer>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Timer>
- [Timer (componente)](timer-component-windows-forms.md)
- [Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms](limitations-of-the-timer-component-interval-property.md)
