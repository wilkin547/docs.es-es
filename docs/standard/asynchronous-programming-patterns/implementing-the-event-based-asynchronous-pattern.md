---
title: Implementar el modelo asincrónico basado en eventos
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
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
ms.openlocfilehash: 484050b45b5da72386e9ac29805d7faf0ca9cbd6
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289387"
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a>Implementar el modelo asincrónico basado en eventos

Si está escribiendo una clase con algunas operaciones que pueden dar lugar a retrasos evidentes, considere la posibilidad de darle funcionalidad asincrónica implementando [Información general sobre el modelo asincrónico basado en eventos](event-based-asynchronous-pattern-overview.md).

El modelo asincrónico basado en eventos proporciona una forma estandarizada de empaquetar una clase que tenga características asincrónicas. Si se implementa con clases auxiliares como <xref:System.ComponentModel.AsyncOperationManager>, la clase funciona correctamente en cualquier modelo de aplicación, incluidas aplicaciones de ASP.NET, de consola y de Windows Forms.

Para obtener un ejemplo que implemente el modelo asincrónico basado en eventos, consulte [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](component-that-supports-the-event-based-asynchronous-pattern.md) (Cómo: Implementar un componente que admita el modelo asincrónico basado en eventos).

Para las operaciones asincrónicas sencillas, puede encontrar el componente <xref:System.ComponentModel.BackgroundWorker> adecuado. Para más información sobre <xref:System.ComponentModel.BackgroundWorker>, vea [Cómo: Ejecutar una operación en segundo plano](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md).

En la siguiente lista se describen las características del modelo asincrónico basado en eventos tratadas en este tema.

- Oportunidades para implementar el modelo asincrónico basado en eventos

- Métodos asincrónicos de nomenclatura

- Opcionalmente, admiten la cancelación

- Opcionalmente, admiten la propiedad IsBusy

- Opcionalmente, proporcionan compatibilidad para el informe de progreso

- Opcionalmente, proporcionan compatibilidad para devolver resultados incrementales

- Control de los parámetros Out y Ref en los métodos

## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a>Oportunidades para implementar el modelo asincrónico basado en eventos

Considere la posibilidad de implementar el modelo asincrónico basado en eventos en estos casos:

- Los clientes de la clase no necesitan que los objetos <xref:System.Threading.WaitHandle> y <xref:System.IAsyncResult> estén disponibles para operaciones asincrónicas, lo que significa que el sondeo y <xref:System.Threading.WaitHandle.WaitAll%2A> o <xref:System.Threading.WaitHandle.WaitAny%2A> deberá crearlos el cliente.

- Desea que el cliente administre las operaciones asincrónicas con el modelo delegado o de evento familiar.

Cualquier operación es candidata para una implementación asincrónica, pero deben tenerse en cuenta aquellas que espera que incurran en latencias de larga duración. Son especialmente adecuadas las operaciones en las cuales los clientes llaman a un método y reciben una notificación de su conclusión, sin necesidad de ninguna otra intervención. También son adecuadas aquellas que se ejecutan continuamente, notificando a los clientes de forma periódica del progreso, los resultados incrementales o los cambios de estado.

Para más información sobre cómo decidir cuándo admitir el modelo asincrónico basado en eventos, consulte [Decisión de cuándo implementar el modelo asincrónico basado en eventos](deciding-when-to-implement-the-event-based-asynchronous-pattern.md).

## <a name="naming-asynchronous-methods"></a>Métodos asincrónicos de nomenclatura

Para cada método sincrónico *MethodName* para el cual desee proporcionar un homólogo asincrónico:

Defina un método _MethodName_**Async** que:

- Devuelve `void`.

- Tome los mismos parámetros que el método *MethodName*.

- Acepte varias invocaciones.

Opcionalmente, defina una sobrecarga _MethodName_**Async**, idéntica a _MethodName_**Async**, pero con un parámetro con valor de objeto adicional denominado `userState`. Haga esto si está preparado para administrar varias invocaciones simultáneas de su método, en cuyo caso, el valor `userState` se entregará de nuevo a todos los controladores de eventos para diferenciar las invocaciones del método. También puede decidir hacerlo sencillamente como un lugar donde almacenar el estado del usuario para su posterior recuperación.

Para cada signatura del método _MethodName_**Async** independiente:

1. Defina el siguiente evento en la misma clase que el método:

    ```vb
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler
    ```

    ```csharp
    public event MethodNameCompletedEventHandler MethodNameCompleted;
    ```

