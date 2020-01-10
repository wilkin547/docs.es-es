---
title: Modelo de subprocesos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text on buttons [WPF], updating
- message processing [WPF], nested
- blocking operations [WPF]
- Common Language Runtime (CLR), locking mechanism
- locking mechanism of Common Language Runtime (CLR)
- threading model [WPF]
- Word [WPF], spelling checking
- button text [WPF], updating
- spelling checking in Word [WPF]
- asynchronous behavior [WPF], exposing
- nested message processing [WPF]
- reentrancy [WPF]
ms.assetid: 02d8fd00-8d7c-4604-874c-58e40786770b
ms.openlocfilehash: 72fa95bde0c41e913bdaa35da7fdcd34f81b3057
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740270"
---
# <a name="threading-model"></a>Modelo de subprocesos
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] está diseñado para evitar a los programadores las dificultades de los subprocesos. Como resultado, la mayoría de los desarrolladores de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no tendrán que escribir una interfaz que use más de un subproceso. Dado que los programas multiproceso son complejos y difíciles de depurar, se deben evitar cuando existan soluciones de un único subproceso.

 Sin embargo, independientemente de lo bien que esté diseñado, ningún marco de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nunca podrá proporcionar una solución de un solo subproceso para cada tipo de problema. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se cierra, pero hay situaciones en las que varios subprocesos [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] mejoran la capacidad de respuesta o el rendimiento de la aplicación. Después de explicar material básico, en este documento se exploran algunas de estas situaciones y, después, se concluye con una explicación de algunos detalles de nivel inferior.

> [!NOTE]
> En este tema se describe el subprocesamiento mediante el método <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> para llamadas asincrónicas. También puede realizar llamadas asincrónicas llamando al método <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, que toma un <xref:System.Action> o <xref:System.Func%601> como parámetro.  El método <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> devuelve un <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>, que tiene una propiedad <xref:System.Windows.Threading.DispatcherOperation.Task%2A>. Puede usar la palabra clave `await` con la <xref:System.Windows.Threading.DispatcherOperation> o la <xref:System.Threading.Tasks.Task>asociada. Si necesita esperar sincrónicamente el <xref:System.Threading.Tasks.Task> devuelto por un <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>, llame al método de extensión <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A>.  La llamada a <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> producirá un interbloqueo. Para obtener más información sobre el uso de un <xref:System.Threading.Tasks.Task> para realizar operaciones asincrónicas, consulte paralelismo de tareas.  El método <xref:System.Windows.Threading.Dispatcher.Invoke%2A> también tiene sobrecargas que toman un <xref:System.Action> o <xref:System.Func%601> como parámetro.  Puede usar el método <xref:System.Windows.Threading.Dispatcher.Invoke%2A> para realizar llamadas sincrónicas pasando un delegado, <xref:System.Action> o <xref:System.Func%601>.

