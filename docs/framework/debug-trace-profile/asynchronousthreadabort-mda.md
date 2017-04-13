---
title: "asynchronousThreadAbort MDA | Microsoft Docs"
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
  - "asynchronous thread aborts"
  - "AsynchronousThreadAbort MDA"
  - "managed debugging assistants (MDAs), asynchronous thread aborts"
  - "threading [.NET Framework], managed debugging assistants"
  - "MDAs (managed debugging assistants), asynchronous thread aborts"
ms.assetid: 9ebe40b2-d703-421e-8660-984acc42bfe0
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# asynchronousThreadAbort MDA
El asistente para la depuración administrada \(MDA\) de `asynchronousThreadAbort` se activa cuando un subproceso intenta introducir una anulación asincrónica en otro subproceso.  Las anulaciones de subprocesos sincrónicas no activan el MDA de `asynchronousThreadAbort`.  
  
## Síntomas  
 Una aplicación se bloquea con una excepción <xref:System.Threading.ThreadAbortException> no controlada cuando se anula el subproceso principal de la aplicación.  Si la aplicación siguiera ejecutándose, las consecuencias podrían ser peores que si se produce un bloqueo, dado que existiría el riesgo de que se dañasen más datos.  
  
 Es probable que las operaciones que debían ser atómicas se hayan interrumpido después de una finalización parcial, con lo que el estado resultante de los datos de la aplicación es imprevisible.  Se puede generar una excepción <xref:System.Threading.ThreadAbortException> desde puntos aparentemente aleatorios en la ejecución de código; a menudo, en lugares en los que no se espera que se produzca una excepción.  El código podría no ser capaz de controlar este tipo de excepciones, con lo que se producirían daños.  
  
 Los síntomas pueden variar considerablemente debido a la aleatoriedad inherente al problema.  
  
## Motivo  
 El código de un subproceso llamó al método <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> en un subproceso de destino para introducir una anulación de subproceso asincrónica.  La anulación del subproceso es asincrónica porque el código que realiza la llamada a <xref:System.Threading.Thread.Abort%2A> se ejecuta en un subproceso distinto que el destino de la operación de anulación.  Las anulaciones de subprocesos sincrónicas no deberían plantear ningún problema, ya que el subproceso que ejecuta <xref:System.Threading.Thread.Abort%2A> tiene que haberlo hecho únicamente en un punto de control en el que el estado de la aplicación es coherente.  
  
 Las anulaciones de subprocesos asincrónicas presentan un problema porque se procesan en puntos imprevisibles en la ejecución del subproceso de destino.  Para evitarlo, el código escrito para la ejecución en un subproceso susceptible de anularse de este modo tendría que controlar una excepción <xref:System.Threading.ThreadAbortException> casi en cada línea, con la precaución de devolver los datos de aplicación a un estado coherente.  No es realista esperar que en el desarrollo del código se tenga presente este problema, ni que se escriba código capaz de proporcionar protección ante las circunstancias posibles.  
  
 Las llamadas en el código no administrado y los bloques `finally` no se anularán de forma asincrónica, sino inmediatamente al salir de una de estas categorías.  
  
 La causa podría ser difícil de determinar debido a la aleatoriedad inherente al problema.  
  
## Resolución  
 Evite el diseño del código que requiera el uso de anulaciones de subprocesos asincrónicas.  Existen varios métodos más adecuados para la interrupción de un subproceso de destino que no requieren una llamada a <xref:System.Threading.Thread.Abort%2A>.  El más seguro consiste en introducir un mecanismo, como una propiedad común, que señale el subproceso de destino para solicitar una interrupción.  El subproceso de destino comprueba la señal en ciertos puntos de control seguros.  Si observa que se ha solicitado una interrupción, puede cerrarse correctamente.  
  
## Efecto en el Runtime  
 Este MDA no tiene efecto en el CLR.  Sólo presenta datos sobre las anulaciones de subprocesos asincrónicas.  
  
## Resultados  
 El MDA informa del id. del subproceso que realiza la anulación y del id. del subproceso destino de la anulación.  Nunca coincidirán porque se limita a las anulaciones asincrónicas.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <asynchronousThreadAbort />  
  </assistants>  
</mdaConfig>  
```  
  
## Ejemplo  
 La activación del MDA de `asynchronousThreadAbort` requiere sólo una llamada a <xref:System.Threading.Thread.Abort%2A> en un subproceso en ejecución independiente.  Considere las consecuencias si el contenido de la función de inicio del subproceso fuera un conjunto de operaciones más complejas susceptibles de ser interrumpidas en cualquier punto por la anulación.  
  
```  
using System.Threading;  
void FireMda()  
{  
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Abort();   
    t.Join();  
}  
```  
  
## Vea también  
 <xref:System.Threading.Thread>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)