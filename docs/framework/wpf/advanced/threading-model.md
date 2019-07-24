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
ms.openlocfilehash: 2667417c5d25821f2fed2101e1d485280e171eab
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400646"
---
# <a name="threading-model"></a>Modelo de subprocesos
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] está diseñado para evitar a los programadores las dificultades de los subprocesos. Como resultado, la mayoría de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] los desarrolladores no tendrán que escribir una interfaz que use más de un subproceso. Dado que los programas multiproceso son complejos y difíciles de depurar, se deben evitar cuando existan soluciones de un único subproceso.  
  
 No obstante, con independencia de la arquitectura, ningún [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] marco de trabajo podrá proporcionar una solución de un solo subproceso para cada tipo de problema. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]se mantiene cerca, pero hay situaciones en las que varios subprocesos mejoran [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] la capacidad de respuesta o el rendimiento de la aplicación. Después de explicar material básico, en este documento se exploran algunas de estas situaciones y, después, se concluye con una explicación de algunos detalles de nivel inferior.  

> [!NOTE]
>  En este tema se describe el subprocesamiento mediante <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> el método para llamadas asincrónicas. También puede realizar llamadas asincrónicas llamando al <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> método, que <xref:System.Action> toma o <xref:System.Func%601> como un parámetro.  El <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> método <xref:System.Windows.Threading.DispatcherOperation.Task%2A> devuelve o ,<xref:System.Windows.Threading.DispatcherOperation%601>que tiene una propiedad. <xref:System.Windows.Threading.DispatcherOperation> Puede usar la `await` palabra clave con <xref:System.Windows.Threading.DispatcherOperation> o con el asociado <xref:System.Threading.Tasks.Task>. Si tiene que esperar sincrónicamente por <xref:System.Threading.Tasks.Task> el devuelto <xref:System.Windows.Threading.DispatcherOperation> por o <xref:System.Windows.Threading.DispatcherOperation%601>, llame al <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> método de extensión.  La <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> llamada a dará como resultado un interbloqueo. Para obtener más información sobre el <xref:System.Threading.Tasks.Task> uso de para realizar operaciones asincrónicas, consulte paralelismo de tareas.  El <xref:System.Windows.Threading.Dispatcher.Invoke%2A> método también tiene sobrecargas que <xref:System.Action> toman o <xref:System.Func%601> como un parámetro.  Puede usar el <xref:System.Windows.Threading.Dispatcher.Invoke%2A> método para realizar llamadas sincrónicas pasando un <xref:System.Action> delegado o <xref:System.Func%601>.  
  
