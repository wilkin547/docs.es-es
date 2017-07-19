---
title: "Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Interval (propiedad), limitaciones"
  - "Timer (componente) [Windows Forms], limitaciones de la propiedad Interval"
  - "temporizadores, intervalos de eventos"
  - "temporizadores, basados en Windows"
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms
El componente <xref:System.Windows.Forms.Timer> de formularios Windows Forms tiene una propiedad <xref:System.Windows.Forms.Timer.Interval%2A> que especifica el número de milisegundos que transcurren entre un evento del temporizador y el siguiente.  A menos que se deshabilite el componente, un temporizador continúa recibiendo el evento <xref:System.Windows.Forms.Timer.Tick> a intervalos de tiempo aproximadamente iguales.  
  
 Este componente está diseñado para un entorno de formularios Windows Forms.  Si necesita un temporizador que sea adecuado para un entorno de servidor, vea [Introduction to Server\-Based Timers](http://msdn.microsoft.com/es-es/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## La propiedad Interval  
 La propiedad <xref:System.Windows.Forms.Timer.Interval%2A> tiene algunas limitaciones que deben tenerse en cuenta al programar un componente <xref:System.Windows.Forms.Timer>:  
  
-   Si esta aplicación, o cualquier otra, está solicitando al sistema la realización de tareas pesadas, tales como bucles largos, cálculos intensivos o acceso al disco, a la red o a un puerto, es posible que la aplicación no obtenga los eventos del temporizador con tanta frecuencia como especifica la propiedad <xref:System.Windows.Forms.Timer.Interval%2A>.  
  
-   No se garantiza que el intervalo dure un tiempo exacto.  Para asegurar la precisión, el temporizador debe comprobar el reloj del sistema cuando sea necesario, en lugar de hacer un seguimiento del tiempo acumulado internamente.  
  
-   La precisión de la propiedad <xref:System.Windows.Forms.Timer.Interval%2A> se indica en milisegundos.  Algunos equipos proporcionan un contador de alta resolución con una resolución mayor que milisegundos.  La disponibilidad de este tipo de contador depende del hardware del procesador del equipo.  Para obtener más información, vea el artículo 172338 de Microsoft Knowledge Base, "How To Use QueryPerformanceCounter to Time Code", en http:\/\/support.microsoft.com.  
  
## Vea también  
 <xref:System.Windows.Forms.Timer>   
 [Timer](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)   
 [Información general sobre el componente Timer](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)