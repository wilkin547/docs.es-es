---
title: "Procedimientos recomendados para implementar el modelo asincr&#243;nico basado en eventos | Microsoft Docs"
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
  - "AsyncOperationManager (clase)"
  - "subproceso [.NET Framework], características asincrónicas"
  - "AsyncOperation (clase)"
  - "AsyncCompletedEventArgs (clase)"
ms.assetid: 4acd2094-4f46-4eff-9190-92d0d9ff47db
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Procedimientos recomendados para implementar el modelo asincr&#243;nico basado en eventos
El modelo asincrónico basado en eventos proporciona un método eficaz de exponer el comportamiento asincrónico en clases, con una semántica de delegados y eventos ya conocida. Para implementar el modelo asincrónico basado en eventos, es necesario cumplir algunos requisitos de comportamiento específicos. En las secciones siguientes se describen los requisitos y las instrucciones que se deben tener en cuenta a la hora de implementar una clase que responda a este modelo.  
  
 Para obtener información general, vea [Implementing the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).  
  
## Garantías de comportamiento necesarias  
 Si implementa el modelo asincrónico basado en eventos, debe ofrecer una serie de garantías que aseguren un comportamiento apropiado de su clase en el que puedan confiar sus clientes.  
  
### Finalización  
 Invoque siempre al controlador de eventos *MethodName*`Completed` cuando se produzca un error, una cancelación o una finalización correcta. Las aplicaciones jamás deben encontrarse en una situación en la que permanezcan inactivas sin que se produzca una finalización. La única excepción a esta regla es que la misma operación asincrónica esté diseñada para que nunca finalice.  
  
### Evento Completed y EventArgs  
 En cada método *MethodName*`Async`, aplique los siguientes requisitos de diseño:  
  
-   Defina un evento *MethodName*`Completed` en la misma clase que el método.  
  
-   Defina una clase <xref:System.EventArgs> y un delegado adjunto para el evento *MethodName*`Completed` que deriva de la clase <xref:System.ComponentModel.AsyncCompletedEventArgs>. La forma del nombre de clase predeterminado debe ser *MethodName*`CompletedEventArgs`.  
  
-   Asegúrese de que la clase <xref:System.EventArgs> sea específica de los valores devueltos del método *MethodName*. Cuando use la clase <xref:System.EventArgs>, nunca les pida a los desarrolladores que conviertan el resultado.  
  
     En el ejemplo de código siguiente se muestra una implementación correcta e incorrecta, respectivamente, de este requisito de diseño.  
  
```csharp  
// Good design  
private void Form1_MethodNameCompleted(object sender, xxxCompletedEventArgs e)   
{   
    DemoType result = e.Result;  
}  
  
// Bad design  
private void Form1_MethodNameCompleted(object sender, MethodNameCompletedEventArgs e)   
{   
    DemoType result = (DemoType)(e.Result);  
}  
```  
  
-   No defina una clase <xref:System.EventArgs> para métodos que devuelvan `void`. En su lugar, use una instancia de la clase <xref:System.ComponentModel.AsyncCompletedEventArgs>.  
  
-   Asegúrese de que siempre genera el evento *MethodName*`Completed`. Este evento debe generarse cuando se produce una finalización correcta, un error o una cancelación. Las aplicaciones jamás deben encontrarse en una situación en la que permanezcan inactivas sin que se produzca una finalización.  
  
-   Asegúrese de que captura todas las excepciones que se producen en la operación asincrónica y de que asigna la excepción capturada a la propiedad <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A>.  
  
-   Si se produjo un error al finalizar la tarea, los resultados no deben ser accesibles. Si la propiedad <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> no es `null`, asegúrese de que el acceso a cualquier propiedad de la estructura <xref:System.EventArgs> genera una excepción. Use el método <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A> para realizar esta verificación.  
  
-   Cree un modelo de error para los agotamientos del tiempo de espera. Cuando se agote el tiempo de espera, genere el evento *MethodName*`Completed` y asigne <xref:System.TimeoutException> a la propiedad <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A>.  
  
-   Si su clase admite varias invocaciones simultáneas, asegúrese de que el evento *MethodName*`Completed` contiene el objeto `userSuppliedState` apropiado.  
  
-   Asegúrese de que el evento *MethodName*`Completed` se genera en el subproceso apropiado y en el momento adecuado del ciclo de vida de la aplicación. Para obtener más información, vea la sección Subprocesos y contextos.  
  
### Ejecución simultánea de operaciones  
  
-   Si su clase admite varias invocaciones simultáneas, habilite al desarrollador para que realice un seguimiento por separado de cada invocación; para ello, defina la sobrecarga *MethodName*`Async` que toma un parámetro de estado con valor de objeto o identificador de tarea, denominado `userSuppliedState`. Este parámetro siempre debe ser el último de la signatura del método *MethodName*`Async`.  
  
