---
title: Subprocesos de primer y segundo plano
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 83022bd27379e1ee34197af4897a5c809f495f48
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="foreground-and-background-threads"></a>Subprocesos de primer y segundo plano
Un subproceso administrado es un subproceso en segundo plano o un subproceso en primer plano. Los subprocesos en segundo plano son idénticos a los subprocesos en primer plano con una excepción: un subproceso en segundo plano no mantiene el entorno de ejecución administrado en ejecución. Una vez que todos los subprocesos en primer plano se han detenido en un proceso administrado (donde el archivo .exe es un ensamblado administrado), el sistema detiene todos los subprocesos en segundo plano y se cierra.  
  
> [!NOTE]
>  Cuando el tiempo de ejecución detiene un subproceso en segundo plano porque el proceso se va a cerrar, no se inicia ninguna excepción en el subproceso. Sin embargo, cuando se detienen los subprocesos porque el método <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> descarga el dominio de aplicación, se produce <xref:System.Threading.ThreadAbortException> en los subprocesos en primer y segundo plano.  
  
 Use la propiedad <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> para determinar si un subproceso es de primer o segundo plano o para cambiar su estado. Un subproceso puede cambiar a un subproceso en segundo plano en cualquier momento estableciendo su propiedad <xref:System.Threading.Thread.IsBackground%2A> en `true`.  
  
> [!IMPORTANT]
>  El estado de primer o segundo plano de un subproceso no afecta al resultado de una excepción no controlada del subproceso. En la versión 2.0 de .NET Framework, una excepción no controlada de subprocesos en primer o segundo plano resulta en la terminación de la aplicación. Vea [Excepciones en subprocesos administrados](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
 Los subprocesos que pertenecen al grupo de subprocesos administrados (es decir, subprocesos cuya propiedad <xref:System.Threading.Thread.IsThreadPoolThread%2A> es `true`) son subprocesos en segundo plano. Todos los subprocesos que entran en el entorno de ejecución administrado desde el código no administrado se marcan como subprocesos en segundo plano. Todos los subprocesos generados al crear e iniciar un nuevo objeto <xref:System.Threading.Thread> son subprocesos de primer plano predeterminados.  
  
 Si utiliza un subproceso para controlar una actividad, como una conexión de socket, establezca su propiedad <xref:System.Threading.Thread.IsBackground%2A> en `true` para que el subproceso no impida la terminación del proceso.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadAbortException>
