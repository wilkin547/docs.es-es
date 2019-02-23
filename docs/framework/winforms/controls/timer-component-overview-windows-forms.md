---
title: Información general sobre el componente Timer (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: e92a8028fd532a7c3a44eba7a41799b7344a82df
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746554"
---
# <a name="timer-component-overview-windows-forms"></a>Información general sobre el componente Timer (formularios Windows Forms)
El componente <xref:System.Windows.Forms.Timer> de Windows Forms produce un evento a intervalos regulares. Este componente está diseñado para un entorno de Windows Forms. Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="key-properties-methods-and-events"></a>Los eventos, métodos y propiedades de clave  
 La longitud de los intervalos se define mediante el <xref:System.Windows.Forms.Timer.Interval%2A> propiedad, cuyo valor se expresa en milisegundos. Cuando el componente está habilitado, el <xref:System.Windows.Forms.Timer.Tick> evento se desencadena cada intervalo. Esto es donde puede agregar código que se ejecutará. Para obtener más información, vea [Cómo: Ejecutar procedimientos a intervalos establecidos con el componente Timer de Windows Forms](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md). Los métodos clave de la <xref:System.Windows.Forms.Timer> componente son <xref:System.Windows.Forms.Timer.Start%2A> y <xref:System.Windows.Forms.Timer.Stop%2A>, que activa el temporizador y desactiva. Cuando el temporizador está desactivado, lo reinicia; No hay ninguna manera de pausar una <xref:System.Windows.Forms.Timer> componente.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.Timer>
- [Timer (componente)](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)
- [Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
