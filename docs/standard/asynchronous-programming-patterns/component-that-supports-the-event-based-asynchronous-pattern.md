---
title: 'Cómo: Implementar un componente que admita el modelo asincrónico basado en eventos'
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
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 61f676b5-936f-40f6-83ce-f22805ec9c2f
ms.openlocfilehash: 44a1019ac8169138aa95b03e2027d9539cbf8391
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71957372"
---
# <a name="how-to-implement-a-component-that-supports-the-event-based-asynchronous-pattern"></a>Cómo: Implementar un componente que admita el modelo asincrónico basado en eventos
Si está escribiendo una clase con algunas operaciones que pueden dar lugar a retrasos evidentes, considere la posibilidad de darle funcionalidad asincrónica implementando [Información general sobre el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
 En este tutorial se explica cómo crear un componente que implementa el modelo asincrónico basado en eventos. Se implementa mediante clases auxiliares del espacio de nombres <xref:System.ComponentModel?displayProperty=nameWithType>, lo que garantiza que el componente funcione correctamente en cualquier modelo de aplicación, incluidas aplicaciones de ASP.NET, de consola y de Windows Forms. Este componente también se puede diseñar con un control <xref:System.Windows.Forms.PropertyGrid> y sus propios diseñadores personalizados.  
  
 Cuando haya terminado, tendrá una aplicación que calcula de forma asincrónica los números de primos. La aplicación tendrá un subproceso de interfaz de usuario principal y un subproceso para cada cálculo de números primos. Aunque comproar si un número elevado es primo puede llevar un tiempo considerable, el subproceso de interfaz de usuario principal no se interrumpirá por este retraso, y el formulario seguirá respondiendo durante el cálculo. Podrá ejecutar tantos cálculos como cálculos simultáneos de cancelación desee de forma simultánea y selectiva.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
- Crear el componente  
  
- Definir delegados y eventos asincrónicos públicos  
  
- Definir delegados privados  
  
- Implementar eventos públicos  
  
- Implementar el método de finalización  
  
- Implementar los métodos de trabajo  
  
- Implementar métodos de inicio y cancelación  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: Implementar un cliente en un modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## <a name="creating-the-component"></a>Crear el componente  
 El primer paso es crear el componente que implementará el modelo asincrónico basado en eventos.  
  
### <a name="to-create-the-component"></a>Para crear el componente  
  
- Cree una clase llamada `PrimeNumberCalculator` y heredada de <xref:System.ComponentModel.Component>.  
  
## <a name="defining-public-asynchronous-events-and-delegates"></a>Definir delegados y eventos asincrónicos públicos  
 El componente se comunica con los clientes mediante eventos. El evento _MethodName_**Completed** informa a los clientes de la finalización de una tarea asincrónica, y el evento _MethodName_**ProgressChanged** informa a los clientes del progreso de una tarea asincrónica.  
  
### <a name="to-define-asynchronous-events-for-clients-of-your-component"></a>Para definir eventos asincrónicos para los clientes de su componente:  
  
1. Importe los espacios de nombres <xref:System.Threading?displayProperty=nameWithType> y <xref:System.Collections.Specialized?displayProperty=nameWithType> en la parte superior del archivo.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2. Antes de la definición de clase `PrimeNumberCalculator`, declare delegados de progreso y eventos de finalización.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3. Antes de la definición de clase `PrimeNumberCalculator`, declare eventos de progreso de los informes y de finalización para los clientes.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4. Después de la definición de clase `PrimeNumberCalculator`, derive la clase `CalculatePrimeCompletedEventArgs` para generar informes del resultado de cada cálculo en el controlador de eventos del cliente para el evento `CalculatePrimeCompleted`. Además de las propiedades `AsyncCompletedEventArgs`, esta clase permite al cliente determinar qué número se probó, si es primo y cuál es el primer divisor en caso de que no sea primo.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## <a name="checkpoint"></a>Punto de control  
 En este momento, puede compilar el componente.  
  
### <a name="to-test-your-component"></a>Para probar el componente  
  
- Compile el componente.  
  
     Recibirá dos advertencias del compilador:  
  
    ```console  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     Estas advertencias se borrarán en la sección siguiente.  
  
## <a name="defining-private-delegates"></a>Definir delegados privados  
 Los aspectos asincrónicos del componente `PrimeNumberCalculator` se implementan internamente con un delegado especial conocido como <xref:System.Threading.SendOrPostCallback>. <xref:System.Threading.SendOrPostCallback> representa un método de devolución de llamada que se ejecuta en un subproceso <xref:System.Threading.ThreadPool>. El método de devolución de llamada debe tener una firma que toma un único parámetro de tipo <xref:System.Object>, lo que significa que tendrá que pasar información de estado entre los delegados de una clase contenedora. Para obtener más información, consulta <xref:System.Threading.SendOrPostCallback>.  
  
### <a name="to-implement-your-components-internal-asynchronous-behavior"></a>Para implementar un comportamiento asincrónico interno del componente:  
  
1. Declare y cree los delegados <xref:System.Threading.SendOrPostCallback> en la clase `PrimeNumberCalculator`. Cree los objetos <xref:System.Threading.SendOrPostCallback> en un método de utilidad llamado `InitializeDelegates`.  
  
     Necesitará dos delegados: uno para notificar el progreso al cliente y otro para informar sobre la finalización al cliente.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2. Llame al método `InitializeDelegates` en el constructor del componente.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3. Declare un delegado en la clase `PrimeNumberCalculator` que controla el trabajo real para que se realice de forma asincrónica. Este delegado ajusta el método de trabajo que comprueba si un número es primo. El delegado toma un parámetro <xref:System.ComponentModel.AsyncOperation>, que se usará para realizar el seguimiento de la duración de la operación asincrónica.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4. Cree una colección para administrar la duración de las operaciones asincrónicas pendientes. El cliente necesita una forma de realizar el seguimiento de las operaciones a medida que se ejecutan y completan, y este seguimiento se realiza requiriendo al cliente que pase un token exclusivo o un identificador de tarea cuando el cliente realiza la llamada al método asincrónico. El componente `PrimeNumberCalculator` debe realizar un seguimiento de cada llamada mediante la asociación del identificador de tarea con su invocación correspondiente. Si el cliente pasa un identificador de tarea que no es único, el componente `PrimeNumberCalculator` debe generar una excepción.  
  
     El componente `PrimeNumberCalculator` realiza un seguimiento del identificador de tarea con una clase de colección especial llamada <xref:System.Collections.Specialized.HybridDictionary>. En la definición de clase, cree una clase <xref:System.Collections.Specialized.HybridDictionary> denominada `userTokenToLifetime`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## <a name="implementing-public-events"></a>Implementar eventos públicos  
 Los componentes que implementan el modelo asincrónico basado en eventos se comunican con los clientes mediante eventos. Estos eventos se invocan en el subproceso adecuado con la ayuda de la clase <xref:System.ComponentModel.AsyncOperation>.  
  
### <a name="to-raise-events-to-your-components-clients"></a>Para generar eventos en los clientes del componente:  
  
1. Implemente eventos públicos para informar a los clientes. Necesitará un evento para los informes de progreso y otro para informar de la finalización.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## <a name="implementing-the-completion-method"></a>Implementar el método de finalización  
 El delegado de finalización es el método que el comportamiento asincrónico de subproceso libre y subyacente invocará cuando la operación asincrónica finaliza tras una terminación correcta, un error o una cancelación. Esta invocación se produce en un subproceso arbitrario.  
  
 Este método es donde se quita el identificador de tarea del cliente de la colección interna de tokens de clientes exclusivos. Este método también finaliza la duración de una operación asincrónica determinada llamando al método <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> en la clase <xref:System.ComponentModel.AsyncOperation> correspondiente. Esta llamada genera el evento de finalización en el subproceso que es apropiado para el modelo de aplicación. Después de llamar al método <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>, ya no se puede usar la instancia de <xref:System.ComponentModel.AsyncOperation>, y todos los intentos posteriores para usarla generarán una excepción.  
  
 La firma `CompletionMethod` debe contener todos los estados necesarios para describir el resultado de la operación asincrónica. Contiene información de estado del número que probó esta operación asincrónica particular, si el número es primo y el valor de su primer divisor en caso de que no se trate de un número primo. También contiene información de estado que describe cualquier excepción generada y la clase <xref:System.ComponentModel.AsyncOperation> correspondiente a esta tarea concreta.  
  
### <a name="to-complete-an-asynchronous-operation"></a>Para completar una operación asincrónica:  
  
- Implemente el método de finalización. Adopta seis parámetros, que se usan para rellenar un objeto `CalculatePrimeCompletedEventArgs` devuelto al cliente mediante el objeto `CalculatePrimeCompletedEventHandler` del cliente. Quita el token del identificador de tarea del cliente de la colección interna y finaliza la duración de la operación asincrónica con una llamada a <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>. <xref:System.ComponentModel.AsyncOperation> serializa la llamada al subproceso o contexto que son apropiados para el modelo de aplicación.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## <a name="checkpoint"></a>Punto de control  
 En este momento, puede compilar el componente.  
  
### <a name="to-test-your-component"></a>Para probar el componente  
  
- Compile el componente.  
  
     Recibirá una advertencia del compilador:  
  
    ```console  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     Esta advertencia se resolverá en la sección siguiente.  
  
## <a name="implementing-the-worker-methods"></a>Implementar los métodos de trabajo  
 Hasta ahora, ha implementado el código asincrónico admitido para el componente `PrimeNumberCalculator`. Ahora puede implementar el código que realiza el trabajo real. Implementará tres métodos: `CalculateWorker`, `BuildPrimeNumberList` y `IsPrime`. Juntos, `BuildPrimeNumberList` y `IsPrime` constituyen un algoritmo muy conocido denominado criba de Eratóstenes, que determina si un número es primo buscando todos los números primos hasta la raíz cuadrada del número de prueba. Si no se encuentran divisores en este punto, el número de prueba es primo.  
  
 Si este componente se hubiera escrito para obtener la máxima eficacia, recordaría todos los números primos detectados por distintas invocaciones para diferentes números de prueba. También buscaría divisores triviales como 2, 3 y 5. Con este ejemplo se pretende demostrar cómo las operaciones que consumen mucho tiempo pueden ejecutarse de forma asincrónica; sin embargo, estas optimizaciones se dejan como un ejercicio para el usuario.  
  
 El método `CalculateWorker` se ajusta en un delegado y se invoca de forma asincrónica con una llamada a `BeginInvoke`.  
  
> [!NOTE]
> Los informes de progreso se implementan en el método `BuildPrimeNumberList`. En equipos rápidos, los eventos `ProgressChanged` se pueden producir en una sucesión rápida. El subproceso de cliente, en el que se producen estos eventos, debe ser capaz de controlar esta situación. El código de la interfaz de usuario puede estar congestionado con mensajes y no ser capaz de afrontar esta situación, de tal manera que se puede producir una falta de respuesta. Para consultar una interfaz de usuario de ejemplo que controla esta situación, vea [Implementar un cliente en un modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
### <a name="to-execute-the-prime-number-calculation-asynchronously"></a>Para ejecutar de forma asincrónica el cálculo de números primos:  
  
1. Implemente el método de utilidad `TaskCanceled`. Esto comprueba la colección de la duración de la tarea de un identificador de tarea concreto y devuelve `true` si no se encuentra el identificador de tarea.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2. Implemente el método `CalculateWorker`. Adopta dos parámetros: un número para probar y <xref:System.ComponentModel.AsyncOperation>.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3. Implemente `BuildPrimeNumberList`. Adopta dos parámetros: el número para probar y <xref:System.ComponentModel.AsyncOperation>. Utiliza <xref:System.ComponentModel.AsyncOperation> para informar del progreso y de los resultados incrementales. Esto garantiza que se llama a los controladores de eventos del cliente en el subproceso o contexto apropiados para el modelo de aplicación. Cuando `BuildPrimeNumberList` encuentra un número primo, informa de este como un resultado incremental al controlador de eventos del cliente para el evento `ProgressChanged`. Esto requiere una clase derivada de <xref:System.ComponentModel.ProgressChangedEventArgs>, llamada `CalculatePrimeProgressChangedEventArgs`, que tiene una propiedad agregada denominada `LatestPrimeNumber`.  
  
     El método `BuildPrimeNumberList` también llama periódicamente al método `TaskCanceled` y se cierra si el método devuelve `true`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4. Implemente `IsPrime`. Adopta tres parámetros: una lista de números primos conocidos, el número que se va a probar y un parámetro de salida para el primer divisor encontrado. Dada la lista de números primos, determina si el número de prueba es primo.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5. Deriva `CalculatePrimeProgressChangedEventArgs` de <xref:System.ComponentModel.ProgressChangedEventArgs>. Esta clase es necesaria para notificar los resultados incrementales al controlador de eventos del cliente para el evento `ProgressChanged`. Tiene una propiedad agregada denominada `LatestPrimeNumber`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## <a name="checkpoint"></a>Punto de control  
 En este momento, puede compilar el componente.  
  
### <a name="to-test-your-component"></a>Para probar el componente  
  
- Compile el componente.  
  
     Todo lo que queda por escribir son los métodos para iniciar y cancelar operaciones asincrónicas, `CalculatePrimeAsync` y `CancelAsync`.  
  
## <a name="implementing-the-start-and-cancel-methods"></a>Implementación de los métodos de inicio y cancelación  
 Inicie el método de trabajo en su propio subproceso llamando a `BeginInvoke` en el delegado que lo contiene. Para administrar la duración de una operación asincrónica determinada, llame al método <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> en la clase del asistente <xref:System.ComponentModel.AsyncOperationManager>. Devuelve <xref:System.ComponentModel.AsyncOperation>, que serializa las llamadas a los controladores de eventos del cliente para el subproceso o contexto apropiados.  
  
 Puede cancelar una operación pendiente concreta si llama a <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> en su clase <xref:System.ComponentModel.AsyncOperation> correspondiente. Esto finaliza esa operación y todas las llamadas posteriores a <xref:System.ComponentModel.AsyncOperation> generarán una excepción.  
  
### <a name="to-implement-start-and-cancel-functionality"></a>Para implementar la funcionalidad de inicio y cancelación:  
  
1. Implemente el método `CalculatePrimeAsync`. Asegúrese de que el token proporcionado por el cliente (identificador de tarea) es único con respecto a todos los tokens que representan actualmente las tareas pendientes. Si el cliente pasa un token no exclusivo, `CalculatePrimeAsync` genera una excepción. En caso contrario, el token se agrega a la colección de identificador de tarea.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2. Implemente el método `CancelAsync`. Si el parámetro `taskId` existe en la colección de token, se elimina. Esto impide que las tareas canceladas no empiecen a ejecutarse. Si la tarea está en ejecución, el método `BuildPrimeNumberList` se cierra cuando detecta que el identificador de tarea se ha quitado de la colección de duración.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## <a name="checkpoint"></a>Punto de control  
 En este momento, puede compilar el componente.  
  
### <a name="to-test-your-component"></a>Para probar el componente  
  
- Compile el componente.  
  
 El componente `PrimeNumberCalculator` ya está completo y listo para usarse.  
  
 Para un cliente de ejemplo que usa el componente `PrimeNumberCalculator`, consulte [Cómo: Implementar un cliente del modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Puede rellenar este ejemplo escribiendo `CalculatePrime`, el equivalente sincrónico del método `CalculatePrimeAsync`. Esto hará que el componente `PrimeNumberCalculator` sea totalmente compatible con el modelo asincrónico basado en eventos.  
  
 Puede mejorar este ejemplo conservando la lista de todos los números primos detectados por varias invocaciones de distintos números de prueba. Con este enfoque, cada tarea se beneficiará del trabajo realizado por tareas anteriores. Tenga la precaución de proteger esta lista con las regiones `lock`, para que el acceso a la lista por parte de diferentes subprocesos se serialice.  
  
 También puede mejorar este ejemplo probando divisores triviales, como 2, 3 y 5.  
  
## <a name="see-also"></a>Vea también

- [Ejecutar una operación en segundo plano](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)
- [Modelo asincrónico basado en eventos (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
