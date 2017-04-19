---
title: "Parámetros y valores devueltos para procedimientos multiproceso (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d5d8adde531d31aa6bf353f53bd4cfecc084f515
ms.lasthandoff: 03/13/2017

---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a>Parámetros y valores devueltos para procedimientos multiproceso (Visual Basic)
Suministrar y devolver valores en una aplicación multiproceso es complicado, porque se debe pasar una referencia a un procedimiento que no toma ningún argumento y no devuelve ningún valor al constructor de la clase de subproceso. Las secciones siguientes muestran algunas maneras sencillas de suministrar parámetros y devolver valores de procedimientos en subprocesos separados.  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a>Suministrar parámetros para procedimientos multiproceso  
 La mejor manera de proporcionar parámetros para una llamada al método multiproceso es ajustar el método de destino en una clase y definir campos para dicha clase que servirán como parámetros para el nuevo subproceso. La ventaja de este enfoque es que puede crear una nueva instancia de la clase, con sus propios parámetros, cada vez que desee iniciar un nuevo subproceso. Por ejemplo, suponga que tiene una función que calcula el área de un triángulo, como en el código siguiente:  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 Puede escribir una clase que encapsula la `CalcArea` función y crea campos para almacenar parámetros de entrada, como sigue:  
  
```vb  
Class AreaClass  
    Public Base As Double  
    Public Height As Double  
    Public Area As Double  
    Sub CalcArea()  
        Area = 0.5 * Base * Height  
        MessageBox.Show("The area is: " & Area.ToString)  
    End Sub  
End Class  
```  
  
 Usar el `AreaClass`, puede crear un `AreaClass` objeto y establecer el `Base` y `Height` propiedades como se muestra en el código siguiente:  
  
```vb  
Protected Sub TestArea()  
    Dim AreaObject As New AreaClass  
    Dim Thread As New System.Threading.Thread(  
                        AddressOf AreaObject.CalcArea)  
    AreaObject.Base = 30  
    AreaObject.Height = 40  
    Thread.Start()  
End Sub  
```  
  
 Observe que la `TestArea` procedimiento no comprueba el valor de la `Area` campo después de llamar a la `CalcArea` (método). Porque `CalcArea` se ejecuta en un subproceso independiente, el `Area` campo no se garantiza que se establece si se comprueba inmediatamente después de llamar a `Thread.Start`. La sección siguiente explica una mejor manera de devolver valores de procedimientos multiproceso.  
  
## <a name="returning-values-from-multithreaded-procedures"></a>Devolver valores de procedimientos multiproceso  
 Devolver valores de procedimientos que se ejecutan en subprocesos separados es complicado por el hecho de que los procedimientos no pueden ser funciones y no se pueden usar `ByRef` argumentos. La manera más fácil de devolver valores es usar el <xref:System.ComponentModel.BackgroundWorker>componentes para administrar los subprocesos y provocar un evento cuando se realiza la tarea y procesar los resultados con un controlador de eventos.</xref:System.ComponentModel.BackgroundWorker>  
  
 En el ejemplo siguiente se devuelve un valor por generar un evento desde un procedimiento que se ejecuta en un subproceso independiente:  
  
```vb  
Private Class AreaClass2  
    Public Base As Double  
    Public Height As Double  
    Function CalcArea() As Double  
        ' Calculate the area of a triangle.  
        Return 0.5 * Base * Height  
    End Function  
End Class  
  
Private WithEvents BackgroundWorker1 As New System.ComponentModel.BackgroundWorker  
  
Private Sub TestArea2()  
    Dim AreaObject2 As New AreaClass2  
    AreaObject2.Base = 30  
    AreaObject2.Height = 40  
  
    ' Start the asynchronous operation.  
    BackgroundWorker1.RunWorkerAsync(AreaObject2)  
End Sub  
  
' This method runs on the background thread when it starts.  
Private Sub BackgroundWorker1_DoWork(  
    ByVal sender As Object,   
    ByVal e As System.ComponentModel.DoWorkEventArgs  
    ) Handles BackgroundWorker1.DoWork  
  
    Dim AreaObject2 As AreaClass2 = CType(e.Argument, AreaClass2)  
    ' Return the value through the Result property.  
    e.Result = AreaObject2.CalcArea()  
End Sub  
  
' This method runs on the main thread when the background thread finishes.  
Private Sub BackgroundWorker1_RunWorkerCompleted(  
    ByVal sender As Object,  
    ByVal e As System.ComponentModel.RunWorkerCompletedEventArgs  
    ) Handles BackgroundWorker1.RunWorkerCompleted  
  
    ' Access the result through the Result property.  
    Dim Area As Double = CDbl(e.Result)  
    MessageBox.Show("The area is: " & Area.ToString)  
End Sub  
```  
  
 Puede proporcionar parámetros y devolver valores a los subprocesos del grupo de subprocesos mediante opcional `ByVal` variable de objeto de estado de la <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>método.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> Subprocesos de temporizador de subproceso admiten también un objeto de estado con este propósito. Para obtener información sobre la agrupación de subprocesos y temporizadores de subprocesos, vea [(Visual Basic) de la agrupación de subprocesos](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[agrupación de subprocesos](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) y [temporizadores de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Multithreading con el componente BackgroundWorker (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)   
 [(Visual Basic) de agrupación de subprocesos](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)   
 [Sincronización de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)   
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)   
 [Aplicaciones multiproceso (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)   
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Multithreading en componentes](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
