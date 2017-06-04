---
title: "dangerousThreadingAPI MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "suspending threads"
  - "DangerousThreadingAPI MDA"
  - "managed debugging assistants (MDAs), dangerous threading operations"
  - "threading [.NET Framework], suspending"
  - "MDAs (managed debugging assistants), dangerous threading operations"
  - "Suspend method"
  - "threading [.NET Framework], managed debugging assistants"
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# dangerousThreadingAPI MDA
El asistente para la depuración administrada \(MDA\) `dangerousThreadingAPI` se activa cuando se llama al método <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> en un subproceso distinto del subproceso actual.  
  
## Síntomas  
 Hay una aplicación que no responde o que ha dejado de responder indefinidamente.  Ciertos datos de sistema o de programa podrían quedar temporalmente en un estado imprevisible, incluso después de haber cerrado la aplicación.  Algunas operaciones no están finalizando como se esperaba.  
  
 Los síntomas pueden variar considerablemente debido a la aleatoriedad inherente al problema.  
  
## Motivo  
 Un subproceso es suspendido de forma asincrónica por otro subproceso mediante el método <xref:System.Threading.Thread.Suspend%2A>.  No hay manera de determinar en qué momento es seguro suspender otro subproceso que podría estar en medio de una operación.  Suspender el subproceso puede producir daños en los datos o la ruptura de invariantes.  Si se colocase un subproceso en estado de suspensión y no se volviese a reiniciar mediante el método <xref:System.Threading.Thread.Resume%2A>, la aplicación podría dejar de responder indefinidamente y posiblemente se produjese algún daño en los datos del programa.  Estos métodos se han marcado como obsoletos.  
  
 Si el subproceso de destino contiene primitivos de sincronización, éstos permanecerán así durante la suspensión.  Esto podría conducir a una situación de interbloqueo en caso de que otro subproceso, por ejemplo el subproceso que está realizando el método <xref:System.Threading.Thread.Suspend%2A>, intentase adquirir un bloqueo en el primitivo.  En esta situación, el problema se manifiesta como un interbloqueo.  
  
## Resolución  
 Evite diseños que requieran el uso de <xref:System.Threading.Thread.Suspend%2A> y <xref:System.Threading.Thread.Resume%2A>.  Para la cooperación entre subprocesos, utilice primitivos de sincronización como <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex> o la instrucción `lock` de C\#.  Si tuviese que utilizar estos métodos, reduzca la ventana de tiempo y minimice la cantidad de código en ejecución mientras el subproceso está en estado de suspensión.  
  
## Efecto en el Runtime  
 Este MDA no tiene efecto en el CLR.  Sólo comunica datos sobre operaciones de subprocesamiento peligrosas.  
  
## Resultados  
 El asistente para la depuración administrada identifica el método de subprocesamiento peligroso que produjo su activación.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra una llamada al método <xref:System.Threading.Thread.Suspend%2A> que produce la activación de `dangerousThreadingAPI`.  
  
```  
using System.Threading;  
void FireMda()  
{  
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();   
    t.Resume();  
    t.Join();  
}  
```  
  
## Vea también  
 <xref:System.Threading.Thread>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [lock \(Instrucción\)](../Topic/lock%20Statement%20\(C%23%20Reference\).md)