---
title: "Foreground and Background Threads | Microsoft Docs"
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
  - "threading [.NET Framework], foreground"
  - "threading [.NET Framework], background"
  - "foreground threads"
  - "background threads"
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Foreground and Background Threads
Un subproceso administrado es un subproceso en segundo plano o un subproceso de primer plano.  Los subprocesos en segundo plano son idénticos a los subprocesos en primer plano con una excepción: un subproceso en segundo plano no mantiene activo el entorno de ejecución administrado.  Una vez que todos los subprocesos de primer plano se han detenido en un proceso administrado \(donde el archivo .exe es un ensamblado administrado\), el sistema detiene todos los subprocesos en segundo plano y se cierra.  
  
> [!NOTE]
>  Cuando el tiempo de ejecución detiene un subproceso en segundo plano porque el proceso está cerrándose, no se produce ninguna excepción en el subproceso.  Sin embargo, cuando los subprocesos se detienen porque el método <xref:System.AppDomain.Unload%2A?displayProperty=fullName> descarga el dominio de aplicación, se produce una excepción <xref:System.Threading.ThreadAbortException> tanto en los subprocesos en primer plano como en los subprocesos segundo plano.  
  
 Utilice la propiedad <xref:System.Threading.Thread.IsBackground%2A?displayProperty=fullName> para determinar si un subproceso es un subproceso en segundo plano o en primer plano, o para cambiar su estado.  Un subproceso puede cambiarse a segundo plano en cualquier momento estableciendo su propiedad <xref:System.Threading.Thread.IsBackground%2A> en `true`.  
  
> [!IMPORTANT]
>  El estado de primer plano o segundo plano de un subproceso no afecta al resultado de una excepción no controlada en el subproceso.  En la versión 2.0 de .NET Framework, una excepción no controlada tanto en subprocesos en primer plano como en subprocesos en segundo plano da como resultado la finalización de la aplicación.  Vea [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
 Los subprocesos que pertenecen al grupo de subprocesos administrados \(es decir, los subprocesos cuya propiedad <xref:System.Threading.Thread.IsThreadPoolThread%2A> es `true`\) son subprocesos en segundo plano.  Todos los subprocesos que entran en el entorno de ejecución administrado desde código no administrado se marcan como subprocesos en segundo plano.  Todos los subprocesos generados al crear e iniciar un nuevo objeto <xref:System.Threading.Thread> son subprocesos en primer plano de forma predeterminada.  
  
 Si utiliza un subproceso para controlar una actividad, como una conexión de socket, establezca su propiedad <xref:System.Threading.Thread.IsBackground%2A> en `true` para que el subproceso no impida la finalización del proceso.  
  
## Vea también  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=fullName>   
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadAbortException>