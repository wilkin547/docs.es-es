---
title: Limitaciones de la propiedad Interval del componente Timer
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 15626a53f0541ff79e2098377d9dfdb4626ac155
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745231"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a>Limitaciones de la propiedad Interval del componente Timer de Windows Forms
El componente <xref:System.Windows.Forms.Timer> de Windows Forms tiene una propiedad <xref:System.Windows.Forms.Timer.Interval%2A> que especifica el número de milisegundos que transcurren entre un evento de temporizador y el siguiente. A menos que el componente esté deshabilitado, un temporizador sigue recibiendo el evento <xref:System.Windows.Forms.Timer.Tick> a intervalos de tiempo aproximadamente iguales.  
  
 Este componente está diseñado para un entorno de Windows Forms. Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="the-interval-property"></a>La propiedad Interval  
 La propiedad <xref:System.Windows.Forms.Timer.Interval%2A> tiene algunas limitaciones que se deben tener en cuenta al programar un componente <xref:System.Windows.Forms.Timer>:  
  
- Si su aplicación u otra aplicación está realizando demandas pesadas en el sistema (por ejemplo, bucles largos, cálculos intensivos o acceso de unidad, red o puerto), es posible que la aplicación no obtenga eventos de temporizador con la frecuencia que especifica la propiedad <xref:System.Windows.Forms.Timer.Interval%2A>.  
  
- No se garantiza que el intervalo transcurra exactamente en el tiempo. Para garantizar la precisión, el temporizador debe comprobar el reloj del sistema según sea necesario, en lugar de intentar realizar un seguimiento de la hora acumulada internamente.  
  
- La precisión de la propiedad <xref:System.Windows.Forms.Timer.Interval%2A> se encuentra en milisegundos. Algunos equipos proporcionan un contador de alta resolución que tiene una resolución superior a milisegundos. La disponibilidad de este contador depende del hardware del procesador del equipo.
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Timer>
- [Timer (componente)](timer-component-windows-forms.md)
- [Información general sobre el componente Timer](timer-component-overview-windows-forms.md)
