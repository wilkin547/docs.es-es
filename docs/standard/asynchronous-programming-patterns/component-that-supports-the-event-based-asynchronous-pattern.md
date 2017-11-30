---
title: "Tutorial: Implementar un componente que admita el modelo asincrónico basado en eventos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 150e4b27cc149774895574ddd196de5f9bc2acd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-a-component-that-supports-the-event-based-asynchronous-pattern"></a>Tutorial: Implementar un componente que admita el modelo asincrónico basado en eventos
Si está escribiendo una clase con algunas operaciones que puedan incurrir en retrasos notables, considere la posibilidad de darle funcionalidad asincrónica implementando la [introducción de patrón asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
 Este tutorial muestra cómo crear un componente que implementa el modelo asincrónico basado en eventos. Se implementa utilizando las clases auxiliares de la <xref:System.ComponentModel?displayProperty=nameWithType> espacio de nombres, lo que garantiza que el componente funciona correctamente bajo cualquier modelo de aplicación, incluidos [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], aplicaciones de formularios Windows Forms y aplicaciones de consola. Este componente es también puede diseñar con una <xref:System.Windows.Forms.PropertyGrid> control y sus propios diseñadores personalizados.  
  
 Cuando haya terminado, tendrá una aplicación que calcula los números primos de forma asincrónica. La aplicación tendrá un subproceso de interfaz (UI) de usuario principal y un subproceso para cada cálculo de números primos. Aunque comprobar si es un gran número primo puede tardar bastante tiempo, el subproceso de interfaz de usuario principal no se interrumpirá por este retraso y el formulario seguirá receptivo durante los cálculos. Podrá ejecutar como muchos cálculos como desee simultáneamente y de forma selectiva Cancelar cálculos pendientes.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear el componente  
  
-   Definir delegados y eventos asincrónicos públicos  
  
-   Definir delegados privados  
  
-   Implementar eventos públicos  
  
-   Implementar el método de finalización  
  
-   Implementar los métodos de trabajo  
  
-   Implementar métodos de inicio y cancelar  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: implementar un componente que admita el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
## <a name="creating-the-component"></a>Crear el componente  
 El primer paso es crear el componente que implementará el modelo asincrónico basado en eventos.  
  
#### <a name="to-create-the-component"></a>Para crear el componente  
  
-   Cree una clase denominada `PrimeNumberCalculator` que hereda de <xref:System.ComponentModel.Component>.  
  
## <a name="defining-public-asynchronous-events-and-delegates"></a>Definir delegados y eventos asincrónicos públicos  
 El componente se comunica con los clientes mediante eventos. El *MethodName* `Completed` alertas de eventos a los clientes la finalización de una tarea asincrónica y el *MethodName* `ProgressChanged` eventos informa a los clientes del progreso de una tarea asincrónica.  
  
#### <a name="to-define-asynchronous-events-for-clients-of-your-component"></a>Para definir eventos asincrónicos para los clientes de su componente:  
  
1.  Importar la <xref:System.Threading?displayProperty=nameWithType> y <xref:System.Collections.Specialized?displayProperty=nameWithType> los espacios de nombres en la parte superior del archivo.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2.  Antes de la `PrimeNumberCalculator` definición, de la clase declarar delegados para los eventos de progreso y la finalización.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3.  En el `PrimeNumberCalculator` definición de clase, declare los eventos para los informes de progreso y la finalización a los clientes.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4.  Después de la `PrimeNumberCalculator` definición de clase, derive la `CalculatePrimeCompletedEventArgs` clase para informar del resultado de cada cálculo al controlador de eventos del cliente la `CalculatePrimeCompleted`.event. Además el `AsyncCompletedEventArgs` propiedades, esta clase permite al cliente determinar qué numero se ha comprobado, si es primo y cuál es el primer divisor si no es principal.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## <a name="checkpoint"></a>Punto de control  
 En este momento, puede compilar el componente.  
  
#### <a name="to-test-your-component"></a>Para probar el componente  
  
-   Compilar el componente.  
  
     Recibirá dos advertencias del compilador:  
  
    ```  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     Estas advertencias se borrará en la sección siguiente.  
  
## <a name="defining-private-delegates"></a>Definir delegados privados  
 Los aspectos asincrónicos de las `PrimeNumberCalculator` componentes se implementan internamente con un delegado especial conocido como un <xref:System.Threading.SendOrPostCallback>. A <xref:System.Threading.SendOrPostCallback> representa un método de devolución de llamada que se ejecuta en un <xref:System.Threading.ThreadPool> subproceso. El método de devolución de llamada debe tener una firma que toma un único parámetro de tipo <xref:System.Object>, lo que significa que tendrá que pasar información de estado entre los delegados de una clase contenedora. Para obtener más información, consulta <xref:System.Threading.SendOrPostCallback>.  
  
#### <a name="to-implement-your-components-internal-asynchronous-behavior"></a>Para implementar un comportamiento asincrónico interno de su componente:  
  
1.  Declarar y crear el <xref:System.Threading.SendOrPostCallback> delega en el `PrimeNumberCalculator` clase. Crear el <xref:System.Threading.SendOrPostCallback> llaman a objetos en un método de utilidad `InitializeDelegates`.  
  
     Necesitará dos delegados: uno para notificar el progreso al cliente y otro para informar sobre la finalización al cliente.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2.  Llame a la `InitializeDelegates` método en el constructor del componente.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3.  Declarar un delegado en el `PrimeNumberCalculator` clase que administra el trabajo real para realizarse de forma asincrónica. Este delegado ajusta el método de trabajo que comprueba si un número es primo. El delegado toma un <xref:System.ComponentModel.AsyncOperation> parámetro, que se usará para realizar el seguimiento de la duración de la operación asincrónica.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4.  Crear una colección para administrar la duración de las operaciones asincrónicas pendientes. El cliente necesita una manera para realizar un seguimiento de las operaciones que se ejecuta y completa, y este seguimiento se debe exigir al cliente pasar un token único o un identificador de tarea, cuando el cliente realiza la llamada al método asincrónico. El `PrimeNumberCalculator` componente debe mantener un seguimiento de cada llamada asociando el identificador de tarea a su invocación correspondiente. Si el cliente pasa un identificador de tarea que no es único, el `PrimeNumberCalculator` componente debe generar una excepción.  
  
     El `PrimeNumberCalculator` componente realiza un seguimiento de Id. de tarea mediante el uso de una clase de colección especial denominada una <xref:System.Collections.Specialized.HybridDictionary>. En la definición de clase, cree un <xref:System.Collections.Specialized.HybridDictionary> denominado `userTokenToLifetime`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## <a name="implementing-public-events"></a>Implementar eventos públicos  
 Componentes que implementan el modelo asincrónico basado en eventos se comunican con los clientes mediante eventos. Estos eventos se invocan en el subproceso adecuado con la Ayuda de la <xref:System.ComponentModel.AsyncOperation> clase.  
  
#### <a name="to-raise-events-to-your-components-clients"></a>Para generar los eventos en los clientes de su componente:  
  
1.  Implementar eventos públicos para informar a los clientes. Necesitará un evento para los informes de progreso y otro para informar de la finalización.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## <a name="implementing-the-completion-method"></a>Implementar el método de finalización  
 El delegado de finalización es el método que invocará el comportamiento asincrónico de subprocesamiento libre subyacente cuando finaliza la operación asincrónica de éxito, error o cancelación. Esta invocación se produce en un subproceso arbitrario.  
  
 Este método es donde se quita el Id. de tarea del cliente de la colección interna de símbolos (tokens) de cliente único. Este método también finaliza la duración de una operación asincrónica determinada llamando a la <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> método en la correspondiente <xref:System.ComponentModel.AsyncOperation>. Esta llamada provoca el evento de finalización en el subproceso que es adecuado para el modelo de aplicación. Después de la <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> método se llama, esta instancia de <xref:System.ComponentModel.AsyncOperation> ya no se puede utilizar, y todos los intentos subsiguientes para usarlo, producen una excepción.  
  
 El `CompletionMethod` firma debe contener todos los estados necesarios para describir el resultado de la operación asincrónica. Contiene información de estado para el número que se ha probado por esta operación asincrónica concreta, si el número es primo y el valor de su primer divisor si no es un número primo. También contiene información de estado que describe cualquier excepción que se ha producido, y el <xref:System.ComponentModel.AsyncOperation> correspondiente a esta tarea concreta.  
  
#### <a name="to-complete-an-asynchronous-operation"></a>Para completar una operación asincrónica:  
  
-   Implemente el método de finalización. Toma seis parámetros, que usa para rellenar un `CalculatePrimeCompletedEventArgs` que se devuelve al cliente a través del cliente `CalculatePrimeCompletedEventHandler`. Quita el token de Id. de tarea del cliente de la colección interna y termina la duración de la operación asincrónica con una llamada a <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>. El <xref:System.ComponentModel.AsyncOperation> calcula las referencias de la llamada al subproceso o contexto que sea adecuado para el modelo de aplicación.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## <a name="checkpoint"></a>Punto de control  
 En este momento, puede compilar el componente.  
  
#### <a name="to-test-your-component"></a>Para probar el componente  
  
-   Compilar el componente.  
  
     Recibirá una advertencia del compilador:  
  
    ```  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     Esta advertencia se resolverá en la sección siguiente.  
  
## <a name="implementing-the-worker-methods"></a>Implementar los métodos de trabajo  
 Hasta ahora, ha implementado el código asincrónico admitido para el `PrimeNumberCalculator` componente. Ahora puede implementar el código que realiza el trabajo real. Implementará tres métodos: `CalculateWorker`, `BuildPrimeNumberList`, y `IsPrime`. Juntos, `BuildPrimeNumberList` y `IsPrime` constituyen un algoritmo muy conocido denominado criba de Eratóstenes, que determina si un número es primo buscando todos los números primos hasta la raíz cuadrada del número de pruebas. Si no se encuentran ningún divisores por ese punto, el número de pruebas es primo.  
  
 Si este componente se hubiera escrito para obtener la máxima eficacia, ¿recuerde que todos los números primos detectados por distintas invocaciones de los números de prueba diferentes. También buscaría divisores triviales como 2, 3 y 5. El propósito de este ejemplo es demostrar operaciones prolongadas cómo se puede ejecutar de forma asincrónica, sin embargo, por lo que estas optimizaciones se dejan como un ejercicio para usted.  
  
 El `CalculateWorker` método se ajusta en un delegado y se invoca de forma asincrónica con una llamada a `BeginInvoke`.  
  
> [!NOTE]
>  Informes de progreso se implementan en el `BuildPrimeNumberList` método. En equipos rápidos, `ProgressChanged` se pueden producir eventos en una sucesión rápida. El subproceso de cliente, en el que se producen estos eventos, debe ser capaz de controlar esta situación. Código de la interfaz de usuario puede estar congestiona con mensajes y no se puede mantener el ritmo, lo que produce hanging comportamiento. Para una interfaz de usuario de ejemplo que controla esta situación, vea [Cómo: implementar un cliente del modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
#### <a name="to-execute-the-prime-number-calculation-asynchronously"></a>Para ejecutar de forma asincrónica el cálculo de números primos:  
  
1.  Implemente el `TaskCanceled` método de utilidad. Esto comprueba la colección de duración de tarea para el identificador de tarea determinado y devuelve `true` si no se encuentra el Id. de tarea.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2.  Implemente el método `CalculateWorker`. Toma dos parámetros: un número para probar y un <xref:System.ComponentModel.AsyncOperation>.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3.  Implemente `BuildPrimeNumberList`. Toma dos parámetros: el número que se va a probar y un <xref:System.ComponentModel.AsyncOperation>. Utiliza el <xref:System.ComponentModel.AsyncOperation> para informar del progreso y resultados incrementales. Esto garantiza que se llama a los controladores de eventos del cliente en el subproceso o contexto apropiado para el modelo de aplicación. Cuando `BuildPrimeNumberList` encuentra un número primo, informa de éste como resultado incremental al controlador de eventos del cliente la `ProgressChanged` eventos. Esto requiere una clase derivada de <xref:System.ComponentModel.ProgressChangedEventArgs>, llamado `CalculatePrimeProgressChangedEventArgs`, que tiene una propiedad agregada denominada `LatestPrimeNumber`.  
  
     El `BuildPrimeNumberList` método llama periódicamente la `TaskCanceled` método y se cierra si el método devuelve `true`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4.  Implemente `IsPrime`. Acepta tres parámetros: una lista de números primos conocidos, el número que se va a probar y un parámetro de salida para el primer divisor encontrado. Dada la lista de números primos, determina si el número de pruebas es primo.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5.  Derivar `CalculatePrimeProgressChangedEventArgs` de <xref:System.ComponentModel.ProgressChangedEventArgs>. Esta clase es necesaria para informar de los resultados incrementales al controlador de eventos del cliente la `ProgressChanged` eventos. Tiene una propiedad adicional denominada `LatestPrimeNumber`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## <a name="checkpoint"></a>Punto de control  
 En este momento, puede compilar el componente.  
  
#### <a name="to-test-your-component"></a>Para probar el componente  
  
-   Compilar el componente.  
  
     Todo lo que queda por escribir es los métodos para iniciar y cancelar operaciones asincrónicas, `CalculatePrimeAsync` y `CancelAsync`.  
  
## <a name="implementing-the-start-and-cancel-methods"></a>Implementar los métodos de cancelación y de inicio  
 Inicie el método de trabajo en su propio subproceso llamando a `BeginInvoke` en el delegado que lo contiene. Para administrar la duración de una operación asincrónica determinada, llame a la <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> método en la <xref:System.ComponentModel.AsyncOperationManager> clase auxiliar. Esto devuelve un <xref:System.ComponentModel.AsyncOperation>, que calcula las referencias de llamadas en los controladores de eventos del cliente para el subproceso o contexto apropiado.  
  
 Cancelar una operación pendiente determinada llamando <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> en su correspondiente <xref:System.ComponentModel.AsyncOperation>. Esto finaliza esa operación y las subsiguientes llamadas a su <xref:System.ComponentModel.AsyncOperation> se iniciará una excepción.  
  
#### <a name="to-implement-start-and-cancel-functionality"></a>Para implementar el inicio y cancelar la funcionalidad:  
  
1.  Implemente el método `CalculatePrimeAsync`. Asegúrese de que el token proporcionado por el cliente (Id. de tarea) es único con respecto a todos los tokens que representan actualmente las tareas pendientes. Si el cliente pasa en un token no es único, `CalculatePrimeAsync` produce una excepción. En caso contrario, el token se agrega a la colección de Id. de tarea.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2.  Implemente el método `CancelAsync`. Si el `taskId` parámetro existe en la colección de token, se quita. Esto evita que la tarea cancelada que no haya iniciado de ejecución. Si la tarea se está ejecutando, el `BuildPrimeNumberList` método finaliza cuando detecta que el identificador de tarea se ha quitado de la colección de duración.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## <a name="checkpoint"></a>Punto de control  
 En este momento, puede compilar el componente.  
  
#### <a name="to-test-your-component"></a>Para probar el componente  
  
-   Compilar el componente.  
  
 El `PrimeNumberCalculator` componente ya está completo y listo para usarse.  
  
 Para un cliente de ejemplo que usa el `PrimeNumberCalculator` componente, vea [Cómo: implementar un cliente del modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## <a name="next-steps"></a>Pasos siguientes  
 Puede rellenar este ejemplo escribiendo `CalculatePrime`, el equivalente sincrónico de `CalculatePrimeAsync` método. Esto hará que el `PrimeNumberCalculator` componente totalmente compatible con el modelo asincrónico basado en eventos.  
  
 Puede mejorar este ejemplo, pero se mantiene la lista de todos los números primos detectados por distintas invocaciones de los números de prueba diferentes. Con este enfoque, cada tarea se beneficiará del trabajo realizado por tareas anteriores. Tenga cuidado proteger esta lista con `lock` regiones, por lo que se serializa el acceso a la lista en subprocesos diferentes.  
  
 También puede mejorar este ejemplo probando divisores triviales, como 2, 3 y 5.  
  
## <a name="see-also"></a>Vea también  
 [Ejecutar una operación en segundo plano](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)  
 [NO está en la compilación: Multithreading en Visual Basic](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)  
 [Implementar un componente que admita el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [Programación multiproceso con el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
