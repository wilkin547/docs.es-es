---
title: (Visual Basic) de temporizadores de subprocesos | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 809cba93-cc93-4e21-afda-f299f9a39818
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9ea657482d4e8e1465d9bc6ae3f94915badee512
ms.lasthandoff: 03/13/2017

---
# <a name="thread-timers-visual-basic"></a>Temporizadores de subprocesos (Visual Basic)
La <xref:System.Threading.Timer?displayProperty=fullName>clase es útil para ejecutar periódicamente una tarea en un subproceso independiente.</xref:System.Threading.Timer?displayProperty=fullName> Por ejemplo, podría utilizar un temporizador de subproceso para comprobar el estado y la integridad de una base de datos o para realizar copias de seguridad de archivos críticos.  
  
## <a name="thread-timer-example"></a>Ejemplo de temporizador de subproceso  
 En el ejemplo siguiente se inicia una tarea cada dos segundos y utiliza un indicador para iniciar el <xref:System.IDisposable.Dispose%2A>método que detiene el temporizador.</xref:System.IDisposable.Dispose%2A> Este ejemplo envía el estado a la ventana de salida.  
  
```vb  
Private Class StateObjClass  
    ' Used to hold parameters for calls to TimerTask.  
    Public SomeValue As Integer  
    Public TimerReference As System.Threading.Timer  
    Public TimerCanceled As Boolean  
End Class  
  
Public Sub RunTimer()  
    Dim StateObj As New StateObjClass  
    StateObj.TimerCanceled = False  
    StateObj.SomeValue = 1  
    Dim TimerDelegate As New System.Threading.TimerCallback(AddressOf TimerTask)  
    ' Create a timer that calls a procedure every 2 seconds.  
    ' Note: There is no Start method; the timer starts running as soon as   
    ' the instance is created.  
    Dim TimerItem As New System.Threading.Timer(TimerDelegate, StateObj,  
                                                2000, 2000)  
    ' Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem  
  
    ' Run for ten loops.  
    While StateObj.SomeValue < 10  
        ' Wait one second.  
        System.Threading.Thread.Sleep(1000)  
    End While  
  
    ' Request Dispose of the timer object.  
    StateObj.TimerCanceled = True  
End Sub  
  
Private Sub TimerTask(ByVal StateObj As Object)  
    Dim State As StateObjClass = CType(StateObj, StateObjClass)  
    ' Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(State.SomeValue)  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " & Now.ToString)  
    If State.TimerCanceled Then  
        ' Dispose Requested.  
        State.TimerReference.Dispose()  
        System.Diagnostics.Debug.WriteLine("Done  " & Now)  
    End If  
End Sub  
```  
  
 Temporizadores de subprocesos resultan especialmente útiles cuando la <xref:System.Windows.Forms.Timer?displayProperty=fullName>objeto no está disponible, como cuando se están desarrollando aplicaciones de consola.</xref:System.Windows.Forms.Timer?displayProperty=fullName>  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading></xref:System.Threading>   
 [Aplicaciones multiproceso (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)
