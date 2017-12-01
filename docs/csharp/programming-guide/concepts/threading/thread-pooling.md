---
title: "Agrupación de subprocesos (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 98ae68c1-ace8-44b9-9317-8920ac9ef2b6
caps.latest.revision: "5"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 09dd597e8ac7a6b336f71891ccc89984ea659614
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="thread-pooling-c"></a>Agrupación de subprocesos (C#)
Un *grupo de subprocesos* es una colección de subprocesos que puede usarse para realizar varias tareas en segundo plano. (Vea [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) (Subprocesos (C#)) para obtener información general). Esto deja libre el subproceso primario para realizar otras tareas de forma asincrónica.  
  
 Los grupos de subprocesos suelen emplearse en aplicaciones de servidor. Cada solicitud entrante se asigna a un subproceso del grupo de subprocesos, de modo que la solicitud se pueda procesar de forma asincrónica, sin acaparar el subproceso primario ni retrasar el procesamiento de solicitudes posteriores.  
  
 Una vez que un subproceso del grupo finaliza su tarea, se devuelve a una cola de subprocesos en espera, donde se puede reutilizar. Esta reutilización permite que las aplicaciones eviten el costo que significa crear un nuevo subproceso para cada tarea.  
  
 Normalmente, los grupos de subprocesos tienen un número máximo de subprocesos. Si todos los subprocesos están ocupados, las tareas adicionales se colocan en cola hasta que se puedan atender a medida que estén disponibles los subprocesos.  
  
 Puede implementar su propio grupo de subprocesos, pero es más fácil usar el grupo de subprocesos proporcionado por .NET Framework a través de la clase <xref:System.Threading.ThreadPool>.  
  
 Con la agrupación de subprocesos, se llama al método <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> con un delegado para el procedimiento que se quiere ejecutar, y C# crea el subproceso y ejecuta el procedimiento.  
  
## <a name="thread-pooling-example"></a>Ejemplo de agrupación de subprocesos  
 En el ejemplo siguiente se muestra cómo se puede usar la agrupación de subprocesos para iniciar varias tareas.  
  
```csharp  
public void DoWork()  
{  
    // Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(SomeLongTask));  
    // Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(AnotherLongTask));  
}  
  
private void SomeLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
  
private void AnotherLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
```  
  
 Una ventaja de la agrupación de subprocesos es que se pueden pasar argumentos de un objeto de estado al procedimiento de tarea. Si el procedimiento al que se está llamando requiere más de un argumento, puede convertir una estructura o una instancia de una clase en un tipo de datos `Object`.  
  
## <a name="thread-pool-parameters-and-return-values"></a>Parámetros y valores devueltos de grupos de subprocesos  
 La devolución de valores desde un subproceso del grupo de subprocesos no es sencilla. La manera estándar de devolver valores desde una llamada de función no está permitida, ya que los procedimientos `Sub` son el único tipo de procedimiento que se puede poner en cola en un grupo de subprocesos. Una manera de proporcionar parámetros y valores devueltos consiste en empaquetar los parámetros, los valores devueltos y los métodos en una clase contenedora, como se describe en [Parameters and Return Values for Multithreaded Procedures (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md) (Parámetros y valores devueltos para procedimientos multiproceso (C#)).  
  
 Una manera más sencilla de proporcionar parámetros y devolver valores es usar la variable opcional de objeto de estado `ByVal` del método <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>. Si usa esta variable para pasar una referencia a una instancia de una clase, el subproceso del grupo de subprocesos puede modificar los miembros de la instancia y estos pueden usarse como valores devueltos.  
  
 A primera vista, probablemente no sea obvio que se puede modificar un objeto al que hace referencia una variable que se pasa por valor. Esto se puede hacer porque solo se pasa por valor la referencia del objeto. Cuando se realizan cambios en los miembros del objeto al que hace referencia la referencia de objeto, los cambios se aplican a la instancia de clase real.  
  
 Las estructuras no se pueden usar para devolver valores dentro de objetos de estado. Dado que las estructuras son tipos de valor, los cambios que realiza el proceso asincrónico no cambian los miembros de la estructura original. Use estructuras para proporcionar parámetros cuando no se necesiten valores devueltos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [Cómo: Usar un grupo de subprocesos (C#)](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 [Subprocesamiento (C#)](../../../../csharp/programming-guide/concepts/threading/index.md)  
 [Aplicaciones multiproceso (C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Sincronización de subprocesos (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)