<a name="threading_overview"></a>   
## <a name="overview-and-the-dispatcher"></a>Información general y el distribuidor  
 Normalmente, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las aplicaciones se inician con dos subprocesos: uno para controlar la representación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]y otro para administrar el. El subproceso de representación se ejecuta eficazmente oculto en segundo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] plano mientras el subproceso recibe la entrada, controla los eventos, pinta la pantalla y ejecuta el código de la aplicación. La mayoría de las aplicaciones [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] usan un único subproceso, aunque en algunas situaciones es mejor usar varias. Trataremos esto con un ejemplo más adelante.  
  
 El [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso pone en cola los elementos de trabajo dentro <xref:System.Windows.Threading.Dispatcher>de un objeto denominado. <xref:System.Windows.Threading.Dispatcher> selecciona los elementos de trabajo en función de la prioridad y ejecuta cada uno hasta que se completan.  Todos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] los subprocesos deben tener <xref:System.Windows.Threading.Dispatcher>al menos un <xref:System.Windows.Threading.Dispatcher> , y cada uno de ellos puede ejecutar elementos de trabajo en un solo subproceso.  
  
 El truco para compilar aplicaciones con capacidad de respuesta y fáciles de <xref:System.Windows.Threading.Dispatcher> usar es maximizar el rendimiento manteniendo los elementos de trabajo pequeños. De este modo, los elementos nunca se desalojan en la cola a la <xref:System.Windows.Threading.Dispatcher> espera de ser procesados. Cualquier retraso perceptible entre la entrada y la respuesta puede frustrar a un usuario.  
  
 ¿Cómo se [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supone que las aplicaciones controlan las operaciones Big? ¿Qué ocurre si el código implica un cálculo grande o necesita consultar una base de datos de algún servidor remoto? Normalmente, la respuesta es controlar la operación grande en un subproceso independiente, lo que [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] permite que el subproceso sea gratuito para <xref:System.Windows.Threading.Dispatcher> los elementos de la cola. Una vez completada la operación grande, puede informar de su resultado al [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso para que se muestre.  
  
 Históricamente, [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] solo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] permite acceder a los elementos mediante el subproceso que los creó. Esto significa que un subproceso en segundo plano a cargo de una tarea de ejecución prolongada no puede actualizar un cuadro de texto cuando finalice. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]hace esto para garantizar la integridad de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] los componentes. Un cuadro de lista podría tener una apariencia extraña si un subproceso en segundo plano actualiza su contenido durante la presentación.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene un mecanismo de exclusión mutua integrado que aplica esta coordinación. La mayoría de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las clases <xref:System.Windows.Threading.DispatcherObject>de derivan de. En la construcción, <xref:System.Windows.Threading.DispatcherObject> un almacena una referencia a <xref:System.Windows.Threading.Dispatcher> la vinculada al subproceso que se está ejecutando actualmente. En efecto, el <xref:System.Windows.Threading.DispatcherObject> se asocia con el subproceso que lo crea. Durante la ejecución del programa <xref:System.Windows.Threading.DispatcherObject> , puede llamar a <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> su método público. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A>examina el <xref:System.Windows.Threading.Dispatcher> asociado al subproceso actual y lo compara con la referencia almacenada durante la <xref:System.Windows.Threading.Dispatcher> construcción. Si no coinciden, <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> se produce una excepción. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A>está previsto que se llame al principio de cada método perteneciente a <xref:System.Windows.Threading.DispatcherObject>.  
  
 Si solo un subproceso puede modificar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]el, ¿cómo interactúan los subprocesos en segundo plano con el usuario? Un subproceso en segundo plano [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] puede pedir al subproceso que realice una operación en su nombre. Para ello, registra un elemento <xref:System.Windows.Threading.Dispatcher> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de trabajo con el del subproceso. La <xref:System.Windows.Threading.Dispatcher> clase proporciona dos métodos para registrar los elementos de trabajo <xref:System.Windows.Threading.Dispatcher.Invoke%2A> : <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>y. Ambos métodos programan un delegado para que se ejecute. <xref:System.Windows.Threading.Dispatcher.Invoke%2A>es una llamada sincrónica, es decir, no devuelve hasta que el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso finaliza realmente la ejecución del delegado. <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>es asincrónico y se devuelve inmediatamente.  
  
 <xref:System.Windows.Threading.Dispatcher> Ordena los elementos de la cola por prioridad. Hay diez niveles que se pueden especificar al agregar un elemento a la <xref:System.Windows.Threading.Dispatcher> cola. Estas prioridades se mantienen en la <xref:System.Windows.Threading.DispatcherPriority> enumeración. Puede encontrar información <xref:System.Windows.Threading.DispatcherPriority> detallada sobre los niveles en la [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)] documentación de.  
  
<a name="samples"></a>   
## <a name="threads-in-action-the-samples"></a>Subprocesos en acción: Los ejemplos  
  