2. Defina el delegado siguiente y <xref:System.ComponentModel.AsyncCompletedEventArgs>. Es probable que estos se definan fuera de la propia clase, pero en el mismo espacio de nombres.

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

    - Asegúrese de que la clase _MethodName_**CompletedEventArgs** expone sus miembros como propiedades de solo lectura y no como campos, ya que estos impiden el enlace de datos.

    - No defina ninguna clase derivada de <xref:System.ComponentModel.AsyncCompletedEventArgs> para métodos que no producen resultados. Simplemente se usa una instancia de <xref:System.ComponentModel.AsyncCompletedEventArgs>.

      > [!NOTE]
      > Es perfectamente aceptable, cuando sea posible y apropiado, para reutilizar el delegado y los tipos <xref:System.ComponentModel.AsyncCompletedEventArgs>. En este caso, la nomenclatura no será tan coherente con el nombre del método, ya que ni un delegado especificado ni <xref:System.ComponentModel.AsyncCompletedEventArgs> se vincularán a un solo método.

## <a name="optionally-support-cancellation"></a>Opcionalmente, admiten la cancelación

Si su clase admite la cancelación de operaciones asincrónicas, la cancelación debe exponerse al cliente como se describe a continuación. Tenga en cuenta que hay dos puntos de decisión que deben alcanzarse antes de definir la compatibilidad de cancelación:

- ¿Tiene su clase, incluidas las futuras adiciones a la misma previstas, solo una operación asincrónica que admita la cancelación?

- ¿Pueden las operaciones asincrónicas que admiten la cancelación admitir varias operaciones pendientes? Es decir, ¿toma el método _MethodName_**Async** un parámetro `userState` y permite varias invocaciones antes de esperar a que finalice alguna?

Use las respuestas a estas dos preguntas en la siguiente tabla para determinar cuál debe ser la signatura para el método de cancelación.

### <a name="visual-basic"></a>Visual Basic

||Varias operaciones simultáneas compatibles|Solo una operación cada vez|
|------|------------------------------------------------|----------------------------------|
|Una operación asincrónica en toda la clase|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|
|Varias operaciones asincrónicas en la clase|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|

### <a name="c"></a>C\#

||Varias operaciones simultáneas compatibles|Solo una operación cada vez|
|------|------------------------------------------------|----------------------------------|
|Una operación asincrónica en toda la clase|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|
|Varias operaciones asincrónicas en la clase|`void CancelAsync(object userState);`|`void CancelAsync();`|

Si define el método `CancelAsync(object userState)`, los clientes deben ser cuidadosos al elegir su valor de estado para poder diferenciar entre todos los métodos asincrónicos invocados en el objeto y no solo entre todas las invocaciones de un solo método asincrónico.

La decisión de asignar un nombre a la versión de operación asincrónica única _MethodName_**AsyncCancel** se basa en la capacidad de detectar más fácilmente el método en un entorno de diseño como IntelliSense de Visual Studio. Esto agrupa a los miembros relacionados y los diferencia de otros miembros que no tienen nada que ver con la funcionalidad asincrónica. Si espera que pueda haber agregadas operaciones asincrónicas adicionales en versiones posteriores, es mejor definir `CancelAsync`.

No defina varios métodos de la tabla anterior en la misma clase. No tendrá sentido o desordenará la interfaz de clase con una proliferación de métodos.

Normalmente, estos métodos volverán de inmediato y la operación puede cancelarse, o bien puede no hacerlo en realidad. En el controlador de eventos para el evento _MethodName_**Completed**, el objeto _MethodName_**CompletedEventArgs** contiene un campo `Cancelled` que los clientes pueden usar para determinar si se ha producido la cancelación.

Cumpla la semántica de cancelación descrita en [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).

## <a name="optionally-support-the-isbusy-property"></a>Opcionalmente, admiten la propiedad IsBusy

Si la clase no admite varias invocaciones simultáneas, considere la posibilidad de exponer una propiedad `IsBusy`. Esto permite a los desarrolladores determinar si un método _MethodName_**Async** se ejecuta sin detectar una excepción desde el método _MethodName_**Async**.

Cumpla la semántica de `IsBusy` descrita en [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).

## <a name="optionally-provide-support-for-progress-reporting"></a>Opcionalmente, proporcionan compatibilidad para el informe de progreso

Suele ser recomendable que una operación asincrónica informe sobre el progreso durante su funcionamiento. Para ello, el modelo asincrónico basado en eventos proporciona una directriz.

- Opcionalmente, defina un evento que la operación asincrónica va a generar y que se va a invocar en el subproceso adecuado. El objeto <xref:System.ComponentModel.ProgressChangedEventArgs> lleva un indicador de progreso con valor entero que se espera que se sitúe entre 0 y 100.

- Asigne un nombre a este evento como se muestra a continuación:

  - `ProgressChanged` si la clase tiene varias operaciones asincrónicas (o se espera que crezca para incluir varias operaciones asincrónicas en futuras versiones);

  - _MethodName_**ProgressChanged** si la clase tiene una sola operación asincrónica.

  Esta opción de nomenclatura va paralela a aquella creada para el método de cancelación, como se describe en la sección Opcionalmente, admiten la cancelación.

