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
ms.openlocfilehash: 15115cc0ed14cb5605100ebe47abd5cd4dc02ec0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="threading-model"></a>Modelo de subprocesos
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] está diseñado para evitar a los programadores las dificultades de los subprocesos. Como resultado, la mayoría de los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] los programadores no tienen que escribir una interfaz que usa más de un subproceso. Dado que los programas multiproceso son complejos y difíciles de depurar, se deben evitar cuando existan soluciones de un único subproceso.  
  
 Importar lo bien no diseñado, sin embargo, no [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] framework nunca será capaz de proporcionar una solución de un solo subproceso para cada tipo de problema. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye cerrar, pero todavía hay situaciones en las que varios subprocesos mejoran [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] rendimiento de la capacidad de respuesta o la aplicación. Después de explicar material básico, en este documento se exploran algunas de estas situaciones y, después, se concluye con una explicación de algunos detalles de nivel inferior.  
  

  
> [!NOTE]
>  En este tema se describe el subprocesamiento utilizando el <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> método para las llamadas asincrónicas. También puede realizar llamadas asincrónicas mediante una llamada a la <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> método, que tienen un <xref:System.Action> o <xref:System.Func%601> como un parámetro.  El <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> método devuelve un <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>, que tiene un <xref:System.Windows.Threading.DispatcherOperation.Task%2A> propiedad. Puede usar el `await` palabra clave con cualquiera el <xref:System.Windows.Threading.DispatcherOperation> o asociado <xref:System.Threading.Tasks.Task>. Si tiene que esperar sincrónicamente el <xref:System.Threading.Tasks.Task> devuelto por una <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>, llame a la <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> método de extensión.  Al llamar a <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> dará como resultado un interbloqueo. Para obtener más información sobre el uso de un <xref:System.Threading.Tasks.Task> para llevar a cabo operaciones asincrónicas, vea el paralelismo de tareas.  El <xref:System.Windows.Threading.Dispatcher.Invoke%2A> método también tiene sobrecargas que toman un <xref:System.Action> o <xref:System.Func%601> como un parámetro.  Puede usar el <xref:System.Windows.Threading.Dispatcher.Invoke%2A> método para hacer síncrona llama pasando un delegado, <xref:System.Action> o <xref:System.Func%601>.  
  