<a name="threading_overview"></a>
## <a name="overview-and-the-dispatcher"></a>Información general y el distribuidor
 Normalmente, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones se inician con dos subprocesos: uno para controlar la representación y otro para administrar el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. El subproceso de representación se ejecuta eficazmente oculto en segundo plano mientras el subproceso [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] recibe la entrada, controla los eventos, pinta la pantalla y ejecuta el código de la aplicación. La mayoría de las aplicaciones usan un único subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], aunque en algunos casos es mejor utilizar varios. Trataremos esto con un ejemplo más adelante.

 El subproceso [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] pone en cola los elementos de trabajo dentro de un objeto denominado <xref:System.Windows.Threading.Dispatcher>. <xref:System.Windows.Threading.Dispatcher> selecciona los elementos de trabajo en función de la prioridad y ejecuta cada uno hasta que se completan.  Cada subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] debe tener al menos un <xref:System.Windows.Threading.Dispatcher>y cada <xref:System.Windows.Threading.Dispatcher> puede ejecutar elementos de trabajo en un solo subproceso.

 El truco para compilar aplicaciones con capacidad de respuesta y fáciles de usar es maximizar el rendimiento de <xref:System.Windows.Threading.Dispatcher> manteniendo los elementos de trabajo pequeños. De este modo, los elementos nunca se desalojan en la cola de <xref:System.Windows.Threading.Dispatcher> en espera de procesamiento. Cualquier retraso perceptible entre la entrada y la respuesta puede frustrar a un usuario.

 ¿Cómo se supone [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones para controlar las operaciones Big? ¿Qué ocurre si el código implica un cálculo grande o necesita consultar una base de datos de algún servidor remoto? Normalmente, la respuesta es controlar la operación grande en un subproceso independiente, lo que permite que el subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] tiende a los elementos de la cola de <xref:System.Windows.Threading.Dispatcher>. Una vez completada la operación grande, puede informar de su resultado al subproceso [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para su presentación.

 Históricamente, Windows permite que solo el subproceso que los creó pueda acceder a los elementos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Esto significa que un subproceso en segundo plano a cargo de una tarea de ejecución prolongada no puede actualizar un cuadro de texto cuando finalice. Windows hace esto para garantizar la integridad de los componentes de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Un cuadro de lista podría tener una apariencia extraña si un subproceso en segundo plano actualiza su contenido durante la presentación.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene un mecanismo de exclusión mutua integrado que aplica esta coordinación. La mayoría de las clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] derivan de <xref:System.Windows.Threading.DispatcherObject>. Durante la construcción, un <xref:System.Windows.Threading.DispatcherObject> almacena una referencia al <xref:System.Windows.Threading.Dispatcher> vinculado al subproceso que se está ejecutando actualmente. En efecto, el <xref:System.Windows.Threading.DispatcherObject> se asocia con el subproceso que lo crea. Durante la ejecución del programa, un <xref:System.Windows.Threading.DispatcherObject> puede llamar a su método de <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> público. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> examina el <xref:System.Windows.Threading.Dispatcher> asociado al subproceso actual y lo compara con la referencia <xref:System.Windows.Threading.Dispatcher> almacenada durante la construcción. Si no coinciden, <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> produce una excepción. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> está previsto que se llame al principio de cada método perteneciente a un <xref:System.Windows.Threading.DispatcherObject>.

 Si solo un subproceso puede modificar el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], ¿cómo interactúan los subprocesos en segundo plano con el usuario? Un subproceso en segundo plano puede pedir al subproceso [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que realice una operación en su nombre. Para ello, registra un elemento de trabajo con el <xref:System.Windows.Threading.Dispatcher> del subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. La clase <xref:System.Windows.Threading.Dispatcher> proporciona dos métodos para registrar los elementos de trabajo: <xref:System.Windows.Threading.Dispatcher.Invoke%2A> y <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>. Ambos métodos programan un delegado para que se ejecute. <xref:System.Windows.Threading.Dispatcher.Invoke%2A> es una llamada sincrónica, es decir, no vuelve hasta que el subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] realmente termina de ejecutar el delegado. <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> es asincrónico y vuelve inmediatamente.

 El <xref:System.Windows.Threading.Dispatcher> ordena los elementos de su cola por prioridad. Hay diez niveles que se pueden especificar al agregar un elemento a la cola de <xref:System.Windows.Threading.Dispatcher>. Estas prioridades se mantienen en la enumeración <xref:System.Windows.Threading.DispatcherPriority>. Puede encontrar información detallada sobre los niveles de <xref:System.Windows.Threading.DispatcherPriority> en la documentación de Windows SDK.

<a name="samples"></a>
## <a name="threads-in-action-the-samples"></a>Subprocesos en acción: ejemplos

