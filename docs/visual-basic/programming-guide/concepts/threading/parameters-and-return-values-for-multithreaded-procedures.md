---
title: Parámetros y valores devueltos para procedimientos multiproceso (Visual Basic)
ms.date: 07/20/2015
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
ms.openlocfilehash: 039e9be6f174148995a83c842a442806b9409a3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a>Parámetros y valores devueltos para procedimientos multiproceso (Visual Basic)
El suministro y la devolución de valores en una aplicación multiproceso son complicados porque se debe pasar una referencia a un procedimiento que no tome ningún argumento ni devuelva ningún valor al constructor de la clase de subproceso. En las secciones siguientes se muestran algunas maneras sencillas de proporcionar parámetros y devolver valores desde procedimientos en subprocesos independientes.  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a>Suministro de parámetros para procedimientos multiproceso  
 La mejor manera de proporcionar parámetros para una llamada al método multiproceso es encapsular el método de destino en una clase y definir campos para esa clase que sirvan como parámetros para el nuevo subproceso. La ventaja de este enfoque es que puede crear una nueva instancia de la clase, con sus propios parámetros, cada vez que quiera iniciar un nuevo subproceso. Por ejemplo, imagine que tiene una función que calcula el área de un triángulo, como en el código siguiente:  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 Puede escribir una clase que encapsule la función `CalcArea` y cree campos para almacenar parámetros de entrada como sigue:  
  
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
  
 Para usar `AreaClass`, puede crear un objeto `AreaClass` y establecer las propiedades `Base` y `Height` como se muestra en el código siguiente:  
  
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
  
 Observe que el procedimiento `TestArea` no comprueba el valor del campo `Area` después de llamar al método `CalcArea`. Dado que `CalcArea` se ejecuta en un subproceso independiente, no se garantiza que el campo `Area` se establezca si se comprueba inmediatamente después de llamar a `Thread.Start`. En la sección siguiente se explica una manera mejor de devolver valores desde procedimientos multiproceso.  
  
## <a name="returning-values-from-multithreaded-procedures"></a>Devolución de valores desde procedimientos multiproceso  
 La devolución de valores desde procedimientos que se ejecutan en subprocesos independientes se complica por el hecho de que los procedimientos no pueden ser funciones y no pueden usar argumentos `ByRef`. La manera más fácil de devolver valores es usar el componente <xref:System.ComponentModel.BackgroundWorker> para administrar los subprocesos, generar un evento cuando la tarea esté hecha y procesar los resultados con un controlador de eventos.  
  
 En el ejemplo siguiente se devuelve un valor al generar un evento desde un procedimiento que se ejecuta en un subproceso independiente:  
  
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
  
 Puede proporcionar parámetros y devolver valores a subprocesos de grupo de subprocesos mediante la variable opcional de objeto de estado `ByVal` del método <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>. Los subprocesos de temporizador de subprocesos también admiten un objeto de estado para este fin. Para obtener información sobre la agrupación de subprocesos y temporizadores de subprocesos, vea [(Visual Basic) de la agrupación de subprocesos](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[la agrupación de subprocesos](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) y [temporizadores de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-timers.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Multithreading con el componente BackgroundWorker (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [Agrupación de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [Sincronización de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Aplicaciones multiproceso (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Subprocesamiento múltiple en componentes](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
