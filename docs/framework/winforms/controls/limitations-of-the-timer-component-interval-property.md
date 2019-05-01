---
title: Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 54782c4e0460ba1ba9b8a870b8f60f08a76340b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012846"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a>Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms
Los formularios de Windows <xref:System.Windows.Forms.Timer> componente tiene un <xref:System.Windows.Forms.Timer.Interval%2A> propiedad que especifica el número de milisegundos que transcurren entre un evento del temporizador y el siguiente. A menos que el componente está deshabilitado, un temporizador continúa recibiendo el <xref:System.Windows.Forms.Timer.Tick> eventos a intervalos de tiempo aproximadamente iguales.  
  
 Este componente está diseñado para un entorno de Windows Forms. Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="the-interval-property"></a>La propiedad Interval  
 El <xref:System.Windows.Forms.Timer.Interval%2A> propiedad tiene algunas limitaciones a tener en cuenta al programar un <xref:System.Windows.Forms.Timer> componente:  
  
- Si la aplicación u otra aplicación está realizando fuertes exigencias del sistema, como bucles largos, cálculos intensivos o unidad, red o acceso a los puertos, la aplicación no es posible que obtenga los eventos del temporizador con tanta frecuencia como los <xref:System.Windows.Forms.Timer.Interval%2A> especifica la propiedad.  
  
- El intervalo no se garantiza que transcurran exactamente en el tiempo. Para garantizar la precisión, el temporizador debe comprobar el reloj del sistema según sea necesario, en lugar de intentar realizar un seguimiento del tiempo acumulado internamente.  
  
- La precisión de la <xref:System.Windows.Forms.Timer.Interval%2A> propiedad está en milisegundos. Algunos equipos proporcionan un contador de alta resolución que tenga una resolución mayor que milisegundos. La disponibilidad de este tipo de contador depende del hardware del procesador del equipo.
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Timer>
- [Timer (componente)](timer-component-windows-forms.md)
- [Información general sobre el componente Timer](timer-component-overview-windows-forms.md)
