---
title: "Informaci&#243;n general sobre el componente Timer (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Timer"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Timer (componente) [Windows Forms], acerca de los componentes Timer"
  - "temporizadores, acerca de temporizadores"
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Informaci&#243;n general sobre el componente Timer (formularios Windows Forms)
El componente <xref:System.Windows.Forms.Timer> de formularios Windows Forms produce un evento a intervalos regulares.  Este componente está diseñado para un entorno de formularios Windows Forms.  Si necesita un temporizador que sea adecuado para un entorno de servidor, vea [Introduction to Server\-Based Timers](http://msdn.microsoft.com/es-es/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## Propiedades, métodos y eventos principales  
 La longitud de los intervalos está definida por la propiedad <xref:System.Windows.Forms.Timer.Interval%2A>, cuyo valor se expresa en milisegundos.  Cuando el componente está habilitado, el evento <xref:System.Windows.Forms.Timer.Tick> se produce a cada intervalo.  Aquí es donde se agrega el código que se va a ejecutar.  Para obtener más información, vea [Cómo: Ejecutar procedimientos a intervalos establecidos con el componente Timer de formularios Windows Forms](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).  Los métodos principales del componente <xref:System.Windows.Forms.Timer> son <xref:System.Windows.Forms.Timer.Start%2A> y <xref:System.Windows.Forms.Timer.Stop%2A>, que activan y desactivan el temporizador.  Cuando el temporizador está desactivado, se reinicia; no hay modo de hacer una pausa en un componente <xref:System.Windows.Forms.Timer>.  
  
## Vea también  
 <xref:System.Windows.Forms.Timer>   
 [Timer](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)   
 [Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)