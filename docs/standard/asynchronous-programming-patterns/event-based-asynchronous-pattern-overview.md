---
title: Información general sobre el modelo asincrónico basado en eventos
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 792aa8da-918b-458e-b154-9836b97735f3
ms.openlocfilehash: cce01a7c87f6f20b5e6c46881b8c863bb5a72a88
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160074"
---
# <a name="event-based-asynchronous-pattern-overview"></a>Información general sobre el modelo asincrónico basado en eventos
Las aplicaciones que desempeñan muchas tareas simultáneamente, aunque siguen respondiendo a la interacción del usuario, a menudo exigen un diseño que utiliza varios subprocesos. El espacio de nombres <xref:System.Threading> proporciona todas las herramientas necesarias para crear aplicaciones multiproceso de gran rendimiento, pero, para usar estas herramientas de forma eficaz, es necesario atesorar una gran experiencia en ingeniería de software multiproceso. Para aplicaciones multiproceso relativamente simples, el componente <xref:System.ComponentModel.BackgroundWorker> ofrece una solución sencilla. Para aplicaciones asincrónicas más sofisticadas, considere la opción de implementar una clase que se adhiera al modelo asincrónico basado en eventos.  
  
 El modelo asincrónico basado en eventos pone a su disposición las ventajas de las aplicaciones multiproceso al tiempo que oculta muchos de los problemas complejos inherentes al diseño multiproceso. El uso de una clase compatible con este modelo permite:  
  
- Realizar «en segundo plano» tareas que exigen mucho tiempo, como las descargas y las operaciones de base de datos, sin interrumpir la aplicación.  
  
- Ejecutar varias operaciones simultáneamente y recibir una notificación cuando finalice cada una de ellas.  
  
- Esperar a que los recursos estén disponibles sin detener la aplicación, es decir, sin que se quede "bloqueada".  
  
- Comunicarse con operaciones asincrónicas pendientes mediante el modelo conocido de eventos y delegados. Para obtener más información sobre el uso de controladores de eventos y delegados, vea [Eventos](../../../docs/standard/events/index.md).  
  
 Una clase que admita el modelo asincrónico basado en eventos tendrá uno o varios métodos denominados _NombreDeMétodo_**Async**. Estos métodos pueden reflejar versiones sincrónicas, que desempeñan la misma operación en el subproceso actual. La clase también puede tener un evento _NombreDeMétodo_**Completed** y un método _NombreDeMétodo_**AsyncCancel** (o simplemente **CancelAsync**).  
  
 <xref:System.Windows.Forms.PictureBox> es un componente que admite el modelo asincrónico basado en eventos. Se puede descargar una imagen sincrónicamente mediante una llamada a su método <xref:System.Windows.Forms.PictureBox.Load%2A>, pero si la imagen es grande o si la conexión de red es lenta, la aplicación dejará de responder hasta que la operación finalice y la llamada a <xref:System.Windows.Forms.PictureBox.Load%2A> responda.  
  
 Si quiere que la aplicación siga ejecutándose mientras se carga la imagen, puede llamar al método <xref:System.Windows.Forms.PictureBox.LoadAsync%2A> y controlar el evento <xref:System.Windows.Forms.PictureBox.LoadCompleted>, al igual que haría con cualquier otro evento. Cuando llame al método <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>, la aplicación seguirá ejecutándose mientras se realiza la descarga en un subproceso aparte («en segundo plano»). Cuando la operación de carga de la imagen finalice, se llamará al controlador de eventos; este puede examinar el parámetro <xref:System.ComponentModel.AsyncCompletedEventArgs> para determinar si la descarga se completó correctamente.  
  
 El modelo asincrónico basado en eventos requiere que se pueda cancelar una operación asincrónica y que el control <xref:System.Windows.Forms.PictureBox> admita este requisito con su método <xref:System.Windows.Forms.PictureBox.CancelAsync%2A>. La llamada a <xref:System.Windows.Forms.PictureBox.CancelAsync%2A> envía una solicitud para detener la carga pendiente y, cuando se cancela la operación, se genera el evento <xref:System.Windows.Forms.PictureBox.LoadCompleted>.  
  