<a name="prime_number"></a>   
### <a name="a-single-threaded-application-with-a-long-running-calculation"></a>Una aplicación de un único subproceso con un cálculo de ejecución prolongada  
 La [!INCLUDE[TLA#tla_gui#plural](../../../../includes/tlasharptla-guisharpplural-md.md)] mayoría de los usuarios dedican una gran parte de su tiempo de inactividad mientras esperan los eventos que se generan en respuesta a las interacciones del usuario. Con una programación cuidadosa, este tiempo de inactividad puede usarse de una vez, sin [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]que ello afecte a la capacidad de respuesta de. El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modelo de subprocesos no permite que la entrada interrumpa una operación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se produzca en el subproceso. Esto significa que debe asegurarse de volver a <xref:System.Windows.Threading.Dispatcher> periódicamente para procesar los eventos de entrada pendientes antes de que queden obsoletos.  
  
 Considere el ejemplo siguiente:  
  
 ![Captura de pantalla que muestra los subprocesos de los números primos.](./media/threading-model/threading-prime-numbers.png)  
  
 Esta sencilla aplicación cuenta en orden ascendente a partir de tres, buscando números primos. Cuando el usuario hace clic en el botón **iniciar** , se inicia la búsqueda. Cuando el programa encuentra un número primo, actualiza la interfaz de usuario con su detección. En cualquier momento, el usuario puede detener la búsqueda.  
  
 Aunque es bastante simple, la búsqueda de números primos podría continuar para siempre, lo que presenta algunas dificultades.  Si trabajamos en la búsqueda completa dentro del controlador de eventos Click del botón, nunca proporcionaremos al [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso la oportunidad de controlar otros eventos. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] No podrá responder a los mensajes de entrada o de procesamiento. No se volvería a dibujar nunca y tampoco respondería a los clics de botón.  
  
 Se podría realizar la búsqueda de números primos en un subproceso independiente, pero entonces sería necesario solucionar problemas de sincronización. Con un enfoque de un único subproceso, se puede actualizar directamente la etiqueta que muestra el número primo mayor encontrado.  
  
 Si se divide la tarea de cálculo en fragmentos manejables, se puede volver periódicamente a <xref:System.Windows.Threading.Dispatcher> y procesar eventos. Podemos dar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] una oportunidad para volver a dibujar y procesar la entrada.  
  
 La mejor manera de dividir el tiempo de procesamiento entre el cálculo y el control de eventos es <xref:System.Windows.Threading.Dispatcher>administrar el cálculo desde. Mediante el <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> método, se pueden programar las comprobaciones de números primos en la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] misma cola de la que se extraen los eventos. En el ejemplo, solamente se programa una comprobación de número primo cada vez. Una vez completada la comprobación de número primo, se programa la siguiente de manera inmediata. Esta comprobación continúa solo después de que [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se hayan controlado los eventos pendientes.  
  
 ![Captura de pantalla que muestra la cola del distribuidor.](./media/threading-model/threading-dispatcher-queue.png)  
  
 [!INCLUDE[TLA#tla_word](../../../../includes/tlasharptla-word-md.md)] realiza la revisión ortográfica mediante este mecanismo. La revisión ortográfica se realiza en segundo plano con el tiempo de inactividad del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. Echemos un vistazo al código.  
  
 En el ejemplo siguiente se muestra el XAML que crea la interfaz de usuario.  
  
 [!code-xaml[ThreadingPrimeNumbers#ThreadingPrimeNumberXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml#threadingprimenumberxaml)]  
  
 En el ejemplo siguiente se muestra el código subyacente.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumbercodebehind)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumbercodebehind)]  
  
 En el ejemplo siguiente se muestra el controlador de <xref:System.Windows.Controls.Button>eventos para.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberstartorstop)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberstartorstop)]  
  
 Además de actualizar el texto en <xref:System.Windows.Controls.Button>, este controlador es responsable de programar la primera comprobación de número primo agregando un delegado a la <xref:System.Windows.Threading.Dispatcher> cola. En algún momento después de que este controlador de eventos haya <xref:System.Windows.Threading.Dispatcher> completado su trabajo, seleccionará este delegado para su ejecución.  
  
 Como se mencionó anteriormente, <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> es el <xref:System.Windows.Threading.Dispatcher> miembro que se usa para programar un delegado para su ejecución. En este caso, elegimos la <xref:System.Windows.Threading.DispatcherPriority.SystemIdle> prioridad. <xref:System.Windows.Threading.Dispatcher> Ejecutará este delegado solo cuando no haya eventos importantes que procesar. La capacidad de respuesta de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] es más importante que la comprobación de números. También se pasa un nuevo delegado que representa la rutina de comprobación de números.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberchecknextnumber)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberchecknextnumber)]  
  
 Este método comprueba si el siguiente número impar es primo. Si es primo, el método actualiza `bigPrime` <xref:System.Windows.Controls.TextBlock> directamente para reflejar su detección. Se puede hacer porque el cálculo se está produciendo en el mismo subproceso que se ha usado para crear el componente. Si hubiéramos elegido usar un subproceso independiente para el cálculo, tendríamos que usar un mecanismo de sincronización más complicado y ejecutar la actualización en el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. A continuación se mostrará esta situación.  
  
 Para obtener el código fuente completo de este ejemplo, consulte el [ejemplo de aplicación de un único subproceso con un cálculo de ejecución prolongada](https://go.microsoft.com/fwlink/?LinkID=160038) .  
  
<a name="weather_sim"></a>   
### <a name="handling-a-blocking-operation-with-a-background-thread"></a>Control de una operación de bloqueo con un subproceso en segundo plano  
 El control de operaciones de bloqueo en una aplicación gráfica puede ser difícil. No es recomendable llamar a métodos de bloqueo desde controladores de eventos, porque parecerá que la aplicación se inmoviliza. Podemos usar un subproceso independiente para controlar estas operaciones, pero cuando hayamos terminado, tenemos que sincronizar con el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso porque no se puede modificar [!INCLUDE[TLA2#tla_gui](../../../../includes/tla2sharptla-gui-md.md)] directamente el de nuestro subproceso de trabajo. Se puede usar <xref:System.Windows.Threading.Dispatcher.Invoke%2A> o <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> para <xref:System.Windows.Threading.Dispatcher> Insertar[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] delegados en el del subproceso. Finalmente, estos delegados se ejecutarán con permiso [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para modificar los elementos.  
  
 En este ejemplo, se imita una llamada a procedimiento remoto que recupera la previsión meteorológica. Se usa un subproceso de trabajo independiente para ejecutar esta llamada y se programa un método de actualización <xref:System.Windows.Threading.Dispatcher> en el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del subproceso cuando se haya terminado.  
  
 ![Captura de pantalla que muestra la interfaz de usuario meteorológica.](./media/threading-model/threading-weather-ui.png)  
  
 [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweathercodebehind)]
 [!code-vb[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweathercodebehind)]  
  
 A continuación se enumeran algunos de los detalles para tener en cuenta.  
  
- Creación del controlador del botón  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherbuttonhandler)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherbuttonhandler)]  
  
 Cuando se hace clic en el botón, se muestra el dibujo del reloj y se inicia su animación. Se deshabilita el botón. Se invoca el `FetchWeatherFromServer` método en un nuevo subproceso y, a continuación, se devuelve <xref:System.Windows.Threading.Dispatcher> , lo que permite que el procese eventos mientras se espera para recopilar la previsión meteorológica.  
  