<a name="prime_number"></a>
### <a name="a-single-threaded-application-with-a-long-running-calculation"></a>Una aplicación de un único subproceso con un cálculo de ejecución prolongada
 La mayoría de las interfaces gráficas de usuario (GUI) emplean una gran parte de su tiempo de inactividad mientras esperan los eventos que se generan en respuesta a las interacciones del usuario. Con una programación cuidadosa, este tiempo de inactividad puede usarse de un solo uso, sin que ello afecte a la capacidad de respuesta del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. El modelo de subprocesos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no permite que la entrada interrumpa una operación que se está produciendo en el subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Esto significa que debe asegurarse de volver al <xref:System.Windows.Threading.Dispatcher> periódicamente para procesar los eventos de entrada pendientes antes de que queden obsoletos.

 Considere el ejemplo siguiente:

 ![Captura de pantalla que muestra los subprocesos de los números primos.](./media/threading-model/threading-prime-numbers.png)

 Esta sencilla aplicación cuenta en orden ascendente a partir de tres, buscando números primos. Cuando el usuario hace clic en el botón **iniciar** , se inicia la búsqueda. Cuando el programa encuentra un número primo, actualiza la interfaz de usuario con su detección. En cualquier momento, el usuario puede detener la búsqueda.

 Aunque es bastante simple, la búsqueda de números primos podría continuar para siempre, lo que presenta algunas dificultades.  Si trabajamos en la búsqueda completa dentro del controlador de eventos Click del botón, nunca proporcionaremos al subproceso [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] la oportunidad de controlar otros eventos. El [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] no puede responder a los mensajes de entrada o de procesamiento. No se volvería a dibujar nunca y tampoco respondería a los clics de botón.

 Se podría realizar la búsqueda de números primos en un subproceso independiente, pero entonces sería necesario solucionar problemas de sincronización. Con un enfoque de un único subproceso, se puede actualizar directamente la etiqueta que muestra el número primo mayor encontrado.

 Si se divide la tarea de cálculo en fragmentos manejables, se puede volver periódicamente a la <xref:System.Windows.Threading.Dispatcher> y procesar eventos. Podemos dar a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] una oportunidad para volver a dibujar y procesar la entrada.

 La mejor manera de dividir el tiempo de procesamiento entre el cálculo y el control de eventos consiste en administrar el cálculo desde el <xref:System.Windows.Threading.Dispatcher>. Mediante el método <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>, se pueden programar las comprobaciones de números primos en la misma cola de la que se extraen los eventos de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. En el ejemplo, solamente se programa una comprobación de número primo cada vez. Una vez completada la comprobación de número primo, se programa la siguiente de manera inmediata. Esta comprobación continúa solo después de que se hayan controlado los eventos de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] pendientes.

 ![Captura de pantalla que muestra la cola del distribuidor.](./media/threading-model/threading-dispatcher-queue.png)

 Microsoft Word realiza la revisión ortográfica con este mecanismo. La revisión ortográfica se realiza en segundo plano con el tiempo de inactividad del subproceso [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Echemos un vistazo al código.

 En el ejemplo siguiente se muestra el XAML que crea la interfaz de usuario.

 [!code-xaml[ThreadingPrimeNumbers#ThreadingPrimeNumberXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml#threadingprimenumberxaml)]

 En el ejemplo siguiente se muestra el código subyacente.

 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumbercodebehind)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumbercodebehind)]

 En el ejemplo siguiente se muestra el controlador de eventos para el <xref:System.Windows.Controls.Button>.

 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberstartorstop)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberstartorstop)]

 Además de actualizar el texto en el <xref:System.Windows.Controls.Button>, este controlador es responsable de programar la primera comprobación de número primo agregando un delegado a la cola de <xref:System.Windows.Threading.Dispatcher>. En algún momento después de que este controlador de eventos haya completado su trabajo, el <xref:System.Windows.Threading.Dispatcher> seleccionará este delegado para su ejecución.

 Como mencionamos anteriormente, <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> es el miembro de <xref:System.Windows.Threading.Dispatcher> que se usa para programar un delegado para su ejecución. En este caso, elegimos el <xref:System.Windows.Threading.DispatcherPriority.SystemIdle> prioridad. El <xref:System.Windows.Threading.Dispatcher> ejecutará este delegado solo cuando no haya eventos importantes que procesar. La capacidad de respuesta de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] es más importante que la comprobación de números. También se pasa un nuevo delegado que representa la rutina de comprobación de números.

 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberchecknextnumber)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberchecknextnumber)]

 Este método comprueba si el siguiente número impar es primo. Si es primo, el método actualiza directamente el <xref:System.Windows.Controls.TextBlock> `bigPrime`para reflejar su detección. Se puede hacer porque el cálculo se está produciendo en el mismo subproceso que se ha usado para crear el componente. Si hubiéramos elegido usar un subproceso independiente para el cálculo, tendríamos que usar un mecanismo de sincronización más complicado y ejecutar la actualización en el subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. A continuación se mostrará esta situación.

 Para obtener el código fuente completo de este ejemplo, consulte el [ejemplo de aplicación de un único subproceso con un cálculo de ejecución prolongada](https://go.microsoft.com/fwlink/?LinkID=160038) .

<a name="weather_sim"></a>
### <a name="handling-a-blocking-operation-with-a-background-thread"></a>Control de una operación de bloqueo con un subproceso en segundo plano
 El control de operaciones de bloqueo en una aplicación gráfica puede ser difícil. No es recomendable llamar a métodos de bloqueo desde controladores de eventos, porque parecerá que la aplicación se inmoviliza. Podemos usar un subproceso independiente para controlar estas operaciones, pero cuando hayamos terminado, tenemos que sincronizar con el subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] porque no se puede modificar directamente la GUI desde nuestro subproceso de trabajo. Podemos usar <xref:System.Windows.Threading.Dispatcher.Invoke%2A> o <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> para insertar delegados en la <xref:System.Windows.Threading.Dispatcher> del subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Finalmente, estos delegados se ejecutarán con permiso para modificar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos.

 En este ejemplo, se imita una llamada a procedimiento remoto que recupera la previsión meteorológica. Se usa un subproceso de trabajo independiente para ejecutar esta llamada y se programa un método de actualización en el <xref:System.Windows.Threading.Dispatcher> del subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] cuando haya terminado.

 ![Captura de pantalla que muestra la interfaz de usuario meteorológica.](./media/threading-model/threading-weather-ui.png)

 [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweathercodebehind)]
 [!code-vb[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweathercodebehind)]

 A continuación se enumeran algunos de los detalles para tener en cuenta.

