---
title: "Parámetros y valores devueltos para procedimientos multiproceso (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ba63c30c-d9f0-4962-b5c7-9d83ba851e6a
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fec0ad955439f0cd683ad56c8d6433eed2417304
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="parameters-and-return-values-for-multithreaded-procedures-c"></a>Parámetros y valores devueltos para procedimientos multiproceso (C#)
El suministro y la devolución de valores en una aplicación multiproceso son complicados porque se debe pasar una referencia a un procedimiento que no tome ningún argumento ni devuelva ningún valor al constructor de la clase de subproceso. En las secciones siguientes se muestran algunas maneras sencillas de proporcionar parámetros y devolver valores desde procedimientos en subprocesos independientes.  
  
## <a name="supplying-parameters-for-multithreaded-procedures"></a>Suministro de parámetros para procedimientos multiproceso  
 La mejor manera de proporcionar parámetros para una llamada al método multiproceso es encapsular el método de destino en una clase y definir campos para esa clase que sirvan como parámetros para el nuevo subproceso. La ventaja de este enfoque es que puede crear una nueva instancia de la clase, con sus propios parámetros, cada vez que quiera iniciar un nuevo subproceso. Por ejemplo, imagine que tiene una función que calcula el área de un triángulo, como en el código siguiente:  
  
```csharp  
double CalcArea(double Base, double Height)  
{  
    return 0.5 * Base * Height;  
}  
```  
  
 Puede escribir una clase que encapsule la función `CalcArea` y cree campos para almacenar parámetros de entrada como sigue:  
  
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
  
 Para usar `AreaClass`, puede crear un objeto `AreaClass` y establecer las propiedades `Base` y `Height` como se muestra en el código siguiente:  
  
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
  
 Observe que el procedimiento `TestArea` no comprueba el valor del campo `Area` después de llamar al método `CalcArea`. Dado que `CalcArea` se ejecuta en un subproceso independiente, no se garantiza que el campo `Area` se establezca si se comprueba inmediatamente después de llamar a `Thread.Start`. En la sección siguiente se explica una manera mejor de devolver valores desde procedimientos multiproceso.  
  
## <a name="returning-values-from-multithreaded-procedures"></a>Devolución de valores desde procedimientos multiproceso  
 La devolución de valores desde procedimientos que se ejecutan en subprocesos independientes se complica por el hecho de que los procedimientos no pueden ser funciones y no pueden usar argumentos `ByRef`. La manera más fácil de devolver valores es usar el componente <xref:System.ComponentModel.BackgroundWorker> para administrar los subprocesos, generar un evento cuando la tarea esté hecha y procesar los resultados con un controlador de eventos.  
  
 En el ejemplo siguiente se devuelve un valor al generar un evento desde un procedimiento que se ejecuta en un subproceso independiente:  
  
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
  
 Puede proporcionar parámetros y devolver valores a subprocesos de grupo de subprocesos mediante la variable opcional de objeto de estado `ByVal` del método <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>. Los subprocesos de temporizador de subprocesos también admiten un objeto de estado para este fin. Para más información sobre la agrupación de subprocesos y los temporizadores de subprocesos, vea [Thread Pooling (C#) (Agrupación de subprocesos (C#))](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md) y [Thread Timers (C#) (Temporizadores de subprocesos (C#))](../../../../csharp/programming-guide/concepts/threading/thread-timers.md).  
  
## <a name="see-also"></a>Vea también  
 [Walkthrough: Multithreading with the BackgroundWorker Component (C#) (Tutorial: Multithreading con el componente BackgroundWorker (C#))](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)  
 [Agrupación de subprocesos (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)  
 [Sincronización de subprocesos (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
 [Eventos](../../../../csharp/programming-guide/events/index.md)  
 [Aplicaciones multiproceso (C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [Delegados](../../../../csharp/programming-guide/delegates/index.md)  
 [Subprocesamiento múltiple en componentes](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)