<a name="threading_overview"></a>   
## <a name="overview-and-the-dispatcher"></a>Información general y el distribuidor  
 Por lo general, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones se inician con dos subprocesos: uno para controlar la representación y otro para administrar la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. El subproceso de representación se ejecuta eficazmente oculto en segundo plano mientras el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso recibe la entrada, controla los eventos, pinta la pantalla y se ejecuta el código de la aplicación. Mayoría de aplicaciones utilizan un único [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso, aunque en algunas situaciones es mejor utilizar varios. Trataremos esto con un ejemplo más adelante.  
  
 El [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso pone en cola trabajos elementos dentro de un objeto denominado un <xref:System.Windows.Threading.Dispatcher>. <xref:System.Windows.Threading.Dispatcher> selecciona los elementos de trabajo en función de la prioridad y ejecuta cada uno hasta que se completan.  Cada [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso debe tener al menos un <xref:System.Windows.Threading.Dispatcher>y cada <xref:System.Windows.Threading.Dispatcher> pueden ejecutar los elementos de trabajo en exactamente un subproceso.  
  
 El truco para compilar aplicaciones con capacidad de respuesta y fácil de usar es maximizar la <xref:System.Windows.Threading.Dispatcher> rendimiento manteniendo los elementos de trabajo pequeño. Los elementos de esta forma nunca quedan obsoletos en la <xref:System.Windows.Threading.Dispatcher> cola en espera para su procesamiento. Cualquier retraso perceptible entre la entrada y la respuesta puede frustrar a un usuario.  
  
 ¿Cómo quiere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones supone que administran grandes operaciones? ¿Qué ocurre si el código implica un cálculo grande o necesita consultar una base de datos de algún servidor remoto? Normalmente, la respuesta es administrar la operación grande en un subproceso independiente, dejando el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso libre tienden a los elementos de la <xref:System.Windows.Threading.Dispatcher> cola. Una vez completada la operación grande, puede informar sobre su resultado a la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso para su presentación.  
  
 Históricamente, [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] permite [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos que solo esté accesible para el subproceso que los creó. Esto significa que un subproceso en segundo plano a cargo de una tarea de ejecución prolongada no puede actualizar un cuadro de texto cuando finalice. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] lo hace así para garantizar la integridad de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] componentes. Un cuadro de lista podría tener una apariencia extraña si un subproceso en segundo plano actualiza su contenido durante la presentación.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene un mecanismo de exclusión mutua integrado que aplica esta coordinación. Mayoría de las clases en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] derivan de <xref:System.Windows.Threading.DispatcherObject>. En la construcción, un <xref:System.Windows.Threading.DispatcherObject> almacena una referencia a la <xref:System.Windows.Threading.Dispatcher> vinculado para el subproceso actualmente en ejecución. En efecto, el <xref:System.Windows.Threading.DispatcherObject> asocia con el subproceso que lo crea. Durante la ejecución del programa, un <xref:System.Windows.Threading.DispatcherObject> puede llamar a su público <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> método. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> examina la <xref:System.Windows.Threading.Dispatcher> asociado al subproceso actual y lo compara con el <xref:System.Windows.Threading.Dispatcher> almacenada durante la construcción de referencia. Si no coinciden, <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> produce una excepción. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> está pensado para ser invocado al principio de cada método perteneciente a una <xref:System.Windows.Threading.DispatcherObject>.  
  
 Si solo un subproceso puede modificar el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], ¿cómo interactúan los subprocesos en segundo plano con el usuario? Puede pedir a un subproceso en segundo plano el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso para realizar una operación en su nombre. Para ello, registrando un elemento de trabajo con el <xref:System.Windows.Threading.Dispatcher> de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. El <xref:System.Windows.Threading.Dispatcher> clase proporciona dos métodos para registrar los elementos de trabajo: <xref:System.Windows.Threading.Dispatcher.Invoke%2A> y <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>. Ambos métodos programan un delegado para que se ejecute. <xref:System.Windows.Threading.Dispatcher.Invoke%2A> es una llamada sincrónica: es decir, no devuelve hasta que el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] realmente subproceso termina de ejecutar el delegado. <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> es asincrónica y vuelve inmediatamente.  
  
 El <xref:System.Windows.Threading.Dispatcher> ordena los elementos en su cola por prioridad. Hay diez niveles que se pueden especificar cuando se agrega un elemento a la <xref:System.Windows.Threading.Dispatcher> cola. Estas prioridades se mantienen en la <xref:System.Windows.Threading.DispatcherPriority> enumeración. Obtener información sobre <xref:System.Windows.Threading.DispatcherPriority> niveles pueden encontrarse en el [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)] documentación.  
  
<a name="samples"></a>   
## <a name="threads-in-action-the-samples"></a>Subprocesos en acción: ejemplos  
  