- Creación del controlador del botón

     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherbuttonhandler)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherbuttonhandler)]

 Cuando se hace clic en el botón, se muestra el dibujo del reloj y se inicia su animación. Se deshabilita el botón. Se invoca el método `FetchWeatherFromServer` en un nuevo subproceso y, a continuación, se devuelve, lo que permite al <xref:System.Windows.Threading.Dispatcher> procesar eventos mientras se espera para recopilar la previsión meteorológica.

- Captura de la información meteorológica

     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherfetchweather)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherfetchweather)]

 Para simplificar las cosas, en realidad en este ejemplo no hay ningún código de red. En su lugar, es posible simular el retraso de acceso de red haciendo que el nuevo subproceso espere durante cuatro segundos. En este momento, el subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] original todavía se está ejecutando y responde a los eventos. Para mostrarlo, se deja una animación en ejecución y los botones para minimizar y maximizar también siguen funcionando.

 Cuando finaliza el retraso y hemos seleccionado aleatoriamente nuestra previsión meteorológica, es el momento de volver a informar al subproceso [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Para ello, se programa una llamada a `UpdateUserInterface` en el subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con la <xref:System.Windows.Threading.Dispatcher>del subproceso. Se pasa una cadena que describe la información meteorológica a esta llamada de método programada.

- Actualización del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]

     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherupdateui)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherupdateui)]

 Cuando el <xref:System.Windows.Threading.Dispatcher> en el subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] tiene tiempo, ejecuta la llamada programada en `UpdateUserInterface`. Este método detiene la animación del reloj y elige una imagen que describa la información meteorológica. Muestra esta imagen y restaura el botón para "obtener la información meteorológica".