> [!CAUTION]
> Es posible que la descarga finalice justo en el momento de realizar la solicitud <xref:System.Windows.Forms.PictureBox.CancelAsync%2A> y, por tanto, puede que <xref:System.ComponentModel.AsyncCompletedEventArgs.Cancelled%2A> no refleje la solicitud de cancelación. Esto se denomina *condición de carrera* y es un problema habitual en la programación multiproceso. Para obtener más información sobre problemas en la programación multiproceso, vea [Procedimientos recomendados para el subprocesamiento administrado](../../../docs/standard/threading/managed-threading-best-practices.md).  
  
## <a name="characteristics-of-the-event-based-asynchronous-pattern"></a>Características del modelo asincrónico basado en eventos  
 El modelo asincrónico basado en eventos puede tener varias formas, en función de la complejidad de las operaciones admitidas por una clase en particular. Las clases más simples pueden tener un único método _NombreDeMétodo_**Async** y su correspondiente evento _NombreDeMétodo_**Completed**. Las clases más complejas pueden tener varios métodos _NombreDeMétodo_**Async**, cada uno con su correspondiente evento _NombreDeMétodo_**Completed**, así como versiones sincrónicas de estos métodos. Opcionalmente, las clases pueden admitir cancelación, informes de progreso y resultados incrementales para los métodos asincrónicos.  
  
 Un método asincrónico también puede admitir varias llamadas pendientes (varias invocaciones simultáneas), lo que permite que su código pueda llamarlo todas las veces que quiera sin que se hayan completado las otras operaciones pendientes. La gestión correcta de esta situación puede exigir a la aplicación realizar un seguimiento de la finalización de cada operación.  
  
### <a name="examples-of-the-event-based-asynchronous-pattern"></a>Ejemplos del modelo asincrónico basado en eventos  
 Los componentes <xref:System.Media.SoundPlayer> and <xref:System.Windows.Forms.PictureBox> representan implementaciones simples del modelo asincrónico basado en eventos. Los componentes <xref:System.Net.WebClient> and <xref:System.ComponentModel.BackgroundWorker> representan implementaciones más complejas del modelo asincrónico basado en eventos.  
  
 El siguiente es un ejemplo de declaración de clase que se ajusta al modelo:  
  
```vb  
Public Class AsyncExample  
    ' Synchronous methods.  
    Public Function Method1(ByVal param As String) As Integer
    Public Sub Method2(ByVal param As Double)
  
    ' Asynchronous methods.  
    Overloads Public Sub Method1Async(ByVal param As String)
    Overloads Public Sub Method1Async(ByVal param As String, ByVal userState As Object)
    Public Event Method1Completed As Method1CompletedEventHandler  
  
    Overloads Public Sub Method2Async(ByVal param As Double)
    Overloads Public Sub Method2Async(ByVal param As Double, ByVal userState As Object)
    Public Event Method2Completed As Method2CompletedEventHandler  
  
    Public Sub CancelAsync(ByVal userState As Object)
  
    Public ReadOnly Property IsBusy () As Boolean  
  
    ' Class implementation not shown.  
End Class  
```  
  
```csharp  
public class AsyncExample  
{  
    // Synchronous methods.  
    public int Method1(string param);  
    public void Method2(double param);  
  
    // Asynchronous methods.  
    public void Method1Async(string param);  
    public void Method1Async(string param, object userState);  
    public event Method1CompletedEventHandler Method1Completed;  
  
    public void Method2Async(double param);  
    public void Method2Async(double param, object userState);  
    public event Method2CompletedEventHandler Method2Completed;  
  
    public void CancelAsync(object userState);  
  
    public bool IsBusy { get; }  
  
    // Class implementation not shown.  
}  
```  
  
 La clase `AsyncExample` ficticia tiene dos métodos, los cuales admiten invocaciones de tipo sincrónico y asincrónico. Las sobrecargas sincrónicas se comportan como cualquier llamada al método y ejecutan la operación en el subproceso que realiza la llamada; si la operación lleva mucho tiempo, puede producirse un retraso notable antes de que la llamada responda. Las sobrecargas asincrónicas empezarán la operación en otro subproceso y luego volverán de inmediato, lo que permite continuar el subproceso de llamada mientras la operación se ejecuta «en segundo plano».  
  
