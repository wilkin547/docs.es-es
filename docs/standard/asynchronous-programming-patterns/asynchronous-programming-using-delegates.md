---
title: "Asynchronous Programming Using Delegates | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "BeginInvoke method"
  - "asynchronous programming, delegates"
  - "asynchronous delegates"
  - "calling synchronous methods in asynchronous manner"
  - "EndInvoke method"
  - "calling asynchronous methods"
  - "delegates [.NET Framework], asynchronous"
  - "synchronous calling in asynchronous manner"
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Asynchronous Programming Using Delegates
Los delegados permiten llamar a métodos sincrónicos de forma asincrónica.  Cuando se llama a un delegado sincrónicamente, el método `Invoke` llama al método de destino directamente en el subproceso actual.  Si se llama al método `BeginInvoke`, Common Language Runtime \(CLR\) coloca en cola la solicitud y devuelve inmediatamente el control al elemento que lo llamó.  El método de destino se llama asincrónicamente desde un subproceso del grupo de subprocesos.  El subproceso original, que envió la solicitud, puede continuar ejecutándose en paralelo con el método de destino.  Si se ha especificado un método de devolución de llamada en la llamada al método `BeginInvoke`, el método de devolución de llamada se llama cuando finaliza el método de destino.  En el método de devolución de llamada, el método `EndInvoke` obtiene el valor devuelto y cualquier parámetro de entrada y salida o de solo salida.  Si no se especifica ningún método de devolución de llamada al llamar a `BeginInvoke`, se puede llamar a `EndInvoke` desde el subproceso que llamó a `BeginInvoke`.  
  
> [!IMPORTANT]
>  Los compiladores deben emitir clases de delegados con los métodos `Invoke`, `BeginInvoke` y `EndInvoke` mediante la firma de delegados que especifique el usuario.  Los métodos `EndInvoke` y `BeginInvoke` deben representarse como nativos.  Debido a que estos métodos están marcados como nativos, Common Language Runtime proporciona automáticamente la implementación en el momento en que se carga la clase.  El cargador se asegura de que no se reemplazarán.  
  
## En esta sección  
 [Calling Synchronous Methods Asynchronously](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Describe el uso de los delegados para realizar llamadas asincrónicas a métodos ordinarios y proporciona ejemplos de código sencillos en los que se muestran los cuatro mecanismos que existen para esperar a que una llamada asincrónica devuelva datos.  
  
 [Ejemplo de programación de delegados asincrónicos](../Topic/Asynchronous%20Delegates%20Programming%20Sample.md)  
 Explica el uso de delegados para realizar llamadas asincrónicas en un ejemplo de código más complejo, en el que se factorizan números.  
  
## Secciones relacionadas  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 Describe la programación asincrónica con .NET Framework.  
  
## Vea también  
 <xref:System.Delegate>