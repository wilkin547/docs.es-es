---
title: (Visual Basic) de agrupación de subprocesos
ms.date: 07/20/2015
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
ms.openlocfilehash: 445c1c70cc1371ef918f32046e0c30ae2a473da2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="thread-pooling-visual-basic"></a>(Visual Basic) de agrupación de subprocesos
Un *grupo de subprocesos* es una colección de subprocesos que puede usarse para realizar varias tareas en segundo plano. (Consulte [subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) para obtener información general.) Esto deja libre el subproceso primario para realizar otras tareas de forma asincrónica.  
  
 Los grupos de subprocesos suelen emplearse en aplicaciones de servidor. Cada solicitud entrante se asigna a un subproceso del grupo de subprocesos, de modo que la solicitud se pueda procesar de forma asincrónica, sin acaparar el subproceso primario ni retrasar el procesamiento de solicitudes posteriores.  
  
 Una vez que un subproceso del grupo finaliza su tarea, se devuelve a una cola de subprocesos en espera, donde se puede reutilizar. Esta reutilización permite que las aplicaciones eviten el costo que significa crear un nuevo subproceso para cada tarea.  
  
 Normalmente, los grupos de subprocesos tienen un número máximo de subprocesos. Si todos los subprocesos están ocupados, las tareas adicionales se colocan en cola hasta que se puedan atender a medida que estén disponibles los subprocesos.  
  
 Puede implementar su propio grupo de subprocesos, pero es más fácil usar el grupo de subprocesos proporcionado por .NET Framework a través de la clase <xref:System.Threading.ThreadPool>.  
  
 Con la agrupación de subprocesos, se llama a la <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> método con un delegado para el procedimiento que desea ejecutar y Visual Basic crea el subproceso y ejecuta el procedimiento.  
  
## <a name="thread-pooling-example"></a>Ejemplo de agrupación de subprocesos  
 En el ejemplo siguiente se muestra cómo se puede usar la agrupación de subprocesos para iniciar varias tareas.  
  
```vb  
Public Sub DoWork()  
    ' Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf SomeLongTask))  
    ' Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf AnotherLongTask))  
End Sub  
Private Sub SomeLongTask(ByVal state As Object)  
    ' Insert code to perform a long task.  
End Sub  
Private Sub AnotherLongTask(ByVal state As Object)  
    ' Insert code to perform another long task.  
End Sub  
```  
  
 Una ventaja de la agrupación de subprocesos es que se pueden pasar argumentos de un objeto de estado al procedimiento de tarea. Si el procedimiento al que se está llamando requiere más de un argumento, puede convertir una estructura o una instancia de una clase en un tipo de datos `Object`.  
  
## <a name="thread-pool-parameters-and-return-values"></a>Parámetros y valores devueltos de grupos de subprocesos  
 La devolución de valores desde un subproceso del grupo de subprocesos no es sencilla. La manera estándar de devolver valores desde una llamada de función no está permitida, ya que los procedimientos `Sub` son el único tipo de procedimiento que se puede poner en cola en un grupo de subprocesos. Una manera de poder proporcionar parámetros y devolver valores consiste en ajustar los parámetros, valores devueltos, y métodos en un contenedor de clase como se describe en [parámetros y valores devueltos para procedimientos multiproceso (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).  
  
 Una manera más sencilla de proporcionar parámetros y devolver valores es usar la variable opcional de objeto de estado `ByVal` del método <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>. Si usa esta variable para pasar una referencia a una instancia de una clase, el subproceso del grupo de subprocesos puede modificar los miembros de la instancia y estos pueden usarse como valores devueltos.  
  
 A primera vista, probablemente no sea obvio que se puede modificar un objeto al que hace referencia una variable que se pasa por valor. Esto se puede hacer porque solo se pasa por valor la referencia del objeto. Cuando se realizan cambios en los miembros del objeto al que hace referencia la referencia de objeto, los cambios se aplican a la instancia de clase real.  
  
 Las estructuras no se pueden usar para devolver valores dentro de objetos de estado. Dado que las estructuras son tipos de valor, los cambios que realiza el proceso asincrónico no cambian los miembros de la estructura original. Use estructuras para proporcionar parámetros cuando no se necesiten valores devueltos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [Cómo: Usar un grupo de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 [Subprocesamiento (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [Aplicaciones multiproceso (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Sincronización de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)
