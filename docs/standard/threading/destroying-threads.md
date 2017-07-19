---
title: "Destroying Threads | Microsoft Docs"
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
  - "destroying threads"
  - "threading [.NET Framework], destroying threads"
ms.assetid: df54e648-c5d1-47c9-bd29-8e4438c1db6d
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Destroying Threads
El método <xref:System.Threading.Thread.Abort%2A> se utiliza para detener un subproceso administrado de forma permanente.  Cuando llama a <xref:System.Threading.Thread.Abort%2A>, Common Language Runtime inicia una <xref:System.Threading.ThreadAbortException> en el subproceso de destino, que puede detectar el subproceso de destino.  Para obtener más información, vea <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>.  
  
> [!NOTE]
>  Si un subproceso está ejecutando código no administrado cuando se llama a su método <xref:System.Threading.Thread.Abort%2A>, el motor en tiempo de ejecución lo marca como <xref:System.Threading.ThreadState?displayProperty=fullName>.  Se inicia la excepción cuando el subproceso vuelve al código administrado.  
  
 Una vez anulado un subproceso, no se puede reiniciar.  
  
 El método <xref:System.Threading.Thread.Abort%2A> no causa que el subproceso se anule inmediatamente, porque el subproceso de destino puede detectar la <xref:System.Threading.ThreadAbortException> y ejecutar cantidades arbitrarias de código en un bloque `finally`.  Puede llamar a <xref:System.Threading.Thread.Join%2A?displayProperty=fullName> si necesita esperar hasta que haya finalizado el subproceso.  <xref:System.Threading.Thread.Join%2A?displayProperty=fullName> es una llamada de bloqueo que no vuelve hasta que la ejecución del subproceso se ha detenido realmente o ha transcurrido un tiempo de espera opcional.  El subproceso anulado podría llamar al método <xref:System.Threading.Thread.ResetAbort%2A> o realizar un procesamiento independiente en un bloque `finally`, por lo que si no especifica un tiempo de espera, no existe garantía de que finalice dicha espera.  
  
 Otros subprocesos que llaman a <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>pueden interrumpir subprocesos que están esperando una llamada al método <xref:System.Threading.Thread.Join%2A?displayProperty=fullName>.  
  
## Controlar ThreadAbortException  
 Si espera que se vaya a anular su subproceso, bien como resultado de llamar a <xref:System.Threading.Thread.Abort%2A> desde su propio código o como resultado de descargar un dominio de aplicación en el que se está ejecutando el subproceso \(<xref:System.AppDomain.Unload%2A?displayProperty=fullName> utiliza <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> para finalizar subprocesos\), su subproceso debe controlar la <xref:System.Threading.ThreadAbortException> y realizar cualquier procesamiento final en una cláusula `finally`, como se puede ver en el código siguiente.  
  
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
  
 Su código de limpieza debe estar en la cláusula `catch` o en la cláusula `finally`, porque el sistema vuelve a iniciar una <xref:System.Threading.ThreadAbortException> al final de la cláusula `finally`, o al final de la cláusula `catch` si no hay ninguna cláusula `finally`.  
  
 Puede evitar el sistema de vuelva a iniciar la excepción llamando al método <xref:System.Threading.Thread.ResetAbort%2A?displayProperty=fullName>.  Sin embargo, sólo debería hacerlo si la <xref:System.Threading.ThreadAbortException> fue provocada por su propio código.  
  
## Vea también  
 <xref:System.Threading.ThreadAbortException>   
 <xref:System.Threading.Thread>   
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)