- Captura de la información meteorológica  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherfetchweather)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherfetchweather)]  
  
 Para simplificar las cosas, en realidad en este ejemplo no hay ningún código de red. En su lugar, es posible simular el retraso de acceso de red haciendo que el nuevo subproceso espere durante cuatro segundos. En este momento, el subproceso original [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sigue en ejecución y responde a los eventos. Para mostrarlo, se deja una animación en ejecución y los botones para minimizar y maximizar también siguen funcionando.  
  
 Cuando finaliza el retraso y hemos seleccionado aleatoriamente nuestra previsión meteorológica, es el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] momento de informar al subproceso. Para ello, se programa una llamada a `UpdateUserInterface` en el subproceso con el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del <xref:System.Windows.Threading.Dispatcher>subproceso. Se pasa una cadena que describe la información meteorológica a esta llamada de método programada.  
  
- Actualizar el[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherupdateui)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherupdateui)]  
  
 Cuando el <xref:System.Windows.Threading.Dispatcher> del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso tiene tiempo, ejecuta la llamada programada a `UpdateUserInterface`. Este método detiene la animación del reloj y elige una imagen que describa la información meteorológica. Muestra esta imagen y restaura el botón para "obtener la información meteorológica".  
  
<a name="multi_browser"></a>   
### <a name="multiple-windows-multiple-threads"></a>Varias ventanas, varios subprocesos  
 Algunas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones requieren varias ventanas de nivel superior. Es absolutamente aceptable que un subproceso o<xref:System.Windows.Threading.Dispatcher> combinación administre varias ventanas, pero a veces varios subprocesos realizan un mejor trabajo. Esto es especialmente cierto si hay alguna posibilidad de que una de las ventanas monopolice el subproceso.  
  
 El Explorador de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] funciona de esta manera. Cada nueva ventana del Explorador pertenece al proceso original, pero se crea bajo el control de un subproceso independiente.  
  
 Mediante el uso [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de un <xref:System.Windows.Controls.Frame> control, podemos mostrar páginas Web. Podemos crear fácilmente un sustituto sencillo [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] . Comenzamos con una característica importante: la capacidad de abrir una nueva ventana del explorador. Cuando el usuario hace clic en el botón "Nueva ventana", se inicia una copia de nuestra ventana en un subproceso independiente. De este modo, las operaciones de ejecución prolongada o de bloqueo en una de las ventanas no bloquearán a todas las demás.  
  
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
  
 Este método es el punto de partida para el nuevo subproceso. Se crea una nueva ventana bajo el control de este subproceso. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]crea automáticamente un nuevo <xref:System.Windows.Threading.Dispatcher> para administrar el nuevo subproceso. Lo único que hay que hacer para que la ventana sea funcional es iniciar <xref:System.Windows.Threading.Dispatcher>el.  
  
