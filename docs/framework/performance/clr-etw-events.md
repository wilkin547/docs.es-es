---
title: "CLR ETW Events | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CLR ETW events"
  - "ETW, common language runtime"
  - "ETW, CLR events"
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
caps.latest.revision: 45
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 45
---
# CLR ETW Events
Los temas de esta sección describen la traza de eventos para Windows \(ETW\).  Cada evento tiene asociados una palabra clave y un nivel, que se describen en el tema [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).  El CLR tiene dos proveedores para los eventos:  
  
-   El proveedor de runtime, que genera eventos, en función de las palabras clave \(categorías de eventos\) que están habilitadas.  El GUID del proveedor en tiempo de ejecución de CLR es e13c0d23\-ccbc\-4e12\-931b\-d9cc2eee27e4.  
  
-   El proveedor del informe detallado, que tiene usos específicos.  El GUID del proveedor de informe detallado de CLR es a669021c\-c450\-4609\-a035\-5af59af4df18.  
  
 Para obtener más información sobre los proveedores, vea [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md).  
  
## En esta sección  
 [Runtime Information Events](../../../docs/framework/performance/runtime-information-etw-events.md)  
 Captura información sobre el runtime, incluidos SKU, número de versión, manera en que se activó el runtime, parámetros de línea de comandos con los que se inició, el GUID \(si es aplicable\) y otra información pertinente.  
  
 [Exception Thrown\_V1 Event](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 Captura información sobre las excepciones que se producen.  
  
 [Contention Events](../../../docs/framework/performance/contention-etw-events.md)  
 Captura información sobre la contención para bloqueos del monitor o bloqueos nativos que se utilizan en el runtime.  
  
 [Thread Pool Events](../../../docs/framework/performance/thread-pool-etw-events.md)  
 Captura información sobre los grupos de subprocesos de trabajo y los grupos de subprocesos de E\/S.  
  
 [Loader Events](../../../docs/framework/performance/loader-etw-events.md)  
 Captura información sobre la carga y descarga de dominios de aplicación, ensamblados y módulos.  
  
 [Method Events](../../../docs/framework/performance/method-etw-events.md)  
 Captura información sobre los métodos CLR para la resolución del símbolo.  
  
 [Garbage Collection Events](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 Captura información relativa a la recolección de elementos no utilizados, para ayudar en el diagnóstico y la depuración.  
  
 [JIT Tracing Events](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 Captura información sobre la inclusión de Just\-In\-Time \(JIT\) y las llamadas de cola.  
  
 [Interop Events](../../../docs/framework/performance/interop-etw-events.md)  
 Captura información sobre la generación de código auxiliar del lenguaje intermedio de Microsoft \(MSIL\) y su almacenamiento en memoria caché.  
  
 [ARM Events](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 Captura información de diagnóstico detallada sobre el estado de un dominio de aplicación.  
  
 [Security Events](../../../docs/framework/performance/security-etw-events.md)  
 Captura información sobre el nombre seguro y la comprobación de Authenticode.  
  
 [Stack Event](../../../docs/framework/performance/stack-etw-event.md)  
 Captura información que se utiliza con otros eventos para generar trazas de pila una vez generado un evento.  
  
## Vea también  
 [Mejorar la optimización de depuración y de rendimiento con ETW](http://go.microsoft.com/fwlink/?LinkId=179696)   
 [Blog de rendimiento de Windows](http://go.microsoft.com/fwlink/?LinkId=179509)   
 [Controlling .NET Framework Logging](../../../docs/framework/performance/controlling-logging.md)   
 [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md)   
 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)   
 [ETW Events in the Common Language Runtime](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)