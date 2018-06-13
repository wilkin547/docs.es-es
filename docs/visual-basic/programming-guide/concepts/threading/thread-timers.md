---
title: Temporizadores de subprocesos (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 809cba93-cc93-4e21-afda-f299f9a39818
ms.openlocfilehash: 019b8372be63b9a9fdbcee134834a34f6bef2b74
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646903"
---
# <a name="thread-timers-visual-basic"></a>Temporizadores de subprocesos (Visual Basic)
La clase <xref:System.Threading.Timer?displayProperty=nameWithType> es útil para ejecutar una tarea periódicamente en un subproceso independiente. Por ejemplo, podría usar un temporizador de subprocesos para comprobar el estado y la integridad de una base de datos o para hacer copias de seguridad de archivos importantes.  
  
## <a name="thread-timer-example"></a>Ejemplo de temporizador de subprocesos  
 El ejemplo siguiente inicia una tarea cada dos segundos y usa un marcador para iniciar el método <xref:System.IDisposable.Dispose%2A>, que detiene el temporizador. En este ejemplo se publica el estado en la ventana de salida.  
  
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
  
 Los temporizadores de subprocesos resultan especialmente útiles cuando el objeto <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> no se encuentra disponible; como cuando se desarrollan aplicaciones de consola.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading>  
 [Aplicaciones multiproceso (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)