<a name="stumbling_points"></a>   
## <a name="technical-details-and-stumbling-points"></a>Detalles técnicos y puntos problemáticos  
  
### <a name="writing-components-using-threading"></a>Escribir componentes mediante subprocesos  
 En la guía del desarrollador de Microsoft .NET Framework se describe un patrón sobre cómo un componente puede exponer el comportamiento asincrónico a sus clientes (consulte [información general sobre el modelo asincrónico basado en eventos](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)). Por ejemplo, supongamos que deseamos `FetchWeatherFromServer` empaquetar el método en un componente no gráfico reutilizable. Siguiendo el patrón estándar de Microsoft .NET Framework, se vería algo parecido a lo siguiente.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent1)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent1)]  
  
 `GetWeatherAsync` usaría una de las técnicas descritas anteriormente, como la creación de un subproceso en segundo plano, para hacer el trabajo de forma asincrónica, sin bloquear el subproceso de llamada.  
  
 Una de las partes más importantes de este patrón es llamar al método *MethodName* `Completed` en el mismo subproceso que llamó al método *MethodName* `Async` para comenzar. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Puede hacer esto con bastante facilidad, mediante el almacenamiento <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>, pero el componente no gráfico solo podría usarse en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones, no en programas de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o ASP.net.  
  
 La <xref:System.Windows.Threading.DispatcherSynchronizationContext> clase se ocupa de esta necesidad, como es una versión simplificada <xref:System.Windows.Threading.Dispatcher> de que también funciona [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con otros marcos de trabajo.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent2)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent2)]  
  
### <a name="nested-pumping"></a>Bombeo anidado  
 A veces no es factible bloquear completamente el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. Veamos el <xref:System.Windows.MessageBox.Show%2A> método de la <xref:System.Windows.MessageBox> clase. <xref:System.Windows.MessageBox.Show%2A>no vuelve hasta que el usuario hace clic en el botón Aceptar. Pero crea una ventana que debe tener un bucle de mensajes para poder ser interactiva. Mientras se espera a que el usuario haga clic en Aceptar, la ventana de la aplicación original no responde a la entrada del usuario. Pero sigue procesando los mensajes de pintura. La ventana original se vuelve a dibujar cuando se oculta y se muestra.  
  
 ![Captura de pantalla que muestra un cuadro de mensajes con un botón Aceptar](./media/threading-model/threading-message-loop.png)  
  
 Algún subproceso debe estar a cargo de la ventana del cuadro de mensaje. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] podría crear un nuevo subproceso para la ventana del cuadro de mensaje, pero este subproceso no podría representar los elementos deshabilitados en la ventana original (recuerde la explicación anterior sobre la exclusión mutua). En su lugar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , utiliza un sistema de procesamiento de mensajes anidado. La <xref:System.Windows.Threading.Dispatcher> clase incluye un método especial denominado <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>, que almacena el punto de ejecución actual de la aplicación y, a continuación, inicia un nuevo bucle de mensajes. Cuando finaliza el bucle de mensajes anidados, la ejecución se reanuda después <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> de la llamada original.  
  
 En este caso, <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> mantiene el contexto del programa en la llamada <xref:System.Windows.MessageBox>a<xref:System.Windows.MessageBox.Show%2A>., e inicia un nuevo bucle de mensajes para volver a dibujar la ventana de fondo y controlar la entrada en la ventana de cuadro de mensaje. Cuando el usuario hace clic en aceptar y borra la ventana emergente, se cierra el bucle anidado y se reanuda el control después de la llamada a <xref:System.Windows.MessageBox.Show%2A>.  
  
