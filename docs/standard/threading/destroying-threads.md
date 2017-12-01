---
title: Destruir subprocesos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- destroying threads
- threading [.NET Framework], destroying threads
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a41dce5db707d0be49c283256de665d316e1a1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="destroying-threads"></a>Destruir subprocesos
El <xref:System.Threading.Thread.Abort%2A> método se utiliza para detener un subproceso administrado de forma permanente. Cuando se llama a <xref:System.Threading.Thread.Abort%2A>, common language runtime produce una <xref:System.Threading.ThreadAbortException> en el subproceso de destino, que puede detectar el subproceso de destino. Para obtener más información, consulta <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Si se está ejecutando un subproceso no administrado código, cuando su <xref:System.Threading.Thread.Abort%2A> se llama al método, el tiempo de ejecución lo marca <xref:System.Threading.ThreadState.AbortRequested?displayProperty=nameWithType>. La excepción se produce cuando el subproceso vuelve al código administrado.  
  
 Una vez que se anula un subproceso, no se puede reiniciar.  
  
 El <xref:System.Threading.Thread.Abort%2A> método no hace que el subproceso se anule inmediatamente, porque el subproceso de destino puede detectar la <xref:System.Threading.ThreadAbortException> y ejecutar cantidades arbitrarias de código en un `finally` bloque. Puede llamar a <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> si tiene que esperar hasta que haya finalizado el subproceso. <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>es una llamada de bloqueo que no vuelve hasta que el subproceso se ha detenido realmente o ha transcurrido un intervalo de tiempo de espera opcional. El subproceso anulado podría llamar a la <xref:System.Threading.Thread.ResetAbort%2A> método o llevar a cabo el procesamiento sin enlazar en una `finally` bloquear, por lo que si no especifica un tiempo de espera, no se garantiza que la espera para finalizar.  
  
 Subprocesos que están esperando en una llamada a la <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> método puede interrumpirse por otros subprocesos que llaman a <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>.  
  
## <a name="handling-threadabortexception"></a>Controlar ThreadAbortException  
 Si espera que el subproceso anulado, ya sea como resultado de llamar al método <xref:System.Threading.Thread.Abort%2A> desde su propio código o como resultado de descargar un dominio de aplicación en el que está ejecutando el subproceso (<xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> utiliza <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> para finalizar subprocesos), debe controlar el subproceso el <xref:System.Threading.ThreadAbortException> y realizar cualquier procesamiento final en un `finally` cláusula, tal como se muestra en el código siguiente.  
  
```vb  
Try  
    ' Code that is executing when the thread is aborted.  
Catch ex As ThreadAbortException  
    ' Clean-up code can go here.  
    ' If there is no Finally clause, ThreadAbortException is  
    ' re-thrown by the system at the end of the Catch clause.   
Finally  
    ' Clean-up code can go here.  
End Try  
' Do not put clean-up code here, because the exception   
' is rethrown at the end of the Finally clause.  
```  
  
```csharp  
try   
{  
    // Code that is executing when the thread is aborted.  
}   
catch (ThreadAbortException ex)   
{  
    // Clean-up code can go here.  
    // If there is no Finally clause, ThreadAbortException is  
    // re-thrown by the system at the end of the Catch clause.   
}  
// Do not put clean-up code here, because the exception   
// is rethrown at the end of the Finally clause.  
```  
  
 El código de limpieza debe estar en el `catch` cláusula o la `finally` cláusula, porque un <xref:System.Threading.ThreadAbortException> se vuelve a iniciar el sistema al final de la `finally` cláusula, o al final de la `catch` cláusula si no hay ningún `finally` cláusula.  
  
 Puede impedir que el sistema de vuelva a iniciar la excepción mediante una llamada a la <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=nameWithType> método. Sin embargo, debe hacerlo los solo si su propio código que provocó la <xref:System.Threading.ThreadAbortException>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.ThreadAbortException>  
 <xref:System.Threading.Thread>  
 [Usar subprocesos y subprocesamiento](../../../docs/standard/threading/using-threads-and-threading.md)