### <a name="asynchronous-method-overloads"></a>Sobrecargas de método asincrónico  
 Hay dos posibles sobrecargas para las operaciones asincrónicas: invocación única e invocación múltiple. Las dos formas se distinguen por sus signaturas de método: la forma de invocación múltiple tiene un parámetro adicional llamado `userState`. Esta forma permite al código llamar varias veces a `Method1Async(string param, object userState)` sin tener que esperar a que finalicen otras operaciones asincrónicas pendientes. Por otra parte, si se intenta llamar a `Method1Async(string param)` antes de que haya finalizado una invocación anterior, el método genera una <xref:System.InvalidOperationException>.  
  
 El parámetro `userState` para sobrecargas de invocación múltiple permite distinguir entre operaciones asincrónicas. Usted proporciona un valor único (por ejemplo, un GUID o código hash) para cada llamada a `Method1Async(string param, object userState)`, y cuando la operación finalice, el controlador de eventos podrá determinar qué instancia de la operación fue la que generó el evento de finalización.  
  
### <a name="tracking-pending-operations"></a>Seguimiento de operaciones pendientes  
 Si usa sobrecargas de invocación múltiple, el código necesitará realizar un seguimiento de los objetos `userState` (id. de tareas) de las tareas pendientes. En cada llamada a `Method1Async(string param, object userState)`, normalmente hay que generar un objeto `userState` nuevo y único y agregarlo a una colección. Cuando la tarea correspondiente a este objeto `userState` genera el evento de finalización, su implementación del método de finalización examinará <xref:System.ComponentModel.AsyncCompletedEventArgs.UserState%2A?displayProperty=nameWithType> y lo quitará de su colección. Usado de este modo, el parámetro `userState` adopta el rol de id. de tarea.  
  
> [!NOTE]
> Asegúrese de proporcionar un valor único para `userState` en las llamadas a sobrecargas de invocación múltiple. Los id. de tarea que no sean únicos provocarán que la clase asincrónica genere una <xref:System.ArgumentException>.  
  
### <a name="canceling-pending-operations"></a>Cancelación de operaciones pendientes  
 Es importante ser capaz cancelar operaciones asincrónicas en cualquier momento antes de la finalización. Las clases que implementan el modelo asincrónico basado en eventos tendrán un método `CancelAsync` (si solo hay un método asincrónico) o un método _NombreDeMétodo_**AsyncCancel** (si hay varios métodos asincrónicos).  
  
 Los métodos que permiten varias invocaciones toman un parámetro `userState` que puede usarse para seguir la duración de cada tarea. `CancelAsync` toma un parámetro `userState` que permite cancelar tareas pendientes concretas.  
  
 Los métodos que solo admiten una única operación pendiente a la vez, como `Method1Async(string param)`, no son cancelables.  
  
### <a name="receiving-progress-updates-and-incremental-results"></a>Recibir actualizaciones de progreso y resultados incrementales  
 Una clase que se adhiera al modelo asincrónico basado en eventos puede, como opción, proporcionar un evento para seguir el progreso y los resultados incrementales. Por lo general, se denominará `ProgressChanged` o _NombreDeMétodo_**ProgressChanged**, y su controlador de eventos correspondiente tomará un parámetro <xref:System.ComponentModel.ProgressChangedEventArgs>.  
  
 El controlador de eventos del evento `ProgressChanged` puede examinar la propiedad <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A?displayProperty=nameWithType> para determinar el progreso de una tarea asincrónica expresado mediante porcentaje. Esta propiedad estará comprendida entre 0 y 100 y se puede usar para actualizar la propiedad <xref:System.Windows.Forms.ProgressBar.Value%2A> de un <xref:System.Windows.Forms.ProgressBar>. Si hay varias operaciones asincrónicas pendientes, puede usar la propiedad <xref:System.ComponentModel.ProgressChangedEventArgs.UserState%2A?displayProperty=nameWithType> para distinguir cuál de ellas está informando del progreso.  
  
 Algunas clases pueden informar de resultados incrementales durante el desarrollo de operaciones asincrónicas. Estos resultados se almacenarán en una clase que deriva de <xref:System.ComponentModel.ProgressChangedEventArgs> y aparecerán como propiedades en la clase derivada. El acceso a estos resultados en el controlador de eventos del evento `ProgressChanged` se realiza del mismo modo que el acceso a la propiedad <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A>. Si hay varias operaciones asincrónicas pendientes, puede usar la propiedad <xref:System.ComponentModel.ProgressChangedEventArgs.UserState%2A> para distinguir cuál de ellas está informando de resultados incrementales.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- [Cómo: Uso de componentes que admitan el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)
- [Cómo: Ejecutar una operación en segundo plano](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [Cómo: Implementar un formulario que usa una operación en segundo plano](../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [Decisión de cuándo implementar el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
