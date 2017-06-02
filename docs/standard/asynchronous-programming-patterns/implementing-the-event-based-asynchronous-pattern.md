---
title: "Implementar el modelo asincr&#243;nico basado en eventos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "modelo asincrónico basado en eventos"
  - "ProgressChangedEventArgs (clase)"
  - "BackgroundWorker (componente)"
  - "eventos [.NET Framework], asincrónicos"
  - "modelo asincrónico"
  - "AsyncOperationManager (clase)"
  - "subproceso [.NET Framework], características asincrónicas"
  - "componentes [.NET Framework], asincrónicos"
  - "AsyncOperation (clase)"
  - "AsyncCompletedEventArgs (clase)"
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Implementar el modelo asincr&#243;nico basado en eventos
Si está escribiendo una clase con algunas operaciones que puedan incurrir en retrasos notables, considere la posibilidad de darle funcionalidad asincrónica implementando [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
 El modelo asincrónico basado en eventos proporciona una forma estandarizada de empaquetar una clase que tiene características asincrónicas. Si se implementa con clases auxiliares como <xref:System.ComponentModel.AsyncOperationManager>, la clase funcionará correctamente bajo cualquier modelo de aplicación, incluidos [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], aplicaciones de consola y aplicaciones de Windows Forms.  
  
 Para obtener un ejemplo que implementa el modelo asincrónico basado en eventos, vea [Cómo: implementar un componente que admita el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 Para las operaciones asincrónicas simples, puede encontrar el <xref:System.ComponentModel.BackgroundWorker> componente adecuado. Para obtener más información acerca de <xref:System.ComponentModel.BackgroundWorker>, consulte [Cómo: ejecutar una operación en segundo plano](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).  
  
 En la lista siguiente describe las características del modelo asincrónico basado en eventos, se tratan en este tema.  
  
-   Posibilidad de implementar el modelo asincrónico basado en eventos  
  
-   Métodos asincrónicos de nomenclatura  
  
-   Opcionalmente, admiten la cancelación  
  
-   Opcionalmente, admitir la propiedad IsBusy  
  
-   Opcionalmente, proporcionan compatibilidad para informes de progreso  
  
-   Opcionalmente, proporcionan compatibilidad para devolver resultados incrementales  
  
-   Control Out y Ref parámetros en métodos  
  
## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a>Posibilidad de implementar el modelo asincrónico basado en eventos  
 Considere la posibilidad de implementar el modelo asincrónico basado en eventos cuando:  
  
-   Los clientes de la clase no es necesario <xref:System.Threading.WaitHandle> y <xref:System.IAsyncResult> objetos disponibles para las operaciones asincrónicas, lo que significa que el sondeo y <xref:System.Threading.WaitHandle.WaitAll%2A> o <xref:System.Threading.WaitHandle.WaitAny%2A> tendrá que ser generados por el cliente.  
  
-   Desea que las operaciones asincrónicas para ser administrados por el cliente con el modelo conocido de eventos y delegados.  
  
 Cualquier operación es un candidato para una implementación asincrónica, pero deben considerarse la esperada incurrir en largas latencias. Son especialmente adecuadas las operaciones en el que los clientes llamar a un método y le notificará cuando haya terminado, con ninguna intervención necesaria. También son adecuadas las operaciones que se ejecutan continuamente, notificar periódicamente a los clientes de progreso, resultados incrementales o cambios de estado.  
  
 Para obtener más información sobre cuándo debe admitir el modelo asincrónico basado en eventos, vea [decidir cuándo implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md).  
  
## <a name="naming-asynchronous-methods"></a>Métodos asincrónicos de nomenclatura  
 Para cada método sincrónico *MethodName* para que desea proporcionar un homólogo asincrónico:  
  
 Definir una *MethodName* `Async` método que:  
  
-   Devuelve `void`.  
  
-   Toma los mismos parámetros que la *MethodName* método.  
  
-   Acepte varias invocaciones.  
  
 Definir una *MethodName* `Async` sobrecarga, idéntica a *MethodName*`Async`, pero con un parámetro con valor de objeto adicional denominado `userState`. Si está preparado para administrar varias invocaciones simultáneas de su método, en cuyo caso el `userState` valor se entregará a todos los controladores de eventos para diferenciar las invocaciones del método. También puede hacerlo simplemente como un lugar para almacenar el estado de usuario para su posterior recuperación.  
  
 En cada *MethodName* `Async` firma del método:  
  
1.  Defina el evento siguiente en la misma clase que el método:  
  
    ```vb  
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler  
    ```  
  
    ```csharp  
    public event MethodNameCompletedEventHandler MethodNameCompleted;  
    ```  
  
2.  Defina el delegado siguiente y <xref:System.ComponentModel.AsyncCompletedEventArgs>. Éstos probablemente se definirán fuera de la propia clase, pero en el mismo espacio de nombres.  
  
    ```vb  
    Public Delegate Sub MethodNameCompletedEventHandler( _  
        ByVal sender As Object, _  
        ByVal e As MethodNameCompletedEventArgs)  
  
    Public Class MethodNameCompletedEventArgs  
        Inherits System.ComponentModel.AsyncCompletedEventArgs  
    Public ReadOnly Property Result() As MyReturnType  
    End Property  
    ```  
  
    ```csharp  
    public delegate void MethodNameCompletedEventHandler(object sender,   
        MethodNameCompletedEventArgs e);  
  
    public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs  
    {  
        public MyReturnType Result { get; }  
    }  
    ```  
  
    -   Asegúrese de que el *MethodName* `CompletedEventArgs` clase expone sus miembros como propiedades de sólo lectura y no campos como campos impiden el enlace de datos.  
  
    -   No se define ninguna <xref:System.ComponentModel.AsyncCompletedEventArgs>-derivadas de las clases para los métodos que no generan resultados. Simplemente utilice una instancia de <xref:System.ComponentModel.AsyncCompletedEventArgs> propio.  
  
        > [!NOTE]
        >  Es perfectamente aceptable, cuando sea factible y adecuado, reutilizar el delegado y <xref:System.ComponentModel.AsyncCompletedEventArgs> tipos. En este caso, la nomenclatura no será coherente con el nombre del método, desde un delegado dado y <xref:System.ComponentModel.AsyncCompletedEventArgs> estarán asociados a un único método.  
  
## <a name="optionally-support-cancellation"></a>Opcionalmente, admiten la cancelación  
 Si su clase admite la cancelación de operaciones asincrónicas, cancelación debe exponer al cliente tal como se describe a continuación. Tenga en cuenta que hay dos puntos de decisión que deben resolverse antes de definir la compatibilidad de cancelación:  
  
-   ¿Tiene la clase, incluidos los futuros anticipados, sólo una operación asincrónica que admite la cancelación?  
  
-   ¿Puede que las operaciones asincrónicas que admiten la cancelación con varias operaciones pendientes? ¿Es decir, hace la *MethodName* `Async` método toma un `userState` parámetro, y permiten varias invocaciones antes de esperar a que finalice cualquiera?  
  
 Utilice las respuestas a estas dos preguntas en la tabla siguiente para determinar cuál debería ser la firma para el método de cancelación.  
  
### <a name="visual-basic"></a>Visual Basic  
  
||Varias operaciones simultáneas|Una única operación cada vez|  
|------|------------------------------------------------|----------------------------------|  
|Una operación asincrónica en toda la clase|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|  
|Varias operaciones asincrónicas en la clase|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|  
  
### <a name="c"></a>C#  
  
||Varias operaciones simultáneas|Una única operación cada vez|  
|------|------------------------------------------------|----------------------------------|  
|Una operación asincrónica en toda la clase|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|  
|Varias operaciones asincrónicas en la clase|`void CancelAsync(object userState);`|`void CancelAsync();`|  
  
 Si define la `CancelAsync(object userState)` método, los clientes deben ser cuidadoso al elegir sus valores de estado para que sean capaces de diferenciar entre todos los métodos asincrónicos invocados en el objeto y no sólo entre todas las invocaciones de un único método asincrónico.  
  
 La decisión de la versión de operaciones asincrónicas solo el nombre *MethodName* `AsyncCancel` se basa en la capacidad detectar más fácilmente el método en un entorno de diseño como IntelliSense de Visual Studio. Esto agrupa a los miembros relacionados y los distingue de otros miembros que no tienen nada que ver con la funcionalidad asincrónica. Si piensa que puede haber adicionales agregan operaciones asincrónicas en versiones posteriores, es mejor definir `CancelAsync`.  
  
 No defina varios métodos de la tabla anterior en la misma clase. Que no tendrá sentido, o recargará la interfaz de clase con una proliferación de métodos.  
  
 Estos métodos normalmente devolverá inmediatamente y la operación puede o no, cancelarse realmente. En el controlador de eventos para el *MethodName* `Completed` evento, el *MethodName* `CompletedEventArgs` objeto contiene un `Cancelled` campo, que los clientes pueden utilizar para determinar si se ha producido la cancelación.  
  
 Aténgase a la semántica de cancelación se describe en [prácticas recomendadas para implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-support-the-isbusy-property"></a>Opcionalmente, admitir la propiedad IsBusy  
 Si su clase admite varias invocaciones simultáneas, considere la posibilidad de exponer una `IsBusy` propiedad. Esto permite a los desarrolladores determinar si un *MethodName* `Async` método se está ejecutando sin detectar una excepción desde el *MethodName* `Async` método.  
  
 Respetar el `IsBusy` semántica se describe en [prácticas recomendadas para implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-provide-support-for-progress-reporting"></a>Opcionalmente, proporcionan compatibilidad para informes de progreso  
 Es con frecuencia deseable para una operación asincrónica para notificar el progreso durante su funcionamiento. El modelo asincrónico basado en eventos proporciona instrucciones para hacerlo.  
  
-   Definir un evento generado por la operación asincrónica y se invoca en el subproceso adecuado. El <xref:System.ComponentModel.ProgressChangedEventArgs> objeto lleva un indicador de progreso con valores enteros que debe estar entre 0 y 100.  
  
-   Denomine este evento como sigue:  
  
    -   `ProgressChanged`Si la clase tiene varias operaciones asincrónicas (o se espera que crezca para incluir varias operaciones asincrónicas en versiones futuras);  
  
    -   *MethodName* `ProgressChanged` si la clase tiene una operación asincrónica única.  
  
     Esta opción de denominación es semejante realizados por el método de cancelación, tal como se describe en la sección de cancelación de soporte técnico si lo desea.  
  
 Este evento debería utilizar la <xref:System.ComponentModel.ProgressChangedEventHandler> firma de delegado y la <xref:System.ComponentModel.ProgressChangedEventArgs> clase. Como alternativa, si se pueden proporcionar un indicador de progreso mas específico de dominio (para la instancia, bytes leídos y bytes totales para una operación de descarga), a continuación, debe definir una clase derivada de <xref:System.ComponentModel.ProgressChangedEventArgs>.  
  
 Tenga en cuenta que solo hay un `ProgressChanged` o *MethodName* `ProgressChanged` eventos para la clase, independientemente del número de métodos asincrónicos que admite. Se esperan que los clientes utilicen la `userState` objeto que se pasa a la *MethodName* `Async` métodos para distinguir entre las actualizaciones de progreso en varias operaciones simultáneas.  
  
 Puede haber situaciones en las que varias operaciones admiten el progreso y cada una devuelve un indicador diferente. En este caso, un único `ProgressChanged` evento no es adecuado y puede admitir varios `ProgressChanged` eventos. En este caso, utilice un patrón de nomenclatura de *MethodName* `ProgressChanged` para cada *MethodName* `Async` método.  
  
 Aténgase a la semántica de informes de progreso descrita [prácticas recomendadas para implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="optionally-provide-support-for-returning-incremental-results"></a>Opcionalmente, proporcionan compatibilidad para devolver resultados incrementales  
 A veces, una operación asincrónica puede devolver resultados incrementales antes de finalizar. Hay una serie de opciones que puede utilizar para admitir este escenario. Siguen algunos ejemplos.  
  
### <a name="single-operation-class"></a>Clase de operación única  
 Si una clase sólo admite una operación asincrónica única y esa operación es capaz de devolver resultados incrementales, a continuación:  
  
-   Extender la <xref:System.ComponentModel.ProgressChangedEventArgs> escriba para llevar los datos del resultado incremental y defina un *MethodName* `ProgressChanged` eventos con este datos extendidos.  
  
-   Elevar esta *MethodName* `ProgressChanged` eventos cuando haya un resultado incremental al informe.  
  
 Esta solución se aplica específicamente a una clase única operaciones asincrónicas porque no hay ningún problema con el mismo evento devuelva resultados incrementales en "todas las operaciones", como sucede el *MethodName* `ProgressChanged` evento.  
  
### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a>Clase de varias operaciones con resultados incrementales homogéneos  
 En este caso, la clase admite varios métodos asincrónicos, cada uno de ellos capaces de devolver resultados incrementales, y estos resultados incrementales tienen todos el mismo tipo de datos.  
  
 Seguir el modelo descrito anteriormente para las clases de operación única, como el mismo <xref:System.EventArgs> estructura funcionará para todos los resultados incrementales. Definir una `ProgressChanged` evento en lugar de un *MethodName* `ProgressChanged` evento, ya que se aplica a varios métodos asincrónicos.  
  
### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a>Clase de varias operaciones con resultados incrementales heterogéneos  
 Si su clase admite varios métodos asincrónicos, cada uno devuelve un tipo diferente de datos, debe:  
  
-   Separe el resultado incremental informes desde los informes de progreso.  
  
-   Definen otro *MethodName* `ProgressChanged` eventos con adecuada <xref:System.EventArgs> para cada método asincrónico administrar los datos del resultado incremental de ese método.  
  
 Invocar ese controlador de eventos en el subproceso adecuado, tal como se describe en [prácticas recomendadas para implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).  
  
## <a name="handling-out-and-ref-parameters-in-methods"></a>Control Out y Ref parámetros en métodos  
 Aunque el uso de `out` y `ref` es, en general, en absoluto en .NET Framework, estas son las reglas que seguir cuando están presentes:  
  
 Dado un método sincrónico *MethodName*:  
  
-   `out`parámetros de *MethodName* no debe formar parte de *MethodName*`Async`. En su lugar, deberían formar parte de *MethodName* `CompletedEventArgs` con el mismo nombre que su parámetro equivalente en *MethodName* (a menos que haya un nombre más adecuado).  
  
-   `ref`parámetros de *MethodName* debería aparecer como parte de *MethodName*`Async`y como parte de *MethodName* `CompletedEventArgs` con el mismo nombre que su parámetro equivalente en *MethodName* (a menos que haya un nombre más adecuado).  
  
 Por ejemplo, con:  
  
```vb  
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer  
```  
  
```csharp  
public int MethodName(string arg1, ref string arg2, out string arg3);  
```  
  
 El método asincrónico y su <xref:System.ComponentModel.AsyncCompletedEventArgs> clase tendría este aspecto:  
  
```vb  
Public Sub MethodNameAsync(ByVal arg1 As String, ByVal arg2 As String)  
  
Public Class MethodNameCompletedEventArgs  
    Inherits System.ComponentModel.AsyncCompletedEventArgs  
    Public ReadOnly Property Result() As Integer   
    End Property  
    Public ReadOnly Property Arg2() As String   
    End Property  
    Public ReadOnly Property Arg3() As String   
    End Property  
End Class  
```  
  
```csharp  
public void MethodNameAsync(string arg1, string arg2);  
  
public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs  
{  
    public int Result { get; };  
    public string Arg2 { get; };  
    public string Arg3 { get; };  
}  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ComponentModel.ProgressChangedEventArgs>   
 <xref:System.ComponentModel.AsyncCompletedEventArgs>   
 [Cómo: implementar un componente que admita el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)   
 [Cómo: ejecutar una operación en segundo plano](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Cómo: implementar un formulario que utiliza una operación en segundo plano](../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)   
 [Decidir cuándo implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)   
 [Programación multiproceso con el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)   
 [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)