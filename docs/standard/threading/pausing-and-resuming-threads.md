---
title: "Pausing and Resuming Threads | Microsoft Docs"
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
  - "resuming threads"
  - "threading [.NET Framework], pausing"
  - "pausing threads"
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Pausing and Resuming Threads
Las maneras más habituales de sincronizar las actividades de los subprocesos son bloquear y liberar subprocesos, o bloquear objetos o regiones de código.  Para obtener más información sobre estos bloqueos y mecanismos de bloqueo, consulte [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 También puede hacer que los subprocesos se pongan en modo de suspensión.  Cuando los subprocesos se bloquean o se ponen en modo de suspensión, puede usar una <xref:System.Threading.ThreadInterruptedException> para interrumpir sus estados de espera.  
  
## Método Thread.Sleep  
 Al llamar al método <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>, el subproceso actual se bloquea inmediatamente durante el número de milisegundos que pase a <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>, y el resto de su intervalo de tiempo se dedica a otro subproceso.  Un subproceso no puede llamar a <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> en otro subproceso.  
  
 Al llamar a <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> con <xref:System.Threading.Timeout.Infinite?displayProperty=fullName>, un subproceso se pone en modo de suspensión hasta que lo interrumpe otro subproceso que llama a <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>, o hasta que <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> lo termina.  
  
## Interrumpir subprocesos  
 Puede interrumpir un subproceso en espera llamando a <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> en el subproceso bloqueado para generar una <xref:System.Threading.ThreadInterruptedException>, que saca al subproceso de la llamada de bloqueo.  El subproceso debe detectar la <xref:System.Threading.ThreadInterruptedException> y hacer lo que sea necesario para seguir trabajando.  Si el subproceso pasa por alto la excepción, el tiempo de ejecución detecta la excepción y detiene el subproceso.  
  
> [!NOTE]
>  Si el subproceso de destino no está bloqueado cuando se llama a <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>, el subproceso no se interrumpe hasta que se bloquea.  Si el subproceso nunca se bloquea, puede finalizar sin ser interrumpido.  
  
 Si una espera es administrada, tanto <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> como <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> activan el subproceso inmediatamente.  Si una espera es de tipo no administrado \(por ejemplo, una llamada de invocación de plataforma a la función `WaitForSingleObject` de Win32\), ni <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> ni <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> pueden tomar el control del subproceso hasta que este vuelva o llame a código administrado.  En código administrado, el comportamiento es el siguiente:  
  
-   <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> activa un subproceso de cualquier tipo de espera que pueda haber y hace que se genere una <xref:System.Threading.ThreadInterruptedException> en el subproceso de destino.  
  
-   <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> es similar a <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>, excepto porque hace que se genere una <xref:System.Threading.ThreadAbortException> en el subproceso.  Para obtener más información, consulte [Destruir subprocesos](../../../docs/standard/threading/destroying-threads.md).  
  
## Suspender y reanudar \(obsoleto\)  
 La clase <xref:System.Threading.Thread> incluye dos métodos, <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> y <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName>, para pausar y reanudar un subproceso.  Sin embargo, no se recomienda usar estos métodos.  
  
> [!IMPORTANT]
>  A partir de la versión 2.0 de .NET Framework, los métodos <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> y <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName> están marcados como obsoletos y se quitarán en futuras versiones.  
>   
>  Los métodos <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> y <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName> no suelen ser útiles para las aplicaciones y no deben confundirse con los mecanismos de sincronización.  Como <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> y <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName> no dependen de la cooperación del subproceso que se está controlando, son muy intrusivos y pueden provocar problemas graves de aplicación como interbloqueos \(por ejemplo, si se suspende un subproceso que contiene un recurso que otro subproceso necesitará\).  
  
 Algunas aplicaciones necesitan controlar la prioridad de los subprocesos para mejorar el rendimiento.  Para ello, debe usar la propiedad <xref:System.Threading.Thread.Priority%2A?displayProperty=fullName> en lugar del método <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadInterruptedException>   
 <xref:System.Threading.ThreadAbortException>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)   
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)