Este evento debería utilizar la firma de delegado <xref:System.ComponentModel.ProgressChangedEventHandler> y la clase <xref:System.ComponentModel.ProgressChangedEventArgs>. De forma alternativa, si puede proporcionarse un indicador de progreso más específico de dominio (por ejemplo, bytes leídos y total de bytes para una operación de descarga), debe definir una clase derivada de <xref:System.ComponentModel.ProgressChangedEventArgs>.

Tenga en cuenta que solo hay un evento `ProgressChanged` o _MethodName_**ProgressChanged** para la clase, independientemente del número de métodos asincrónicos que admite. Se espera que los clientes usen el objeto `userState` que se pasa a los métodos _MethodName_**Async** para diferenciar entre las actualizaciones de progreso en varias operaciones simultáneas.

Puede haber situaciones en las que varias operaciones admitan el progreso y cada una devuelva un indicador para el progreso diferente. En este caso, un solo evento `ProgressChanged` no es adecuado, pudiendo considerar la posibilidad de admitir varios eventos `ProgressChanged`. En este caso, use un patrón de nombres de _MethodName_**ProgressChanged** para cada método _MethodName_**Async**.

Cumpla la semántica de notificación sobre el progreso descrita en [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).

## <a name="optionally-provide-support-for-returning-incremental-results"></a>Opcionalmente, proporcionan compatibilidad para devolver resultados incrementales

A veces, una operación asincrónica puede devolver resultados incrementales antes de finalizar. Hay una serie de opciones que se pueden usar para admitir este escenario. A continuación, se presentan algunos ejemplos.

### <a name="single-operation-class"></a>Clase de operación única

Si la clase solo admite una sola operación asincrónica y dicha operación puede devolver resultados incrementales, haga lo siguiente:

- Amplíe el tipo <xref:System.ComponentModel.ProgressChangedEventArgs> para llevar los datos del resultado incremental y defina un evento _MethodName_**ProgressChanged** con estos datos extendidos.

- Genere este evento _MethodName_**ProgressChanged** cuando haya un resultado incremental que notificar.

Esta solución se aplica de forma específica a una clase de operación asincrónica única porque no hay ningún problema con que el mismo evento se produzca para devolver resultados incrementales en "todas las operaciones", como hace el evento _MethodName_**ProgressChanged**.

### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a>Clase de varias operaciones con resultados incrementales homogéneos

En este caso, la clase admite varios métodos asincrónicos, cada uno capaz de devolver resultados incrementales. Además, todos estos resultados incrementales tienen el mismo tipo de datos.

Siga el modelo descrito anteriormente para las clases de operación única, ya que la misma estructura <xref:System.EventArgs> funcionará para todos los resultados incrementales. Defina un evento `ProgressChanged` en lugar de un evento _MethodName_**ProgressChanged**, ya que se aplica a varios métodos asincrónicos.

### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a>Clase de varias operaciones con resultados incrementales heterogéneos

Si la clase admite varios métodos asincrónicos, devolviendo cada uno un tipo de datos diferente, debe hacer lo siguiente:

- Separe el informe de resultados del informe de progreso.

- Defina un evento _MethodName_**ProgressChanged** independiente con el elemento <xref:System.EventArgs> adecuado para cada método asincrónico con el fin de controlar los datos del resultado incremental de ese método.

Invoque ese controlador de eventos en el subproceso adecuado como se describe en [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).

## <a name="handling-out-and-ref-parameters-in-methods"></a>Control de los parámetros Out y Ref en los métodos

Aunque, en general, no se aconseja el uso de `out` y `ref` en .NET Framework, estas son las reglas que se deben seguir cuando estén presentes:

Dado un método sincrónico *MethodName*:

- Los parámetros `out` de *MethodName* no deben formar parte de _MethodName_**Async**. En su lugar, deben formar parte de _MethodName_**CompletedEventArgs** con el mismo nombre que su parámetro equivalente en *MethodName* (a menos que haya un nombre más adecuado).

- Los parámetros `ref` de *MethodName* deben aparecer como parte de _MethodName_**Async** y como parte de _MethodName_**CompletedEventArgs** con el mismo nombre que su parámetro equivalente en *MethodName* (a menos que haya un nombre más adecuado).

Por ejemplo, dado:

```vb
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer
```

```csharp
public int MethodName(string arg1, ref string arg2, out string arg3);
```

El método asincrónico y su clase <xref:System.ComponentModel.AsyncCompletedEventArgs> tendrían un aspecto similar a este:

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

- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- [Implementar un componente que admita el modelo asincrónico basado en eventos](component-that-supports-the-event-based-asynchronous-pattern.md)
- [Ejecutar una operación en segundo plano](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [Cómo: Implementar un formulario que utiliza una operación en segundo plano](../../framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [Decisión de cuándo implementar el modelo asincrónico basado en eventos](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
- [Procedimientos recomendados para implementar el modelo asincrónico basado en eventos](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [Modelo asincrónico basado en eventos (EAP)](event-based-asynchronous-pattern-eap.md)
