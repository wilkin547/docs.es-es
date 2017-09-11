---
title: "Parámetros y valores devueltos para procedimientos multiproceso (C#)"
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
ms.assetid: ba63c30c-d9f0-4962-b5c7-9d83ba851e6a
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5e377a006409dbae49b3c00297f69e8d55a01295
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="parameters-and-return-values-for-multithreaded-procedures-c"></a><span data-ttu-id="dc3ad-102">Parámetros y valores devueltos para procedimientos multiproceso (C#)</span><span class="sxs-lookup"><span data-stu-id="dc3ad-102">Parameters and Return Values for Multithreaded Procedures (C#)</span></span>
<span data-ttu-id="dc3ad-103">El suministro y la devolución de valores en una aplicación multiproceso son complicados porque se debe pasar una referencia a un procedimiento que no tome ningún argumento ni devuelva ningún valor al constructor de la clase de subproceso.</span><span class="sxs-lookup"><span data-stu-id="dc3ad-103">Supplying and returning values in a multithreaded application is complicated because the constructor for the thread class must be passed a reference to a procedure that takes no arguments and returns no value.</span></span> <span data-ttu-id="dc3ad-104">En las secciones siguientes se muestran algunas maneras sencillas de proporcionar parámetros y devolver valores desde procedimientos en subprocesos independientes.</span><span class="sxs-lookup"><span data-stu-id="dc3ad-104">The following sections show some simple ways to supply parameters and return values from procedures on separate threads.</span></span>  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a><span data-ttu-id="dc3ad-105">Suministro de parámetros para procedimientos multiproceso</span><span class="sxs-lookup"><span data-stu-id="dc3ad-105">Supplying Parameters for Multithreaded Procedures</span></span>  
 <span data-ttu-id="dc3ad-106">La mejor manera de proporcionar parámetros para una llamada al método multiproceso es encapsular el método de destino en una clase y definir campos para esa clase que sirvan como parámetros para el nuevo subproceso.</span><span class="sxs-lookup"><span data-stu-id="dc3ad-106">The best way to supply parameters for a multithreaded method call is to wrap the target method in a class and define fields for that class that will serve as parameters for the new thread.</span></span> <span data-ttu-id="dc3ad-107">La ventaja de este enfoque es que puede crear una nueva instancia de la clase, con sus propios parámetros, cada vez que quiera iniciar un nuevo subproceso.</span><span class="sxs-lookup"><span data-stu-id="dc3ad-107">The advantage of this approach is that you can create a new instance of the class, with its own parameters, every time you want to start a new thread.</span></span> <span data-ttu-id="dc3ad-108">Por ejemplo, imagine que tiene una función que calcula el área de un triángulo, como en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc3ad-108">For example, suppose you have a function that calculates the area of a triangle, as in the following code:</span></span>  
  
```csharp  
double CalcArea(double Base, double Height)  
{  
    return 0.5 * Base * Height;  
}  
```  
  
 <span data-ttu-id="dc3ad-109">Puede escribir una clase que encapsule la función `CalcArea` y cree campos para almacenar parámetros de entrada como sigue:</span><span class="sxs-lookup"><span data-stu-id="dc3ad-109">You can write a class that wraps the `CalcArea` function and creates fields to store input parameters, as follows:</span></span>  
  
```csharp  
class AreaClass  
{  
    public double Base;  
    public double Height;  
    public double Area;  
    public void CalcArea()  
    {  
        Area = 0.5 * Base * Height;  
        MessageBox.Show("The area is: " + Area.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="dc3ad-110">Para usar `AreaClass`, puede crear un objeto `AreaClass` y establecer las propiedades `Base` y `Height` como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc3ad-110">To use the `AreaClass`, you can create an `AreaClass` object, and set the `Base` and `Height` properties as shown in the following code:</span></span>  
  
```csharp  
protected void TestArea()  
{  
    AreaClass AreaObject = new AreaClass();  
  
    System.Threading.Thread Thread =  
        new System.Threading.Thread(AreaObject.CalcArea);  
    AreaObject.Base = 30;  
    AreaObject.Height = 40;  
    Thread.Start();  
}  
```  
  
 <span data-ttu-id="dc3ad-111">Observe que el procedimiento `TestArea` no comprueba el valor del campo `Area` después de llamar al método `CalcArea`.</span><span class="sxs-lookup"><span data-stu-id="dc3ad-111">Notice that the `TestArea` procedure does not check the value of the `Area` field after calling the `CalcArea` method.</span></span> <span data-ttu-id="dc3ad-112">Dado que `CalcArea` se ejecuta en un subproceso independiente, no se garantiza que el campo `Area` se establezca si se comprueba inmediatamente después de llamar a `Thread.Start`.</span><span class="sxs-lookup"><span data-stu-id="dc3ad-112">Because `CalcArea` runs on a separate thread, the `Area` field is not guaranteed to be set if you check it immediately after calling `Thread.Start`.</span></span> <span data-ttu-id="dc3ad-113">En la sección siguiente se explica una manera mejor de devolver valores desde procedimientos multiproceso.</span><span class="sxs-lookup"><span data-stu-id="dc3ad-113">The next section discusses a better way to return values from multithreaded procedures.</span></span>  
  
## <a name="returning-values-from-multithreaded-procedures"></a><span data-ttu-id="dc3ad-114">Devolución de valores desde procedimientos multiproceso</span><span class="sxs-lookup"><span data-stu-id="dc3ad-114">Returning Values from Multithreaded Procedures</span></span>  
 <span data-ttu-id="dc3ad-115">La devolución de valores desde procedimientos que se ejecutan en subprocesos independientes se complica por el hecho de que los procedimientos no pueden ser funciones y no pueden usar argumentos `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="dc3ad-115">Returning values from procedures that run on separate threads is complicated by the fact that the procedures cannot be functions and cannot use `ByRef` arguments.</span></span> <span data-ttu-id="dc3ad-116">La manera más fácil de devolver valores es usar el componente <xref:System.ComponentModel.BackgroundWorker> para administrar los subprocesos, generar un evento cuando la tarea esté hecha y procesar los resultados con un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="dc3ad-116">The easiest way to return values is to use the <xref:System.ComponentModel.BackgroundWorker> component to manage your threads and raise an event when the task is done, and process the results with an event handler.</span></span>  
  
 <span data-ttu-id="dc3ad-117">En el ejemplo siguiente se devuelve un valor al generar un evento desde un procedimiento que se ejecuta en un subproceso independiente:</span><span class="sxs-lookup"><span data-stu-id="dc3ad-117">The following example returns a value by raising an event from a procedure running on a separate thread:</span></span>  
  
```csharp  
class AreaClass2  
{  
    public double Base;  
    public double Height;  
    public double CalcArea()  
    {  
        // Calculate the area of a triangle.  
        return 0.5 * Base * Height;  
    }  
}  
  
private System.ComponentModel.BackgroundWorker BackgroundWorker1  
    = new System.ComponentModel.BackgroundWorker();  
  
private void TestArea2()  
{  
    InitializeBackgroundWorker();  
  
    AreaClass2 AreaObject2 = new AreaClass2();  
    AreaObject2.Base = 30;  
    AreaObject2.Height = 40;  
  
    // Start the asynchronous operation.  
    BackgroundWorker1.RunWorkerAsync(AreaObject2);  
}  
  
private void InitializeBackgroundWorker()  
{  
    // Attach event handlers to the BackgroundWorker object.  
    BackgroundWorker1.DoWork +=  
        new System.ComponentModel.DoWorkEventHandler(BackgroundWorker1_DoWork);  
    BackgroundWorker1.RunWorkerCompleted +=  
        new System.ComponentModel.RunWorkerCompletedEventHandler(BackgroundWorker1_RunWorkerCompleted);  
}  
  
private void BackgroundWorker1_DoWork(  
    object sender,  
    System.ComponentModel.DoWorkEventArgs e)  
{  
    AreaClass2 AreaObject2 = (AreaClass2)e.Argument;  
    // Return the value through the Result property.  
    e.Result = AreaObject2.CalcArea();  
}  
  
private void BackgroundWorker1_RunWorkerCompleted(  
    object sender,  
    System.ComponentModel.RunWorkerCompletedEventArgs e)  
{  
    // Access the result through the Result property.  
    double Area = (double)e.Result;  
    MessageBox.Show("The area is: " + Area.ToString());  
}  
```  
  
 <span data-ttu-id="dc3ad-118">Puede proporcionar parámetros y devolver valores a subprocesos de grupo de subprocesos mediante la variable opcional de objeto de estado `ByVal` del método <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="dc3ad-118">You can provide parameters and return values to thread-pool threads by using the optional `ByVal` state-object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="dc3ad-119">Los subprocesos de temporizador de subprocesos también admiten un objeto de estado para este fin.</span><span class="sxs-lookup"><span data-stu-id="dc3ad-119">Thread-timer threads also support a state object for this purpose.</span></span> <span data-ttu-id="dc3ad-120">Para más información sobre la agrupación de subprocesos y los temporizadores de subprocesos, vea [Thread Pooling (C#) (Agrupación de subprocesos (C#))](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) y [Thread Timers (C#) (Temporizadores de subprocesos (C#))](../../../../csharp/programming-guide/concepts/threading/thread-timers.md).</span><span class="sxs-lookup"><span data-stu-id="dc3ad-120">For information on thread pooling and thread timers, see [Thread Pooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) and [Thread Timers (C#)](../../../../csharp/programming-guide/concepts/threading/thread-timers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc3ad-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc3ad-121">See Also</span></span>  
 <span data-ttu-id="dc3ad-122">[Walkthrough: Multithreading with the BackgroundWorker Component (C#) (Tutorial: Multithreading con el componente BackgroundWorker (C#))](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md) </span><span class="sxs-lookup"><span data-stu-id="dc3ad-122">[Walkthrough: Multithreading with the BackgroundWorker Component (C#)](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md) </span></span>  
 <span data-ttu-id="dc3ad-123">[Thread Pooling (C#) (Agrupación de subprocesos (C#))](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) </span><span class="sxs-lookup"><span data-stu-id="dc3ad-123">[Thread Pooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) </span></span>  
 <span data-ttu-id="dc3ad-124">[Sincronización de subprocesos (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="dc3ad-124">[Thread Synchronization (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md) </span></span>  
 <span data-ttu-id="dc3ad-125">[Eventos](../../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="dc3ad-125">[Events](../../../../csharp/programming-guide/events/index.md) </span></span>  
 <span data-ttu-id="dc3ad-126">[Aplicaciones multiproceso (C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md) </span><span class="sxs-lookup"><span data-stu-id="dc3ad-126">[Multithreaded Applications (C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md) </span></span>  
 <span data-ttu-id="dc3ad-127">[Delegados](../../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="dc3ad-127">[Delegates](../../../../csharp/programming-guide/delegates/index.md) </span></span>  
 [<span data-ttu-id="dc3ad-128">Subprocesamiento múltiple en componentes</span><span class="sxs-lookup"><span data-stu-id="dc3ad-128">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)

