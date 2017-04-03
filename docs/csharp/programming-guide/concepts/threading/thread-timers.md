---
title: Temporizadores de subprocesos (C#) | Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 52ed71e8-4fd9-43a4-ae40-04cce7cff23f
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1f91fde1340772c62f7779a2503bfb79aba7c3fb
ms.lasthandoff: 03/13/2017

---
# <a name="thread-timers-c"></a>Temporizadores de subprocesos (C#)
La clase <xref:System.Threading.Timer?displayProperty=fullName> es útil para ejecutar periódicamente una tarea en un subproceso separado. Por ejemplo, podría usar un temporizador de subprocesos para comprobar el estado y la integridad de una base de datos o para hacer copias de seguridad de archivos importantes.  
  
## <a name="thread-timer-example"></a>Ejemplo de temporizador de subprocesos  
 El ejemplo siguiente inicia una tarea cada dos segundos y usa un marcador para iniciar el método <xref:System.IDisposable.Dispose%2A>, que detiene el temporizador. En este ejemplo se publica el estado en la ventana de salida.  
  
```csharp  
private class StateObjClass  
{  
    // Used to hold parameters for calls to TimerTask.  
    public int SomeValue;  
    public System.Threading.Timer TimerReference;  
    public bool TimerCanceled;  
}  
  
public void RunTimer()  
{  
    StateObjClass StateObj = new StateObjClass();  
    StateObj.TimerCanceled = false;  
    StateObj.SomeValue = 1;  
    System.Threading.TimerCallback TimerDelegate =  
        new System.Threading.TimerCallback(TimerTask);  
  
    // Create a timer that calls a procedure every 2 seconds.  
    // Note: There is no Start method; the timer starts running as soon as   
    // the instance is created.  
    System.Threading.Timer TimerItem =  
        new System.Threading.Timer(TimerDelegate, StateObj, 2000, 2000);  
  
    // Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem;    
  
    // Run for ten loops.  
    while (StateObj.SomeValue < 10)   
    {  
        // Wait one second.  
        System.Threading.Thread.Sleep(1000);    
    }  
  
    // Request Dispose of the timer object.  
    StateObj.TimerCanceled = true;    
}  
  
private void TimerTask(object StateObj)  
{  
    StateObjClass State = (StateObjClass)StateObj;  
    // Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(ref State.SomeValue);  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " + DateTime.Now.ToString());  
    if (State.TimerCanceled)      
    // Dispose Requested.  
    {  
        State.TimerReference.Dispose();  
        System.Diagnostics.Debug.WriteLine("Done  " + DateTime.Now.ToString());  
    }  
}  
```  
  
 Los temporizadores de subprocesos resultan especialmente útiles cuando el objeto <xref:System.Windows.Forms.Timer?displayProperty=fullName> no se encuentra disponible; como cuando se desarrollan aplicaciones de consola.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading>   
 [Aplicaciones multiproceso (C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)
