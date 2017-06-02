---
title: "Per&#237;odo de detecci&#243;n de instancias ejecutables | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Per&#237;odo de detecci&#243;n de instancias ejecutables
El almacén de instancias de flujo de trabajo de SQL ejecuta una tarea interna que se inicia periódicamente y que detecta instancias de flujo de trabajo ejecutables o activables en la base de datos de persistencia.La propiedad **Período de detección de instancias ejecutables** del almacén de instancias de flujo de trabajo de SQL especifica el período de tiempo transcurrido el cual este almacén ejecuta una tarea de detección para detectar cualquier instancia de flujo de trabajo ejecutable o activable en la base de datos de persistencia después del ciclo de detección anterior.  
  
 Al establecer un intervalo más corto para esta propiedad, se reduce el tiempo entre la expiración de un temporizador asociado a una instancia de flujo de trabajo y la señal del evento y la posterior carga de la instancia.Sin embargo, también aumenta la carga de procesamiento en un host y puede no ser aconsejable en escenarios donde los temporizadores de larga duración o los errores del host son escasos.El tipo de la propiedad es TimeSpan y su valor sigue el formato: hh:mm:ss.El valor mínimo de esta propiedad es 00:00:01.El valor predeterminado de la propiedad es 00:00:05.  
  
 Para obtener más información sobre la detección y activación de instancias de flujo de trabajo ejecutables y activables, vea [Activación de instancias](../../../docs/framework/windows-workflow-foundation//instance-activation.md).