<a name="prime_number"></a>   
### <a name="a-single-threaded-application-with-a-long-running-calculation"></a>Una aplicación de un único subproceso con un cálculo de ejecución prolongada  
 La mayoría [!INCLUDE[TLA#tla_gui#plural](../../../../includes/tlasharptla-guisharpplural-md.md)] dedican una gran parte de su tiempo de inactividad mientras se espera para los eventos que se generan en respuesta a las interacciones del usuario. Con la programación sea cuidadosa este tiempo de inactividad puede utilizarse constructivamente, sin que afecte a la capacidad de respuesta de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modelo de subprocesos no permite realizar entradas interrumpir una operación que ocurra en el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. Esto significa que debe ser seguro volver a la <xref:System.Windows.Threading.Dispatcher> periódicamente al proceso pendiente de eventos de entrada antes de que queden obsoletos.  
  
 Considere el ejemplo siguiente:  
  
 ![Captura de pantalla de números primos](../../../../docs/framework/wpf/advanced/media/threadingprimenumberscreenshot.PNG "ThreadingPrimeNumberScreenShot")  
  
 Esta sencilla aplicación cuenta en orden ascendente a partir de tres, buscando números primos. Cuando el usuario hace clic en el **iniciar** botón, se inicia la búsqueda. Cuando el programa encuentra un número primo, actualiza la interfaz de usuario con su detección. En cualquier momento, el usuario puede detener la búsqueda.  
  
 Aunque es bastante simple, la búsqueda de números primos podría continuar para siempre, lo que presenta algunas dificultades.  Si se controla la búsqueda completa dentro del controlador de eventos click del botón, nunca se daría el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] una oportunidad para controlar otros eventos de subprocesos. El [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sería incapaz de responder a la entrada o proceso de mensajes. No se volvería a dibujar nunca y tampoco respondería a los clics de botón.  
  
 Se podría realizar la búsqueda de números primos en un subproceso independiente, pero entonces sería necesario solucionar problemas de sincronización. Con un enfoque de un único subproceso, se puede actualizar directamente la etiqueta que muestra el número primo mayor encontrado.  
  
 Si se interrumpe la tarea de cálculo en fragmentos manejables, podemos volver periódicamente a los <xref:System.Windows.Threading.Dispatcher> y procesar los eventos. Le podemos dar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oportunidad de volver a dibujar y procesar la entrada.  
  
 Es la mejor manera de dividir el tiempo de procesamiento entre el cálculo y el control de eventos administrar el cálculo de la <xref:System.Windows.Threading.Dispatcher>. Mediante el uso de la <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> método, podemos programar las comprobaciones de números primos en la misma cola que [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se extraen de los eventos. En el ejemplo, solamente se programa una comprobación de número primo cada vez. Una vez completada la comprobación de número primo, se programa la siguiente de manera inmediata. Esta comprobación sólo después continúa pendiente [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] han sido controlados o eventos.  
  
 ![Ilustración de la cola del distribuidor](../../../../docs/framework/wpf/advanced/media/threadingdispatcherqueue.PNG "ThreadingDispatcherQueue")  
  
 [!INCLUDE[TLA#tla_word](../../../../includes/tlasharptla-word-md.md)] realiza la revisión ortográfica mediante este mecanismo. Corrector ortográfico se realiza en segundo plano mediante el tiempo de inactividad de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. Echemos un vistazo al código.  
  
 En el ejemplo siguiente se muestra el XAML que crea la interfaz de usuario.  
  
 [!code-xaml[ThreadingPrimeNumbers#ThreadingPrimeNumberXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml#threadingprimenumberxaml)]  
  
 En el ejemplo siguiente se muestra el código subyacente.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumbercodebehind)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumbercodebehind)]  
  
 En el ejemplo siguiente se muestra el controlador de eventos para el <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberstartorstop)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberstartorstop)]  
  
 Además de actualizar el texto en el <xref:System.Windows.Controls.Button>, este controlador es responsable de programar la primera comprobación de número primo agregando un delegado para que la <xref:System.Windows.Threading.Dispatcher> cola. Algún día después de este controlador de eventos haya completado su trabajo, la <xref:System.Windows.Threading.Dispatcher> seleccionará este delegado para la ejecución.  
  
 Como mencionamos anteriormente, <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> es el <xref:System.Windows.Threading.Dispatcher> miembro que se usa para programar un delegado para la ejecución. En este caso, elegimos el <xref:System.Windows.Threading.DispatcherPriority.SystemIdle> prioridad. El <xref:System.Windows.Threading.Dispatcher> se ejecutará este delegado cuando no haya ningún evento importante por procesar. La capacidad de respuesta de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] es más importante que la comprobación de números. También se pasa un nuevo delegado que representa la rutina de comprobación de números.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberchecknextnumber)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberchecknextnumber)]  
  
 Este método comprueba si el siguiente número impar es primo. Si es primo, el método actualiza directamente el `bigPrime` <xref:System.Windows.Controls.TextBlock> para reflejar su detección. Se puede hacer porque el cálculo se está produciendo en el mismo subproceso que se ha usado para crear el componente. Si hubiéramos decidido utilizar un subproceso independiente para el cálculo, se tendría que usar un mecanismo de sincronización más complicado y ejecutar la actualización en el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. A continuación se mostrará esta situación.  
  
 Para el código fuente completo de este ejemplo, vea el [aplicación uniproceso con ejemplo de cálculo de ejecución prolongada](http://go.microsoft.com/fwlink/?LinkID=160038)  
  
<a name="weather_sim"></a>   
### <a name="handling-a-blocking-operation-with-a-background-thread"></a>Control de una operación de bloqueo con un subproceso en segundo plano  
 El control de operaciones de bloqueo en una aplicación gráfica puede ser difícil. No es recomendable llamar a métodos de bloqueo desde controladores de eventos, porque parecerá que la aplicación se inmoviliza. Podemos utilizar un subproceso independiente para administrar estas operaciones, pero cuando hayamos terminados, tenemos que sincronizar con el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subprocesos porque no podemos modificar directamente el [!INCLUDE[TLA2#tla_gui](../../../../includes/tla2sharptla-gui-md.md)] desde el subproceso de trabajo. Podemos usar <xref:System.Windows.Threading.Dispatcher.Invoke%2A> o <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> para insertar delegados en la <xref:System.Windows.Threading.Dispatcher> de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. Finalmente, estos delegados se ejecutarán con permiso para modificar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos.  
  
 En este ejemplo, se imita una llamada a procedimiento remoto que recupera la previsión meteorológica. Utilizamos un subproceso de trabajo independiente para ejecutar esta llamada y se programa un método de actualización en el <xref:System.Windows.Threading.Dispatcher> de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] una vez se haya terminado de subprocesos.  
  
 ![Captura de pantalla de UI de información meteorológica](../../../../docs/framework/wpf/advanced/media/threadingweatheruiscreenshot.PNG "ThreadingWeatherUIScreenShot")  
  
 [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweathercodebehind)]
 [!code-vb[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweathercodebehind)]  
  
 A continuación se enumeran algunos de los detalles para tener en cuenta.  
  
-   Creación del controlador del botón  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherbuttonhandler)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherbuttonhandler)]  
  
 Cuando se hace clic en el botón, se muestra el dibujo del reloj y se inicia su animación. Se deshabilita el botón. Invocamos el `FetchWeatherFromServer` método en un nuevo subproceso y, a continuación, return, lo que permite el <xref:System.Windows.Threading.Dispatcher> para procesar los eventos mientras se esperan para recopilar el boletín meteorológico.  
  