### <a name="stale-routed-events"></a>Eventos enrutados obsoletos  
 El sistema de eventos enrutados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] notifica a los árboles completos cuando se producen eventos.  
  
 [!code-xaml[InputOvw#ThreadingArticleStaticRoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#threadingarticlestaticroutedevent)]  
  
 Cuando se presiona el botón primario del mouse sobre la elipse, `handler2` se ejecuta. Una `handler2` vez finalizado, el evento se pasa <xref:System.Windows.Controls.Canvas> al objeto, que utiliza `handler1` para procesarlo. Esto solo sucede si `handler2` no marca explícitamente el objeto de evento como controlado.  
  
 Es posible que `handler2` se tarde mucho tiempo en procesar este evento. `handler2`puede usar <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> para iniciar un bucle de mensajes anidados que no devuelve para horas. Si `handler2` no marca el evento como controlado cuando se completa este bucle de mensajes, el evento se pasa al árbol a pesar de ser muy antiguo.  
  
### <a name="reentrancy-and-locking"></a>Reentrada y bloqueo  
 El mecanismo de bloqueo del Common Language Runtime (CLR) no se comporta exactamente como puede imaginarse; podría esperar que un subproceso deje de funcionar completamente al solicitar un bloqueo. En realidad, el subproceso continúa recibiendo y procesando mensajes de alta prioridad. Esto ayuda a evitar interbloqueos y a que la capacidad de respuesta de las interfaces sea mínima, pero introduce la posibilidad de errores sutiles.  La inmensa mayoría del tiempo no necesita saber nada sobre esto, pero en raras circunstancias (normalmente implican [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] mensajes de ventana o componentes de com STA) esto puede merecer la pena conocer.  
  
 La mayoría de las interfaces no se crean teniendo en cuenta la seguridad para subprocesos, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ya que los desarrolladores trabajan bajo la suposición de que nunca se tiene acceso a a través de más de un subproceso. En este caso, ese subproceso único puede realizar cambios en el entorno en momentos inesperados, provocando así los efectos indebidos que se supone que el <xref:System.Windows.Threading.DispatcherObject> mecanismo de exclusión mutua debe resolver. Considere el siguiente seudocódigo:  
  
 ![Diagrama que muestra la reentrada de subprocesos.](./media/threading-model/threading-reentrancy.png "ThreadingReentrancy")  
  
 La mayor parte del tiempo es lo correcto, pero hay ocasiones en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las que tal reentrada inesperada puede causar problemas. Por lo tanto, en ciertos momentos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clave <xref:System.Windows.Threading.Dispatcher.DisableProcessing%2A>, llama a, que cambia la instrucción de bloqueo de ese [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] subproceso para utilizar el bloqueo sin reentrada, en lugar del bloqueo CLR habitual.  
  
 ¿Por qué el equipo CLR eligió este comportamiento? Tenía que ver con los objetos COM STA y el subproceso de finalización. Cuando un objeto se recolecta como elemento no `Finalize` utilizado, el método se ejecuta en el subproceso del finalizador dedicado, no en el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. En este tema se encuentra el problema, ya que un objeto STA com creado en el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso solo se puede desechar en el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. CLR realiza el equivalente de <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> (en este caso, mediante Win32 `SendMessage`). Pero si el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso está ocupado, el subproceso finalizador se detiene y no se puede eliminar el objeto STA com, lo que crea una pérdida de memoria grave. Por lo tanto, el equipo de CLR realizó la llamada difícil para que los bloqueos funcionen de la manera en que lo hacen.  
  
 La tarea para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es evitar la reentrada inesperada sin volver a introducir la fuga de memoria, motivo por el que no se bloquea la reentrada en todas partes.  
  
## <a name="see-also"></a>Vea también

- [Single-Threaded Application with Long-Running Calculation Sample](https://go.microsoft.com/fwlink/?LinkID=160038) (Ejemplo de aplicación de un único subproceso con un cálculo de ejecución prolongada)