<a name="multi_browser"></a>
### <a name="multiple-windows-multiple-threads"></a>Varias ventanas, varios subprocesos
 Algunas aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] requieren varias ventanas de nivel superior. Es absolutamente aceptable para una combinación de subprocesos y<xref:System.Windows.Threading.Dispatcher> administrar varias ventanas, pero a veces varios subprocesos realizan un mejor trabajo. Esto es especialmente cierto si hay alguna posibilidad de que una de las ventanas monopolice el subproceso.

 El explorador de Windows funciona de este modo. Cada nueva ventana del Explorador pertenece al proceso original, pero se crea bajo el control de un subproceso independiente.

 Mediante el uso de un control <xref:System.Windows.Controls.Frame> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], podemos mostrar páginas Web. Podemos crear fácilmente un sustituto simple de Internet Explorer. Comenzamos con una característica importante: la capacidad de abrir una nueva ventana del explorador. Cuando el usuario hace clic en el botón "Nueva ventana", se inicia una copia de nuestra ventana en un subproceso independiente. De este modo, las operaciones de ejecución prolongada o de bloqueo en una de las ventanas no bloquearán a todas las demás.

 En realidad, el modelo de explorador web tiene su propio modelo complicado de subprocesos. Lo elegimos porque debería resultar conocido para la mayoría de los lectores.

 En el ejemplo siguiente se muestra el código.

 [!code-xaml[ThreadingMultipleBrowsers#ThreadingMultiBrowserXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml#threadingmultibrowserxaml)]

 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsercodebehind)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsercodebehind)]

 Los siguientes segmentos de subprocesos de este código son los que más nos interesan en este contexto:

 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsernewwindow)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsernewwindow)]

 Este método se llama cuando se hace clic en el botón "Nueva ventana". Crea un nuevo subproceso y lo inicia de forma asincrónica.

 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowserthreadstart)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowserthreadstart)]

 Este método es el punto de partida para el nuevo subproceso. Se crea una nueva ventana bajo el control de este subproceso. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea automáticamente un nuevo <xref:System.Windows.Threading.Dispatcher> para administrar el nuevo subproceso. Lo único que hay que hacer para que la ventana sea funcional es iniciar el <xref:System.Windows.Threading.Dispatcher>.

<a name="stumbling_points"></a>
## <a name="technical-details-and-stumbling-points"></a>Detalles técnicos y puntos problemáticos

### <a name="writing-components-using-threading"></a>Escribir componentes mediante subprocesos
 En la guía del desarrollador de Microsoft .NET Framework se describe un patrón sobre cómo un componente puede exponer el comportamiento asincrónico a sus clientes (consulte [información general sobre el modelo asincrónico basado en eventos](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)). Por ejemplo, supongamos que deseamos empaquetar el método `FetchWeatherFromServer` en un componente no gráfico reutilizable. Siguiendo el patrón estándar de Microsoft .NET Framework, se vería algo parecido a lo siguiente.

 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent1)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent1)]

 `GetWeatherAsync` usaría una de las técnicas descritas anteriormente, como la creación de un subproceso en segundo plano, para hacer el trabajo de forma asincrónica, sin bloquear el subproceso de llamada.

 Una de las partes más importantes de este patrón es llamar al método *methodname*`Completed` en el mismo subproceso que llamó al método *MethodName*`Async` para comenzar. Para ello, puede usar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bastante fácilmente, mediante el almacenamiento de <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>, pero el componente no gráfico solo se puede usar en aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], no en programas de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o ASP.NET.

 La clase <xref:System.Windows.Threading.DispatcherSynchronizationContext> se redirige a esta necesidad, piense en ello como una versión simplificada de <xref:System.Windows.Threading.Dispatcher> que también funciona con otros marcos de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].

 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent2)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent2)]

### <a name="nested-pumping"></a>Bombeo anidado
 A veces no es factible bloquear completamente el subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Veamos el método <xref:System.Windows.MessageBox.Show%2A> de la clase <xref:System.Windows.MessageBox>. <xref:System.Windows.MessageBox.Show%2A> no vuelve hasta que el usuario hace clic en el botón Aceptar. Pero crea una ventana que debe tener un bucle de mensajes para poder ser interactiva. Mientras se espera a que el usuario haga clic en Aceptar, la ventana de la aplicación original no responde a la entrada del usuario. Pero sigue procesando los mensajes de pintura. La ventana original se vuelve a dibujar cuando se oculta y se muestra.

 ![Captura de pantalla que muestra un cuadro de mensajes con un botón Aceptar](./media/threading-model/threading-message-loop.png)

 Algún subproceso debe estar a cargo de la ventana del cuadro de mensaje. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] podría crear un nuevo subproceso para la ventana del cuadro de mensaje, pero este subproceso no podría representar los elementos deshabilitados en la ventana original (recuerde la explicación anterior sobre la exclusión mutua). En su lugar, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza un sistema de procesamiento de mensajes anidado. La clase <xref:System.Windows.Threading.Dispatcher> incluye un método especial denominado <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>, que almacena el punto de ejecución actual de la aplicación y, a continuación, inicia un nuevo bucle de mensajes. Cuando finaliza el bucle de mensajes anidados, la ejecución se reanuda después de la llamada de <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> original.

 En este caso, <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> mantiene el contexto del programa en la llamada a <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType>e inicia un nuevo bucle de mensajes para volver a dibujar la ventana de fondo y controlar la entrada en la ventana de cuadro de mensaje. Cuando el usuario hace clic en aceptar y borra la ventana emergente, se cierra el bucle anidado y se reanuda el control después de la llamada a <xref:System.Windows.MessageBox.Show%2A>.

