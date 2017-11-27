---
title: "Información general sobre el componente Timer (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ea78cadae6e033bc54274e5428ba5e8c6410259d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="timer-component-overview-windows-forms"></a>Información general sobre el componente Timer (formularios Windows Forms)
El componente <xref:System.Windows.Forms.Timer> de Windows Forms produce un evento a intervalos regulares. Este componente está diseñado para un entorno de Windows Forms. Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="key-properties-methods-and-events"></a>Eventos, métodos y propiedades clave  
 La longitud de los intervalos está definida por el <xref:System.Windows.Forms.Timer.Interval%2A> propiedad, cuyo valor se expresa en milisegundos. Cuando el componente está habilitado, el <xref:System.Windows.Forms.Timer.Tick> evento se desencadena cada intervalo. Esto es donde puede agregar código que se ejecute. Para obtener más información, consulte [Cómo: ejecutar procedimientos a intervalos establecido con el componente Timer de formularios Windows Forms](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md). Los métodos principales de la <xref:System.Windows.Forms.Timer> componente <xref:System.Windows.Forms.Timer.Start%2A> y <xref:System.Windows.Forms.Timer.Stop%2A>, que activar el temporizador y desactivar. Cuando el temporizador está desactivado, se reinicia; No hay ninguna manera de poner en pausa un <xref:System.Windows.Forms.Timer> componente.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Timer>  
 [Timer (componente)](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
