---
title: Temporizadores de subprocesos (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 809cba93-cc93-4e21-afda-f299f9a39818
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b828476301424ca767e2b581c173d6a2dcd184ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="thread-timers-visual-basic"></a><span data-ttu-id="b249b-102">Temporizadores de subprocesos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b249b-102">Thread Timers (Visual Basic)</span></span>
<span data-ttu-id="b249b-103">La clase <xref:System.Threading.Timer?displayProperty=nameWithType> es útil para ejecutar una tarea periódicamente en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="b249b-103">The <xref:System.Threading.Timer?displayProperty=nameWithType> class is useful for periodically running a task on a separate thread.</span></span> <span data-ttu-id="b249b-104">Por ejemplo, podría usar un temporizador de subprocesos para comprobar el estado y la integridad de una base de datos o para hacer copias de seguridad de archivos importantes.</span><span class="sxs-lookup"><span data-stu-id="b249b-104">For example, you could use a thread timer to check the status and integrity of a database or to back up critical files.</span></span>  
  
## <a name="thread-timer-example"></a><span data-ttu-id="b249b-105">Ejemplo de temporizador de subprocesos</span><span class="sxs-lookup"><span data-stu-id="b249b-105">Thread Timer Example</span></span>  
 <span data-ttu-id="b249b-106">El ejemplo siguiente inicia una tarea cada dos segundos y usa un marcador para iniciar el método <xref:System.IDisposable.Dispose%2A>, que detiene el temporizador.</span><span class="sxs-lookup"><span data-stu-id="b249b-106">The following example starts a task every two seconds and uses a flag to initiate the <xref:System.IDisposable.Dispose%2A> method that stops the timer.</span></span> <span data-ttu-id="b249b-107">En este ejemplo se publica el estado en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="b249b-107">This example posts status to the output window.</span></span>  
  
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
  
 <span data-ttu-id="b249b-108">Los temporizadores de subprocesos resultan especialmente útiles cuando el objeto <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> no se encuentra disponible; como cuando se desarrollan aplicaciones de consola.</span><span class="sxs-lookup"><span data-stu-id="b249b-108">Thread timers are particularly useful when the <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> object is unavailable, such as when you are developing console applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b249b-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b249b-109">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="b249b-110">Aplicaciones multiproceso (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b249b-110">Multithreaded Applications (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)