### <a name="stale-routed-events"></a>Eventos enrutados obsoletos
 El sistema de eventos enrutados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] notifica a los árboles completos cuando se producen eventos.

 [!code-xaml[InputOvw#ThreadingArticleStaticRoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#threadingarticlestaticroutedevent)]

 Cuando se presiona el botón primario del mouse sobre la elipse, se ejecuta `handler2`. Una vez finalizada la `handler2`, el evento se pasa al objeto <xref:System.Windows.Controls.Canvas>, que usa `handler1` para procesarlo. Esto solo sucede si `handler2` no marca explícitamente el objeto de evento como controlado.

 Es posible que `handler2` tarde mucho tiempo en procesar este evento. `handler2` podría usar <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> para iniciar un bucle de mensajes anidados que no devuelve para horas. Si `handler2` no marca el evento como controlado cuando se completa este bucle de mensajes, el evento se pasa al árbol aunque sea muy antiguo.

### <a name="reentrancy-and-locking"></a>Reentrada y bloqueo
 El mecanismo de bloqueo del Common Language Runtime (CLR) no se comporta exactamente como puede imaginarse; podría esperar que un subproceso deje de funcionar completamente al solicitar un bloqueo. En realidad, el subproceso continúa recibiendo y procesando mensajes de alta prioridad. Esto ayuda a evitar interbloqueos y a que la capacidad de respuesta de las interfaces sea mínima, pero introduce la posibilidad de errores sutiles.  La inmensa mayoría del tiempo no necesita saber nada sobre esto, pero en raras circunstancias (normalmente implican mensajes de ventana de Win32 o componentes de COM STA), esto puede merecer la pena conocer.

 La mayoría de las interfaces no se crean teniendo en cuenta la seguridad para subprocesos, ya que los desarrolladores trabajan bajo la suposición de que más de un subproceso no tiene acceso nunca a un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. En este caso, ese subproceso único puede realizar cambios en el entorno en momentos inesperados, provocando así los efectos indebidos que se supone que el mecanismo de exclusión mutua <xref:System.Windows.Threading.DispatcherObject>. Considere el siguiente seudocódigo:

 ![Diagrama que muestra la reentrada de subprocesos.](./media/threading-model/threading-reentrancy.png "ThreadingReentrancy")

 La mayor parte del tiempo es lo correcto, pero hay ocasiones en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] donde tal reentrada inesperada puede causar problemas. Por lo tanto, en ciertos momentos clave, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llama a <xref:System.Windows.Threading.Dispatcher.DisableProcessing%2A>, que cambia la instrucción de bloqueo de ese subproceso para usar el bloqueo sin reentrada [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], en lugar del bloqueo CLR habitual.

 ¿Por qué el equipo CLR eligió este comportamiento? Tenía que ver con los objetos COM STA y el subproceso de finalización. Cuando un objeto se recolecta como elemento no utilizado, su método de `Finalize` se ejecuta en el subproceso del finalizador dedicado, no en el subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. En este tema se encuentra el problema, ya que un objeto STA COM creado en el subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] solo se puede desechar en el subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. CLR realiza el equivalente de un <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> (en este caso, mediante Win32 `SendMessage`). Pero si el subproceso de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] está ocupado, el subproceso finalizador se detiene y no se puede eliminar el objeto STA COM, lo que crea una pérdida de memoria grave. Por lo tanto, el equipo de CLR realizó la llamada difícil para que los bloqueos funcionen de la manera en que lo hacen.

 La tarea para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es evitar la reentrada inesperada sin volver a introducir la fuga de memoria, motivo por el que no se bloquea la reentrada en todas partes.

## <a name="see-also"></a>Vea también

- [Single-Threaded Application with Long-Running Calculation Sample](https://go.microsoft.com/fwlink/?LinkID=160038) (Ejemplo de aplicación de un único subproceso con un cálculo de ejecución prolongada)