-   Si su clase define la sobrecarga *MethodName*`Async` que toma un parámetro de estado con valor de objeto o identificador de tarea, asegúrese de realizar un seguimiento de la duración de la operación con ese identificador de tarea y de devolverlo al controlador de finalización. Hay clases auxiliares que le servirán de ayuda. Para obtener más información sobre la administración de simultaneidad, consulte [Walkthrough: Implementing a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
-   Si su clase define el método *MethodName*`Async` sin el parámetro de estado y no admite varias invocaciones simultáneas, asegúrese de que cualquier intento de invocar *MethodName*`Async` antes de que la invocación previa a *MethodName*`Async` se haya completado genere <xref:System.InvalidOperationException>.  
  
-   Por lo general, no genere una excepción si se invoca varias veces al método *MethodName*`Async` sin el parámetro `userSuppliedState` de modo que haya varias operaciones pendientes. Puede generar una excepción si la clase no puede controlar esa situación de forma explícita, pero piense que los desarrolladores pueden gestionar varias devoluciones de llamadas indistinguibles.  
  
### Acceso a resultados  
  
-   Si se produjo un error durante la ejecución de la operación asincrónica, los resultados no pueden ser accesibles. Asegúrese de que el acceso a cualquier propiedad de <xref:System.ComponentModel.AsyncCompletedEventArgs> cuando <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> no es `null` genera la excepción a la que hace referencia <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A>. La clase <xref:System.ComponentModel.AsyncCompletedEventArgs> proporciona el método <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A> para este fin.  
  
-   Asegúrese de que cualquier intento de acceder al resultado genere una <xref:System.InvalidOperationException> en la que se declare que la operación se canceló. Use el método <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A?displayProperty=fullName> para realizar esta verificación.  
  
### Informe de progreso  
  
-   Si es posible, admita informes de progreso. Esto permite a los desarrolladores ofrecer una mejor experiencia a los usuarios de la aplicación cuando utilicen su clase.  
  
-   Si implementa un evento `ProgressChanged`\/*MethodName*`ProgressChanged`, asegúrese de que no se han generado esos eventos para una operación asincrónica concreta después de que se haya generado el evento *MethodName*`Completed` de esa operación.  
  
-   Si se rellena la clase <xref:System.ComponentModel.ProgressChangedEventArgs> estándar, asegúrese de que <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> siempre se pueda interpretar como un porcentaje. No es necesario que el porcentaje sea exacto, pero debe representarse uno. Si su métrica de informes de progreso debe ser distinta a un porcentaje, derive una clase a partir de la clase <xref:System.ComponentModel.ProgressChangedEventArgs> y deje <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> en 0. Evite usar una métrica de informes que no sea un porcentaje.  
  
-   Asegúrese de que el evento `ProgressChanged` se genera en el subproceso apropiado y en el momento adecuado del ciclo de vida de la aplicación. Para obtener más información, vea la sección Subprocesos y contextos.  
  
### Implementación de IsBusy  
  
-   No exponga una propiedad `IsBusy` si su clase admite varias invocaciones simultáneas. Por ejemplo, los proxy del servicio XML Web no exponen una propiedad `IsBusy` porque admiten varias invocaciones simultáneas de métodos asincrónicos.  
  
-   La propiedad `IsBusy` debe devolver `true` después de que se haya llamado al método *MethodName*`Async` y antes de que se haya generado el evento *MethodName*`Completed`. De lo contrario, debe devolver `false`. Los componentes <xref:System.ComponentModel.BackgroundWorker> y <xref:System.Net.WebClient> son ejemplos de clases que exponen una propiedad `IsBusy`.  
  
### Cancelación  
  
-   Si es posible, admita cancelación. Esto permite a los desarrolladores ofrecer una mejor experiencia a los usuarios de la aplicación cuando utilicen su clase.  
  
-   En caso de cancelación, establezca la marca <xref:System.ComponentModel.AsyncCompletedEventArgs.Cancelled%2A> en el objeto <xref:System.ComponentModel.AsyncCompletedEventArgs>.  
  
-   Asegúrese de que cualquier intento de acceder al resultado genere una <xref:System.InvalidOperationException> en la que se declare que la operación se canceló. Use el método <xref:System.ComponentModel.AsyncCompletedEventArgs.RaiseExceptionIfNecessary%2A?displayProperty=fullName> para realizar esta verificación.  
  
-   Asegúrese de que las llamadas a un método de cancelación siempre se devuelvan correctamente y nunca generen una excepción. Por lo general, los clientes no son informados de si una operación es realmente cancelable en un momento determinado, ni tampoco de si una cancelación emitida previamente se ha realizado de forma correcta. No obstante, la aplicación siempre recibirá notificación cuando la cancelación tenga éxito, ya que la aplicación participa en el estado de finalización.  
  
-   Genere el evento *MethodName*`Completed` cuando la operación se cancele.  
  
### Errores y excepciones  
  
-   Capture todas las excepciones que se produzcan en la operación asincrónica y establezca el valor de la propiedad <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=fullName> en esa excepción.  
  
### Subprocesos y contextos  
 Para que su clase funcione correctamente, es muy importante que los controladores de eventos del cliente se invoquen en el subproceso o contexto apropiados para el modelo de aplicación dado, incluidas aplicaciones de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] y Windows Forms. Para garantizar que su clase asincrónica se comporta correctamente en cualquier modelo de aplicación, se proporcionan dos importantes clases auxiliares: <xref:System.ComponentModel.AsyncOperation> y <xref:System.ComponentModel.AsyncOperationManager>.  
  
 <xref:System.ComponentModel.AsyncOperationManager> proporciona un método, <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A>, que devuelve una <xref:System.ComponentModel.AsyncOperation>. El método *MethodName*`Async` llama a <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> y su clase usa la clase <xref:System.ComponentModel.AsyncOperation> devuelta para realizar un seguimiento de la duración de la tarea asincrónica.  
  
 Para informar al cliente del progreso, los resultados incrementales y la finalización, llame a los métodos <xref:System.ComponentModel.AsyncOperation.Post%2A> y <xref:System.ComponentModel.AsyncOperation.OperationCompleted%2A> en <xref:System.ComponentModel.AsyncOperation>.<xref:System.ComponentModel.AsyncOperation> es responsable de calcular las referencias de llamadas a los controladores de eventos del cliente para el subproceso o contexto apropiado.  
  
> [!NOTE]
>  Puede sortear estas reglas si desea contravenir la directiva del modelo de aplicación, pero al mismo tiempo seguir beneficiándose de las otras ventajas de usar el modelo asincrónico basado en eventos. Por ejemplo, es posible que desee que una clase que opera en Windows Forms sea de subproceso libre. Puede crear una clase de subproceso libre si los desarrolladores entienden las restricciones implícitas. Las aplicaciones de consola no sincronizan la ejecución de llamadas <xref:System.ComponentModel.AsyncOperation.Post%2A>. Esto puede provocar que se generen eventos `ProgressChanged` fuera de lugar. Si desea serializar la ejecución de llamadas <xref:System.ComponentModel.AsyncOperation.Post%2A>, implemente e instale una clase <xref:System.Threading.SynchronizationContext?displayProperty=fullName>.  
  
 Para obtener más información sobre el uso de <xref:System.ComponentModel.AsyncOperation> y <xref:System.ComponentModel.AsyncOperationManager> para habilitar operaciones asincrónicas, consulte [Walkthrough: Implementing a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
## Instrucciones  
  
-   Lo ideal es que las invocaciones de métodos sean independiente entre sí. Debe evitarse el acoplamiento de invocaciones con recursos compartidos. Si los recursos se van a compartir entre invocaciones, es necesario proporcionar un mecanismo de sincronización adecuado en la implementación.  
  
-   No se recomienda usar diseños que exijan al cliente implementar sincronización. Por ejemplo, si tiene un método asincrónico que recibe un objeto estático global como parámetro y se producen varias invocaciones simultáneas de ese método, se podrían dañar los datos o producir interbloqueos.  
  
-   Si implementa un método con la sobrecarga de varias invocaciones \(`userState` en la signatura\), su clase necesitará administrar una colección de estados de usuario o identificadores de tarea, así como sus correspondientes operaciones pendientes. Esta colección debe protegerse con regiones `lock`, ya que las diversas invocaciones agregan y quitan objetos `userState` de la colección.  
  
-   Considere la opción de volver a usar clases `CompletedEventArgs` donde sea posible y apropiado. En este caso, la nomenclatura no es coherente con el nombre de método, ya que un delegado dado y el tipo <xref:System.EventArgs> no están asociados a un único método. Sin embargo, jamás se puede forzar a los desarrolladores a que conviertan el valor recuperado de una propiedad en la clase <xref:System.EventArgs>.  
  
-   Si va a crear una clase que deriva de <xref:System.ComponentModel.Component>, no implemente ni instale su propia clase <xref:System.Threading.SynchronizationContext>. Los modelos de aplicación, y no los componentes, controlan el <xref:System.Threading.SynchronizationContext> utilizado.  
  
-   Si usa multithreading de cualquier tipo, corre el riesgo de que se produzcan errores graves y complejos. Antes de implementar una solución que use multithreading, consulte [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md).  
  
## Vea también  
 <xref:System.ComponentModel.AsyncOperation>   
 <xref:System.ComponentModel.AsyncOperationManager>   
 <xref:System.ComponentModel.AsyncCompletedEventArgs>   
 <xref:System.ComponentModel.ProgressChangedEventArgs>   
 <xref:System.ComponentModel.BackgroundWorker>   
 [Implementing the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)   
 [Multithreaded Programming with the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)   
 [Deciding When to Implement the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)   
 [Best Practices for Implementing the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)   
 [How to: Use Components That Support the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)   
 [Walkthrough: Implementing a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)