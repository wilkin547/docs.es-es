---
title: "Timers | Microsoft Docs"
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
  - "threading [.NET Framework], timers"
  - "timers, about timers"
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Timers
Los temporizadores son objetos pequeños que permiten especificar un delegado para llamarlo en un momento específico.  Un subproceso del grupo realiza la operación de espera.  
  
 El uso de la clase <xref:System.Threading.Timer?displayProperty=fullName> es sencillo.  Para crear un **Timer**, debe pasar un delegado <xref:System.Threading.TimerCallback> al método de devolución de llamada, un objeto que representa el estado que se pasará a la devolución de llamada, la hora de compilación inicial y una cifra que representa el período entre invocaciones de devolución de llamada.  Para cancelar un temporizador pendiente, se debe llamar a la función **Timer.Dispose**.  
  
> [!NOTE]
>  Hay otras dos clases de temporizador.  La clase <xref:System.Windows.Forms.Timer?displayProperty=fullName> es un control que funciona con diseñadores visuales y está pensado para su uso en contextos de interfaz de usuario; provoca eventos en el subproceso de interfaz de usuario.  La clase <xref:System.Timers.Timer?displayProperty=fullName> deriva de <xref:System.ComponentModel.Component>, por lo que puede usarse con diseñadores visuales; también provoca eventos, pero lo hace en un subproceso <xref:System.Threading.ThreadPool>.  La clase <xref:System.Threading.Timer?displayProperty=fullName> realiza las devoluciones de llamada en un subproceso <xref:System.Threading.ThreadPool> y no utiliza el modelo de evento para nada.  También proporciona un objeto de estado al método de devolución de llamada, lo que no hacen otros temporizadores.  Es sumamente ligero.  
  
 El ejemplo de código siguiente inicia un temporizador que se inicia después de un segundo \(1000 milisegundos\) y emite un chasquido por segundo hasta que presione la tecla **Entrar**.  La variable que contiene la referencia al temporizador es un campo de nivel de clase para garantizar que el temporizador no está sujeto a la recolección de elementos no utilizados mientras que todavía está en ejecución.  Para obtener más información acerca de la recolección de elementos no utilizados agresiva, vea <xref:System.GC.KeepAlive%2A>.  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## Vea también  
 <xref:System.Threading.Timer>   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)