-   Captura de la información meteorológica  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherfetchweather)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherfetchweather)]  
  
 Para simplificar las cosas, en realidad en este ejemplo no hay ningún código de red. En su lugar, es posible simular el retraso de acceso de red haciendo que el nuevo subproceso espere durante cuatro segundos. En este momento, la versión original [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso se sigue ejecutando y responder a eventos. Para mostrarlo, se deja una animación en ejecución y los botones para minimizar y maximizar también siguen funcionando.  
  
 Cuando se completa el retraso y hemos seleccionado aleatoriamente nuestro boletín meteorológico, es el momento de informar a los [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. Hacer esto mediante la programación de una llamada a `UpdateUserInterface` en el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subprocesos con ese subproceso <xref:System.Windows.Threading.Dispatcher>. Se pasa una cadena que describe la información meteorológica a esta llamada de método programada.  
  
-   Actualizar el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherupdateui)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherupdateui)]  
  
 Cuando el <xref:System.Windows.Threading.Dispatcher> en el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso tiene tiempo, ejecuta la llamada programada a `UpdateUserInterface`. Este método detiene la animación del reloj y elige una imagen que describa la información meteorológica. Muestra esta imagen y restaura el botón para "obtener la información meteorológica".  
  
<a name="multi_browser"></a>   
### <a name="multiple-windows-multiple-threads"></a>Varias ventanas, varios subprocesos  
 Algunos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones requieren varias ventanas de nivel superior. Es perfectamente aceptable para un subproceso /<xref:System.Windows.Threading.Dispatcher> combinación para administrar varias ventanas, pero en ocasiones, varios subprocesos hacer un mejor trabajo. Esto es especialmente cierto si hay alguna posibilidad de que una de las ventanas monopolice el subproceso.  
  
 El Explorador de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] funciona de esta manera. Cada nueva ventana del Explorador pertenece al proceso original, pero se crea bajo el control de un subproceso independiente.  
  
 Mediante el uso de un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Frame> (control), podemos mostrar páginas Web. Podemos crear fácilmente una sencilla [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] sustituir. Comenzamos con una característica importante: la capacidad de abrir una nueva ventana del explorador. Cuando el usuario hace clic en el botón "Nueva ventana", se inicia una copia de nuestra ventana en un subproceso independiente. De este modo, las operaciones de ejecución prolongada o de bloqueo en una de las ventanas no bloquearán a todas las demás.  
  
 En realidad, el modelo de explorador web tiene su propio modelo complicado de subprocesos. Lo elegimos porque debería resultar conocido para la mayoría de los lectores.  
  
 En el ejemplo siguiente se muestra el código.  
  
 [!code-xaml[ThreadingMultipleBrowsers#ThreadingMultiBrowserXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml#threadingmultibrowserxaml)]  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsercodebehind)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsercodebehind)]  
  
 Los siguientes segmentos de subprocesos de este código son los que más nos interesan en este contexto:  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsernewwindow)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsernewwindow)]  
  
 Este método se llama cuando se hace clic en el botón "Nueva ventana". Crea un nuevo subproceso y lo inicia de forma asincrónica.  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowserthreadstart)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowserthreadstart)]  
  
 Este método es el punto de partida para el nuevo subproceso. Se crea una nueva ventana bajo el control de este subproceso. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea automáticamente un nuevo <xref:System.Windows.Threading.Dispatcher> para administrar el nuevo subproceso. Todo lo que hay que hacer para que la ventana funcional consiste en iniciar el <xref:System.Windows.Threading.Dispatcher>.  
  
