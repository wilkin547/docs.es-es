---
title: "(Visual Basic) de agrupación de subprocesos | Documentos de Microsoft"
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
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6037d7ea17e260d44bae571aa25d413996f5a123
ms.lasthandoff: 03/13/2017

---
# <a name="thread-pooling-visual-basic"></a>(Visual Basic) de agrupación de subprocesos
Un *grupo de subprocesos* es una colección de subprocesos que puede utilizarse para realizar varias tareas en segundo plano. (Consulte [subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) para obtener información general.) Esto deja libre para realizar otras tareas de forma asincrónica el subproceso primario.  
  
 Grupos de subprocesos se emplean a menudo en aplicaciones de servidor. Cada solicitud entrante se asigna a un subproceso del grupo de subprocesos, por lo que la solicitud se pueda procesar de forma asincrónica, sin acaparar el subproceso primario ni retrasar el procesamiento de solicitudes posteriores.  
  
 Una vez que un subproceso del grupo finaliza su tarea, se devuelve a una cola de subprocesos en espera, donde se puede reutilizar. Esta reutilización permite a las aplicaciones evitar el costo de crear un nuevo subproceso para cada tarea.  
  
 Normalmente, los grupos de subprocesos tienen un número máximo de subprocesos. Si todos los subprocesos están ocupados, las tareas adicionales se colocan en cola hasta que se puedan atender a medida que estén disponibles los subprocesos.  
  
 Puede implementar su propio grupo de subprocesos, pero es más fácil de usar el grupo de subprocesos proporcionado por .NET Framework a través de la <xref:System.Threading.ThreadPool>clase.</xref:System.Threading.ThreadPool>  
  
 Con la agrupación de subprocesos, se llama a la <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>método con un delegado para el procedimiento que desea ejecutar y Visual Basic crea el subproceso y ejecuta el procedimiento.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>  
  
## <a name="thread-pooling-example"></a>Ejemplo de agrupación de subprocesos  
 En el ejemplo siguiente se muestra cómo se pueden utilizar la agrupación de subprocesos para iniciar varias tareas.  
  
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
  
 Una ventaja de la agrupación de subprocesos es que puede pasar argumentos en un objeto de estado al procedimiento de tarea. Si el procedimiento que se está llamando requiere más de un argumento, puede convertir una estructura o una instancia de una clase en un `Object` tipo de datos.  
  
## <a name="thread-pool-parameters-and-return-values"></a>Parámetros de grupo de subprocesos y valores devueltos  
 Devolver valores desde un subproceso del grupo de subprocesos no es sencillo. La manera estándar de devolver valores desde una llamada de función no se permite porque `Sub` procedimientos son el único tipo de procedimiento que puede poner en cola para un grupo de subprocesos. Una manera de poder proporcionar parámetros y devolver valores consiste en empaquetar los parámetros, valores devueltos, y métodos en un contenedor de clase como se describe en [parámetros y valores devueltos para procedimientos multiproceso (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).  
  
 Una forma más sencilla de proporcionar parámetros y valores devueltos es mediante opcional `ByVal` variable de objeto de estado de la <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>método.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> Si utiliza esta variable para pasar una referencia a una instancia de una clase, los miembros de la instancia se pueden modificar el grupo de subprocesos y utilizados como valores devueltos.  
  
 Al principio no ser obvio que puede modificar un objeto que hace referencia una variable que se pasa por valor. Puede hacerlo porque sólo la referencia de objeto se pasa por valor. Cuando realiza cambios en los miembros del objeto al que hace referencia la referencia de objeto, los cambios se aplican a la instancia de la clase real.  
  
 Las estructuras no se puede usar para devolver valores dentro de objetos de estado. Dado que las estructuras son tipos de valor, los cambios que realiza el proceso asincrónico no cambian a los miembros de la estructura original. Utilice estructuras para proporcionar parámetros cuando no se necesiten valores devueltos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>   
 <xref:System.Threading></xref:System.Threading>   
 <xref:System.Threading.ThreadPool></xref:System.Threading.ThreadPool>   
 [Cómo: utilizar un grupo de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)   
 [Subprocesamiento (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)   
 [Aplicaciones multiproceso (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)   
 [Sincronización de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)
