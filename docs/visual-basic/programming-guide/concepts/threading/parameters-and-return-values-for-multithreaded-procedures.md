---
title: Parámetros y valores devueltos para procedimientos multiproceso (Visual Basic)
ms.date: 07/20/2015
ms.assetid: cbdce172-7ff6-41a9-bb21-53a7c6f538a5
ms.openlocfilehash: 545da3e89d44c29c67784b5f01812d87350030c6
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874616"
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-visual-basic"></a><span data-ttu-id="0940d-102">Parámetros y valores devueltos para procedimientos multiproceso (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0940d-102">Parameters and Return Values for Multithreaded Procedures (Visual Basic)</span></span>
<span data-ttu-id="0940d-103">El suministro y la devolución de valores en una aplicación multiproceso son complicados porque se debe pasar una referencia a un procedimiento que no tome ningún argumento ni devuelva ningún valor al constructor de la clase de subproceso.</span><span class="sxs-lookup"><span data-stu-id="0940d-103">Supplying and returning values in a multithreaded application is complicated because the constructor for the thread class must be passed a reference to a procedure that takes no arguments and returns no value.</span></span> <span data-ttu-id="0940d-104">En las secciones siguientes se muestran algunas maneras sencillas de proporcionar parámetros y devolver valores desde procedimientos en subprocesos independientes.</span><span class="sxs-lookup"><span data-stu-id="0940d-104">The following sections show some simple ways to supply parameters and return values from procedures on separate threads.</span></span>  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a><span data-ttu-id="0940d-105">Suministro de parámetros para procedimientos multiproceso</span><span class="sxs-lookup"><span data-stu-id="0940d-105">Supplying Parameters for Multithreaded Procedures</span></span>  
 <span data-ttu-id="0940d-106">La mejor manera de proporcionar parámetros para una llamada al método multiproceso es encapsular el método de destino en una clase y definir campos para esa clase que sirvan como parámetros para el nuevo subproceso.</span><span class="sxs-lookup"><span data-stu-id="0940d-106">The best way to supply parameters for a multithreaded method call is to wrap the target method in a class and define fields for that class that will serve as parameters for the new thread.</span></span> <span data-ttu-id="0940d-107">La ventaja de este enfoque es que puede crear una nueva instancia de la clase, con sus propios parámetros, cada vez que quiera iniciar un nuevo subproceso.</span><span class="sxs-lookup"><span data-stu-id="0940d-107">The advantage of this approach is that you can create a new instance of the class, with its own parameters, every time you want to start a new thread.</span></span> <span data-ttu-id="0940d-108">Por ejemplo, imagine que tiene una función que calcula el área de un triángulo, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0940d-108">For example, suppose you have a function that calculates the area of a triangle, as in the following code:</span></span>  
  
```vb  
Function CalcArea(ByVal Base As Double, ByVal Height As Double) As Double  
    CalcArea = 0.5 * Base * Height  
End Function  
```  
  
 <span data-ttu-id="0940d-109">Puede escribir una clase que encapsule la función `CalcArea` y cree campos para almacenar parámetros de entrada como sigue:</span><span class="sxs-lookup"><span data-stu-id="0940d-109">You can write a class that wraps the `CalcArea` function and creates fields to store input parameters, as follows:</span></span>  
  
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
  
 <span data-ttu-id="0940d-110">Para usar `AreaClass`, puede crear un objeto `AreaClass` y establecer las propiedades `Base` y `Height` como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0940d-110">To use the `AreaClass`, you can create an `AreaClass` object, and set the `Base` and `Height` properties as shown in the following code:</span></span>  
  
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
  
 <span data-ttu-id="0940d-111">Observe que el procedimiento `TestArea` no comprueba el valor del campo `Area` después de llamar al método `CalcArea`.</span><span class="sxs-lookup"><span data-stu-id="0940d-111">Notice that the `TestArea` procedure does not check the value of the `Area` field after calling the `CalcArea` method.</span></span> <span data-ttu-id="0940d-112">Dado que `CalcArea` se ejecuta en un subproceso independiente, no se garantiza que el campo `Area` se establezca si se comprueba inmediatamente después de llamar a `Thread.Start`.</span><span class="sxs-lookup"><span data-stu-id="0940d-112">Because `CalcArea` runs on a separate thread, the `Area` field is not guaranteed to be set if you check it immediately after calling `Thread.Start`.</span></span> <span data-ttu-id="0940d-113">En la sección siguiente se explica una manera mejor de devolver valores desde procedimientos multiproceso.</span><span class="sxs-lookup"><span data-stu-id="0940d-113">The next section discusses a better way to return values from multithreaded procedures.</span></span>  
  