<a name="stumbling_points"></a>   
## <a name="technical-details-and-stumbling-points"></a>Detalles técnicos y puntos problemáticos  
  
### <a name="writing-components-using-threading"></a>Escribir componentes mediante subprocesos  
 Guía de Microsoft .NET Framework Developer describe un patrón de cómo un componente puede exponer comportamiento asincrónico a sus clientes (vea [Event-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)). Por ejemplo, supongamos que deseamos empaquetar el `FetchWeatherFromServer` método en un componente reutilizable, no gráfico. Siguiendo el patrón estándar de Microsoft .NET Framework, esto sería algo parecido a lo siguiente.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent1)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent1)]  
  
 `GetWeatherAsync` usaría una de las técnicas descritas anteriormente, como la creación de un subproceso en segundo plano, para hacer el trabajo de forma asincrónica, sin bloquear el subproceso de llamada.  
  
 Una de las partes más importantes de este patrón es llamar a la *MethodName* `Completed` método en el mismo subproceso que llamó la *MethodName* `Async` que comience con método. Puede hacerlo mediante [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bastante fácilmente, almacenando <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>: pero, a continuación, el componente no gráficos solo se puede usar en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones, no en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)] programas.  
  
 El <xref:System.Windows.Threading.DispatcherSynchronizationContext> clase satisface esta necesidad, considérelo como una versión simplificada de <xref:System.Windows.Threading.Dispatcher> que funciona con otras [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] también marcos de trabajo.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent2)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent2)]  
  
### <a name="nested-pumping"></a>Bombeo anidado  
 A veces no es posible bloquear completamente la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. Veamos el <xref:System.Windows.MessageBox.Show%2A> método de la <xref:System.Windows.MessageBox> clase. <xref:System.Windows.MessageBox.Show%2A> no vuelve hasta que el usuario hace clic en el botón Aceptar. Pero crea una ventana que debe tener un bucle de mensajes para poder ser interactiva. Mientras se espera a que el usuario haga clic en Aceptar, la ventana de la aplicación original no responde a la entrada del usuario. Pero sigue procesando los mensajes de pintura. La ventana original se vuelve a dibujar cuando se oculta y se muestra.  
  
 ![MessageBox con un botón "Aceptar"](../../../../docs/framework/wpf/advanced/media/threadingnestedpumping.png "ThreadingNestedPumping")  
  
 Algún subproceso debe estar a cargo de la ventana del cuadro de mensaje. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] podría crear un nuevo subproceso para la ventana del cuadro de mensaje, pero este subproceso no podría representar los elementos deshabilitados en la ventana original (recuerde la explicación anterior sobre la exclusión mutua). En su lugar, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza un sistema de procesamiento de mensajes anidados. El <xref:System.Windows.Threading.Dispatcher> clase incluye un método especial denominado <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>, que almacena el punto de ejecución actual de la aplicación, a continuación, comienza un nuevo bucle de mensajes. Cuando finalice el bucle de mensajes anidados, la ejecución se reanuda después de la versión original <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> llamar.  
  
 En este caso, <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> mantiene el contexto del programa en la llamada a <xref:System.Windows.MessageBox>.<xref:System.Windows.MessageBox.Show%2A>, y se inicia un nuevo bucle de mensajes para volver a dibujar la ventana de fondo y controlar los datos proporcionados a la ventana de cuadro de mensaje. Cuando el usuario hace clic en Aceptar y borra la ventana emergente, sale del bucle anidado y se reanuda el control después de llamar a <xref:System.Windows.MessageBox.Show%2A>.  
  
