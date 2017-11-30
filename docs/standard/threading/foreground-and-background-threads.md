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
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ad427fc2c1175c0d9b333aa418aea039f11a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="foreground-and-background-threads"></a>Subprocesos de primer y segundo plano
Un subproceso administrado es un subproceso en segundo plano o en un subproceso en primer plano. Subprocesos en segundo plano son idénticos a los subprocesos de primer plano con una excepción: un subproceso en segundo plano no mantiene el entorno de ejecución administrado. Una vez que todos los subprocesos de primer plano se ha detenido en un proceso administrado (donde el archivo .exe es un ensamblado administrado), el sistema detiene todos los subprocesos en segundo plano y se cierra.  
  
> [!NOTE]
>  Cuando el tiempo de ejecución detiene un subproceso en segundo plano porque el proceso se va a cerrar, se inicia ninguna excepción en el subproceso. Sin embargo, cuando se detienen los subprocesos porque el <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> método descarga el dominio de aplicación, un <xref:System.Threading.ThreadAbortException> se produce en los subprocesos de primer plano y fondo.  
  
 Use la <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> propiedad para determinar si un subproceso es un fondo o un subproceso en primer plano, o para cambiar su estado. Un subproceso puede cambiar a un subproceso en segundo plano en cualquier momento estableciendo su <xref:System.Threading.Thread.IsBackground%2A> propiedad `true`.  
  
> [!IMPORTANT]
>  El estado de primer plano o en segundo plano de un subproceso no afectan al resultado de una excepción no controlada en el subproceso. En la versión 2.0 de .NET Framework, una excepción no controlada en subprocesos de primer plano o en segundo plano da lugar a finalización de la aplicación. Vea [excepciones en subprocesos administrados](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
 Los subprocesos que pertenecen al grupo de subprocesos administrados (es decir, subprocesos cuya <xref:System.Threading.Thread.IsThreadPoolThread%2A> propiedad es `true`) son subprocesos en segundo plano. Todos los subprocesos que entran en el entorno de ejecución administrado desde código no administrado se marcan como subprocesos en segundo plano. Todos los subprocesos generados al crear e iniciar un nuevo <xref:System.Threading.Thread> objeto son subprocesos de primer plano predeterminado.  
  
 Si utiliza un subproceso para controlar una actividad, como una conexión de socket, establecer su <xref:System.Threading.Thread.IsBackground%2A> propiedad `true` para que el subproceso no impide que el proceso de terminación.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadAbortException>