## <a name="returning-values-from-multithreaded-procedures"></a><span data-ttu-id="0940d-114">Devolución de valores desde procedimientos multiproceso</span><span class="sxs-lookup"><span data-stu-id="0940d-114">Returning Values from Multithreaded Procedures</span></span>  
 <span data-ttu-id="0940d-115">La devolución de valores desde procedimientos que se ejecutan en subprocesos independientes se complica por el hecho de que los procedimientos no pueden ser funciones y no pueden usar argumentos `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="0940d-115">Returning values from procedures that run on separate threads is complicated by the fact that the procedures cannot be functions and cannot use `ByRef` arguments.</span></span> <span data-ttu-id="0940d-116">La manera más fácil de devolver valores es usar el componente <xref:System.ComponentModel.BackgroundWorker> para administrar los subprocesos, generar un evento cuando la tarea esté hecha y procesar los resultados con un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="0940d-116">The easiest way to return values is to use the <xref:System.ComponentModel.BackgroundWorker> component to manage your threads and raise an event when the task is done, and process the results with an event handler.</span></span>  
  
 <span data-ttu-id="0940d-117">En el ejemplo siguiente se devuelve un valor al generar un evento desde un procedimiento que se ejecuta en un subproceso independiente:</span><span class="sxs-lookup"><span data-stu-id="0940d-117">The following example returns a value by raising an event from a procedure running on a separate thread:</span></span>  
  
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
  
 <span data-ttu-id="0940d-118">Puede proporcionar parámetros y devolver valores a subprocesos de grupo de subprocesos mediante la variable opcional de objeto de estado `ByVal` del método <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="0940d-118">You can provide parameters and return values to thread-pool threads by using the optional `ByVal` state-object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="0940d-119">Los subprocesos de temporizador de subprocesos también admiten un objeto de estado para este fin.</span><span class="sxs-lookup"><span data-stu-id="0940d-119">Thread-timer threads also support a state object for this purpose.</span></span> <span data-ttu-id="0940d-120">Para obtener información sobre la agrupación de subprocesos y temporizadores de subprocesos, vea [agrupación de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[agrupación de subprocesos](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) y [temporizadores](../../../../standard/threading/timers.md).</span><span class="sxs-lookup"><span data-stu-id="0940d-120">For information on thread pooling and thread timers, see [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)[Thread Pooling](http://msdn.microsoft.com/library/4b8bb2c8-8ca4-457c-9afd-d11bc9a05701) and [Timers](../../../../standard/threading/timers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0940d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0940d-121">See Also</span></span>  
 [<span data-ttu-id="0940d-122">Tutorial: Multithreading con el componente BackgroundWorker (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0940d-122">Walkthrough: Multithreading with the BackgroundWorker Component (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [<span data-ttu-id="0940d-123">Agrupación de subprocesos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0940d-123">Thread Pooling (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [<span data-ttu-id="0940d-124">Sincronización de subprocesos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0940d-124">Thread Synchronization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="0940d-125">Eventos</span><span class="sxs-lookup"><span data-stu-id="0940d-125">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="0940d-126">Aplicaciones multiproceso (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0940d-126">Multithreaded Applications (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="0940d-127">Delegados</span><span class="sxs-lookup"><span data-stu-id="0940d-127">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="0940d-128">Subprocesamiento múltiple en componentes</span><span class="sxs-lookup"><span data-stu-id="0940d-128">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
