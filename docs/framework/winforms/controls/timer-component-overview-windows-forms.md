---
title: Información general sobre el componente Timer (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 6e453f6b7718c6c5be3109f51153a3f5e4b5b6f4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43733734"
---
# <a name="timer-component-overview-windows-forms"></a>Información general sobre el componente Timer (formularios Windows Forms)
El componente <xref:System.Windows.Forms.Timer> de Windows Forms produce un evento a intervalos regulares. Este componente está diseñado para un entorno de Windows Forms. Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="key-properties-methods-and-events"></a>Los eventos, métodos y propiedades de clave  
 La longitud de los intervalos se define mediante el <xref:System.Windows.Forms.Timer.Interval%2A> propiedad, cuyo valor se expresa en milisegundos. Cuando el componente está habilitado, el <xref:System.Windows.Forms.Timer.Tick> evento se desencadena cada intervalo. Esto es donde puede agregar código que se ejecutará. Para obtener más información, consulte [Cómo: ejecutar procedimientos a intervalos establecido con el componente de temporizador de Windows Forms](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md). Los métodos clave de la <xref:System.Windows.Forms.Timer> componente son <xref:System.Windows.Forms.Timer.Start%2A> y <xref:System.Windows.Forms.Timer.Stop%2A>, que activa el temporizador y desactiva. Cuando el temporizador está desactivado, lo reinicia; No hay ninguna manera de pausar una <xref:System.Windows.Forms.Timer> componente.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Timer>  
 [Timer (componente)](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