### <a name="stale-routed-events"></a>Eventos enrutados obsoletos  
 El sistema de eventos enrutados en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] notifica a todos los árboles cuando se producen eventos.  
  
 [!code-xaml[InputOvw#ThreadingArticleStaticRoutedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#threadingarticlestaticroutedevent)]  
  
 Cuando se presiona el botón primario del mouse sobre la elipse, `handler2` se ejecuta. Después de `handler2` finaliza, el evento se pasa a la <xref:System.Windows.Controls.Canvas> objeto, que utiliza `handler1` para procesarlo. Esto solo sucede si `handler2` does explícitamente no marca el objeto de evento, como controlado.  
  
 Es posible que `handler2` tendrá una gran cantidad de tiempo de procesamiento de este evento. `handler2` Puede usar <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> para iniciar un bucle de mensajes anidados que no devuelve durante horas. Si `handler2` no no marca el evento como controlado cuando este bucle de mensajes se complete, el evento se pasa el árbol, aunque es muy antigua.  
  
### <a name="reentrancy-and-locking"></a>Reentrada y bloqueo  
 El mecanismo de bloqueo de la [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] no se comporta exactamente como se podría imaginar; se podría esperar que un subproceso para dejar de operación completamente cuando se solicita un bloqueo. En realidad, el subproceso continúa recibiendo y procesando mensajes de alta prioridad. Esto ayuda a evitar interbloqueos y a que la capacidad de respuesta de las interfaces sea mínima, pero introduce la posibilidad de errores sutiles.  La mayoría de las veces no es necesario saber nada sobre esto, pero, en algunas circunstancias poco frecuentes (normalmente relativos a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] mensajes de ventana o a los componentes COM STA) puede ser conveniente conocer.  
  
 Mayoría de las interfaces no se compila con la seguridad para subprocesos en cuenta porque los programadores que trabajan en la suposición de que un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nunca se tiene acceso con más de un subproceso. En este caso, que el único subproceso puede realizar cambios en el entorno en momentos inesperados, produciendo esos mal efectos que el <xref:System.Windows.Threading.DispatcherObject> el mecanismo de exclusión mutua se supone que para resolver. Considere el siguiente seudocódigo:  
  
 ![Diagrama de reentrada de subprocesos](../../../../docs/framework/wpf/advanced/media/threadingreentrancy.png "ThreadingReentrancy")  
  
 La mayoría de las veces que es lo correcto, pero hay ocasiones en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] donde tal reentrada inesperada realmente puede causar problemas. Así, en determinados momentos claves, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llamadas <xref:System.Windows.Threading.Dispatcher.DisableProcessing%2A>, que cambia la instrucción de bloqueo para el subproceso que se usará el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bloqueo libre de reentrada, en lugar de la habitual [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] bloqueo.  
  
 ¿Por qué hizo el [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] equipo elegir este comportamiento? Tenía que ver con los objetos COM STA y el subproceso de finalización. Si un objeto se han recopilado, su `Finalize` método se ejecuta en el subproceso finalizador dedicado, no el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. Y en él se encuentra el problema, porque un STA COM del objeto que se creó en el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sólo se pueden desechar los subprocesos en la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso. El [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] realiza el equivalente de un <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> (en este caso con de Win32 `SendMessage`). Pero si el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] subproceso está ocupado, el subproceso finalizador se ha detenido y no se puede desechar el objeto COM STA, que crea una pérdida grave de memoria. Por lo que la [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] equipo tomó esta decisión para realizar bloqueos funcionan de la forma lo hacen.  
  
 La tarea para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste en evitar la reentrada inesperada sin Introducción a la pérdida de memoria, que es el motivo por el que no bloqueamos de reentrada en cualquier lugar.  
  
## <a name="see-also"></a>Vea también  
 [Single-Threaded Application with Long-Running Calculation Sample](http://go.microsoft.com/fwlink/?LinkID=160038) (Ejemplo de aplicación de un único subproceso con un cálculo de ejecución prolongada)
