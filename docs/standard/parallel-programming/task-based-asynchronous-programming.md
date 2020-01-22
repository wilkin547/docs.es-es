---
title: 'Programación asincrónica basada en tareas: .NET'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallelism, task
ms.assetid: 458b5e69-5210-45e5-bc44-3888f86abd6f
ms.openlocfilehash: 51292d977f2be87cec7c3481f5004fe5fe756224
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204543"
---
# <a name="task-based-asynchronous-programming"></a>Programación asincrónica basada en tareas

La biblioteca TPL se basa en el concepto de *tarea*, que representa una operación asincrónica. De cierta forma, una tarea recuerda a un subproceso o elemento de trabajo <xref:System.Threading.ThreadPool>, pero en un nivel más alto de abstracción. El término *paralelismo de tareas* hace referencia a la ejecución simultánea de una o varias tareas independientes. Las tareas proporcionan dos ventajas fundamentales:

- Un uso más eficaz y más escalable de los recursos del sistema.

     En segundo plano, las tareas se ponen en la cola del elemento <xref:System.Threading.ThreadPool>, que se ha mejorado con algoritmos que determinan y ajustan el número de subprocesos y que ofrecen el equilibrio de carga para maximizar el rendimiento. Esto hace que las tareas resulten relativamente ligeras y que, por tanto, pueda crearse un gran número de ellas para habilitar un paralelismo pormenorizado.

- Un mayor control mediante programación del que se puede conseguir con un subproceso o un elemento de trabajo.

     Las tareas y el marco que se crea en torno a ellas proporcionan un amplio conjunto de API que admiten el uso de esperas, cancelaciones, continuaciones, control robusto de excepciones, estado detallado, programación personalizada, y más.

Por estos dos motivos, en .NET Framework, TPL es la API preferida para escribir código multiproceso, asincrónico y paralelo.

## <a name="creating-and-running-tasks-implicitly"></a>Crear y ejecutar tareas implícitamente

El método <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> proporciona una manera conveniente de ejecutar cualquier número de instrucciones arbitrarias simultáneamente. Pase un delegado <xref:System.Action> por cada elemento de trabajo. La manera más fácil de crear estos delegados es con expresiones lambda. La expresión lambda puede llamar a un método con nombre o proporcionar el código alineado. En el siguiente ejemplo se muestra una llamada a <xref:System.Threading.Tasks.Parallel.Invoke%2A> básica que crea e inicia dos tareas que se ejecutan a la vez. La primera tarea se representa mediante una expresión lambda que llama a un método denominado `DoSomeWork` y la segunda tarea se representa mediante una expresión lambda que llama a un método denominado `DoSomeOtherWork`.

> [!NOTE]
> En esta documentación, se utilizan expresiones lambda para definir delegados en la TPL. Si no está familiarizado con las expresiones lambda de C# o Visual Basic, consulte [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md) (Expresiones lambda en PLINQ y TPL).

[!code-csharp[TPL#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#21)]
[!code-vb[TPL#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/tpl_vb.vb#21)]

> [!NOTE]
> El número de instancias de <xref:System.Threading.Tasks.Task> que <xref:System.Threading.Tasks.Parallel.Invoke%2A> crea en segundo plano no es necesariamente igual al número de delegados que se proporcionan. La TPL puede emplear varias optimizaciones, sobre todo con grandes números de delegados.

Para obtener más información, vea [Cómo: Usar Parallel.Invoke para ejecutar operaciones en paralelo](../../../docs/standard/parallel-programming/how-to-use-parallel-invoke-to-execute-parallel-operations.md).

Para tener un mayor control de la ejecución de tareas o para devolver un valor de la tarea, debe trabajar con objetos <xref:System.Threading.Tasks.Task> más explícitamente.

## <a name="creating-and-running-tasks-explicitly"></a>Crear y ejecutar tareas explícitamente

Una tarea que no devuelve un valor se representa mediante la clase <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> . Una tarea que devuelve un valor se representa mediante la clase <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>, que se hereda de <xref:System.Threading.Tasks.Task>. El objeto de tarea controla los detalles de la infraestructura y proporciona métodos y propiedades a los que se puede obtener acceso desde el subproceso que realiza la llamada a lo largo de la duración de la tarea. Por ejemplo, se puede tener acceso a la propiedad <xref:System.Threading.Tasks.Task.Status%2A> de una tarea en cualquier momento para determinar si ha empezado a ejecutarse, si se ha ejecutado hasta su finalización, si se ha cancelado o si se ha producido una excepción. El estado se representa mediante la enumeración <xref:System.Threading.Tasks.TaskStatus>.

Cuando se crea una tarea, se proporciona un delegado de usuario que encapsula el código que la tarea va a ejecutar. El delegado se puede expresar como un delegado con nombre, un método anónimo o una expresión lambda. Las expresiones lambda pueden contener una llamada a un método con nombre, tal y como se muestra en el siguiente ejemplo. Observe que el ejemplo incluye una llamada al método <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> para garantizar que la ejecución de la tarea se complete antes de que finalice la aplicación de modo de consola.

[!code-csharp[TPL_TaskIntro#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/lambda1.cs#1)]
[!code-vb[TPL_TaskIntro#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/lambda1.vb#1)]

También se pueden usar los métodos <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> para crear e iniciar una tarea en una sola operación. Para administrar la tarea, los métodos <xref:System.Threading.Tasks.Task.Run%2A> usan el programador de tareas predeterminado, independientemente qué programador de tareas esté asociado al subproceso actual. Los métodos <xref:System.Threading.Tasks.Task.Run%2A> son el modo preferido para crear e iniciar tareas cuando no se necesita más control sobre la creación y la programación de la tarea.

[!code-csharp[TPL_TaskIntro#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/run1.cs#2)]
[!code-vb[TPL_TaskIntro#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/run1.vb#2)]

También se puede usar el método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> para crear e iniciar una tarea en una sola operación. Utilice este método cuando la creación y la programación no tengan que ser independientes y necesite opciones de creación de tareas adicionales o el uso de un programador concreto, o cuando necesita pasar información de estado adicional en la tarea que se puede recuperar mediante su propiedad <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente.

[!code-csharp[TPL_TaskIntro#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/asyncstate.cs#23)]
[!code-vb[TPL_TaskIntro#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/asyncstate.vb#23)]

<xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> exponen en cada caso una propiedad <xref:System.Threading.Tasks.Task.Factory%2A> estática que devuelve una instancia predeterminada de <xref:System.Threading.Tasks.TaskFactory>, por lo que se puede llamar al método como `Task.Factory.StartNew()`. Asimismo, en el siguiente ejemplo, dado que las tareas son de tipo <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>, cada una tiene una propiedad <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType> pública que contiene el resultado del cálculo. Las tareas se ejecutan de forma asincrónica y pueden completarse en cualquier orden. Si se obtiene acceso a la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A> antes de que el cálculo se complete, la propiedad bloqueará el subproceso hasta que el valor esté disponible.

[!code-csharp[TPL_TaskIntro#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/result1.cs#4)]
[!code-vb[TPL_TaskIntro#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/result1.vb#4)]

Para obtener más información, vea [Cómo: Devolver un valor a partir de una tarea](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md).

Cuando se usa una expresión lambda para crear un delegado, se obtiene acceso a todas las variables que están visibles en ese momento en el código fuente. Sin embargo, en algunos casos, sobre todo en los bucles, una expresión lambda no captura la variable como cabría esperar. Captura solo el valor final, no el valor tal y como se transforma después de cada iteración. En el siguiente ejemplo se ilustra el problema. Pasa un contador de bucle a una expresión lambda que crea instancias de un objeto `CustomData` y usa el contador de bucle como identificador del objeto. Como muestra la salida del ejemplo, cada objeto `CustomData` tiene un identificador idéntico.

[!code-csharp[TPL_TaskIntro#22](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/iteration1b.cs#22)]
[!code-vb[TPL_TaskIntro#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/iteration1b.vb#22)]

Puede obtener acceso al valor en cada iteración si proporciona un objeto de estado a una tarea a través de su constructor. En el ejemplo siguiente se modifica el ejemplo anterior utilizando el contador de bucle al crear el objeto `CustomData` que, a su vez, se pasa a la expresión lambda.  Como muestra el resultado del ejemplo, cada objeto `CustomData` tiene ahora un identificador único basado en el valor del contador de bucle cuando se creó la instancia del objeto.

[!code-csharp[TPL_TaskIntro#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/iteration1a.cs#21)]
[!code-vb[TPL_TaskIntro#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/iteration1a.vb#21)]

Este estado se pasa como argumento al delegado de la tarea y permite tener acceso desde el objeto de tarea mediante la propiedad <xref:System.Threading.Tasks.Task.AsyncState%2A?displayProperty=nameWithType>.  El ejemplo siguiente es una variación del ejemplo anterior. Utiliza la propiedad <xref:System.Threading.Tasks.Task.AsyncState%2A> para mostrar información sobre los objetos `CustomData` pasados a la expresión lambda.

[!code-csharp[TPL_TaskIntro#23](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/asyncstate.cs#23)]
[!code-vb[TPL_TaskIntro#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/asyncstate.vb#23)]

## <a name="task-id"></a>Identificador de tarea

Cada tarea recibe un identificador entero que la identifica de manera inequívoca en un dominio de aplicación y al que se puede obtener acceso mediante la propiedad <xref:System.Threading.Tasks.Task.Id%2A?displayProperty=nameWithType>. El identificador resulta útil para ver información sobre la tarea en las ventanas **Pilas paralelas** y **Tareas** del depurador de Visual Studio. El identificador se crea de forma diferida, lo que significa que no se crea hasta que se solicita; por tanto, una tarea podrá tener un identificador diferente cada vez que se ejecute el programa. Para más información sobre cómo ver los identificadores de tarea en el depurador, consulte [Usar la ventana Tareas](/visualstudio/debugger/using-the-tasks-window) y [Usar la ventana Pilas paralelas](/visualstudio/debugger/using-the-parallel-stacks-window).

## <a name="task-creation-options"></a>Opciones de creación de tareas

La mayoría de las API que crean tareas proporcionan sobrecargas que aceptan un parámetro <xref:System.Threading.Tasks.TaskCreationOptions>. Al especificar una de estas opciones, se le está indicando al programador cómo se programa la tarea en el grupo de subprocesos. En la tabla siguiente se muestran las diversas opciones de creación de tareas.

|<xref:System.Threading.Tasks.TaskCreationOptions> valor de parámetro|DESCRIPCIÓN|
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|
|<xref:System.Threading.Tasks.TaskCreationOptions.None>|Es la opción predeterminada si no se especifica ninguna opción. El programador usa su heurística predeterminada para programar la tarea.|
|<xref:System.Threading.Tasks.TaskCreationOptions.PreferFairness>|Especifica que la tarea debe programarse de modo que las tareas creadas anteriormente tengan más posibilidades de ejecutarse antes y que las tareas posteriormente tengan más posibilidades de ejecutarse después.|
|<xref:System.Threading.Tasks.TaskCreationOptions.LongRunning>|Especifica que la tarea representa una operación de ejecución prolongada.|
|<xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent>|Especifica que una tarea debe crearse como un elemento secundario asociado de la tarea actual, si existe. Para más información, consulte [Attached and Detached Child Tasks](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md) (Tareas secundarias asociadas y desasociadas).|
|<xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach>|Especifica que, si una tarea interna especifica la opción `AttachedToParent`, esa tarea no se convertirá en una tarea secundaria asociada.|
|<xref:System.Threading.Tasks.TaskCreationOptions.HideScheduler>|Especifica que el programador de tareas para tareas creadas llamando a métodos como <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> o <xref:System.Threading.Tasks.Task%601.ContinueWith%2A?displayProperty=nameWithType> desde dentro de una tarea determinada es el programador predeterminado en lugar del programador en el que se ejecuta esta tarea.|

Las opciones pueden combinarse con una operación **OR**. En el ejemplo siguiente se muestra una tarea que tiene las opciones <xref:System.Threading.Tasks.TaskCreationOptions.LongRunning> y <xref:System.Threading.Tasks.TaskContinuationOptions.PreferFairness>.

[!code-csharp[TPL_TaskIntro#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/taskintro.cs#03)]
[!code-vb[TPL_TaskIntro#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/tpl_intro.vb#03)]

## <a name="tasks-threads-and-culture"></a>Tareas, subprocesos y referencia cultural

Cada subproceso tiene asociada una referencia cultural asociada y una interfaz de usuario de referencia cultural, que está definida por las propiedades <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> y <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType>, respectivamente. La referencia cultural de un subproceso se usa en operaciones como dar formato, analizar, ordenar y comparar cadenas. La referencia cultural de la interfaz de usuario de un subproceso se usa en la búsqueda de recursos. Por lo general, a menos que especifique una referencia cultural predeterminada para todos los subprocesos de un dominio de aplicación usando las propiedades <xref:System.Globalization.CultureInfo.DefaultThreadCurrentCulture%2A?displayProperty=nameWithType> y <xref:System.Globalization.CultureInfo.DefaultThreadCurrentUICulture%2A?displayProperty=nameWithType>, la referencia cultural del sistema define la referencia cultural predeterminada y la referencia cultural de la interfaz de usuario de un subproceso. Si establece explícitamente la referencia cultural de un subproceso e inicia un nuevo subproceso, el nuevo subproceso no hereda la referencia cultural del subproceso que realiza la llamada; en su lugar, su referencia cultural es la referencia cultural predeterminada del sistema. El modelo de programación basado en tareas para las aplicaciones destinadas a versiones de .NET Framework anteriores a .NET Framework 4.6 siguen este procedimiento.

> [!IMPORTANT]
> Tenga en cuenta que la referencia cultural del subproceso que realiza la llamada como parte del contexto de una tarea se aplica a las aplicaciones *destinadas* a .NET Framework 4.6, no a las que *se ejecutan* en .NET Framework 4.6. Puede elegir como destino una versión determinada de .NET Framework al crear el proyecto en Visual Studio seleccionado esta versión en la lista desplegable situada en la parte superior del cuadro de diálogo **Nuevo proyecto** o fuera de Visual Studio puede usar el atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute>. Para las aplicaciones destinadas a versiones de .NET Framework anteriores a .NET Framework 4.6 o que no están destinadas a una versión específica de .NET Framework, la referencia cultural del subproceso en el que se ejecuta sigue determinando la referencia cultural de la tarea.

A partir de las aplicaciones destinadas a .NET Framework 4.6, cada tarea hereda la referencia cultural del subproceso que realiza la llamada, aunque la tarea se ejecute de forma asincrónica en un subproceso del grupo de subprocesos.

Esto se muestra en el ejemplo siguiente. Usa el atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute> para elegir .NET Framework 4.6 como destino y cambia la referencia cultural actual de la aplicación a francés (Francia) o, si francés (Francia) es la referencia cultural actual, a inglés (Estados Unidos). Después, invoca un delegado llamado `formatDelegate` que devuelve algunos números con el formato de valores de moneda de la nueva referencia cultural. Tenga en cuenta si el delegado se ejecuta como una tarea tanto de forma sincrónica como asincrónica, devuelve el resultado esperado porque la tarea asincrónica hereda la referencia cultural del subproceso que realiza la llamada.

[!code-csharp[System.Globalization.CultureInfo.Class.Async#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.globalization.cultureinfo.class.async/cs/asyncculture1.cs#5)]
[!code-vb[System.Globalization.CultureInfo.Class.Async#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.globalization.cultureinfo.class.async/vb/asyncculture1.vb#5)]

Si utiliza Visual Studio, puede omitir el atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute> y seleccionar en su lugar .NET Framework 4.6 como destino al crear el proyecto en el cuadro de diálogo **Nuevo proyecto**.

Para que la salida refleje el comportamiento de las aplicaciones destinadas a versiones de .NET Framework anteriores a .NET Framework 4.6, quite el atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute> del código fuente. La salida reflejará las convenciones de formato de la referencia cultural predeterminada del sistema, no la referencia cultural del subproceso que realiza la llamada.

Para obtener más información sobre las tareas asincrónicas y la referencia cultural, consulte la sección "Referencia cultural y operaciones asincrónicas basadas en tareas" en el tema <xref:System.Globalization.CultureInfo>.

## <a name="creating-task-continuations"></a>Crear continuaciones de tareas

Los métodos <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task%601.ContinueWith%2A?displayProperty=nameWithType> permiten especificar una tarea que se iniciará cuando finalice la *tarea anterior*. Al delegado de la tarea de continuación se le pasa una referencia a la tarea antecedente para que pueda examinar el estado de dicha tarea y, al recuperar el valor de la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>, puede usar la salida del antecedente como entrada de la continuación.

En el ejemplo siguiente, la tarea `getData` se inicia llamando al método <xref:System.Threading.Tasks.TaskFactory.StartNew%60%601%28System.Func%7B%60%600%7D%29?displayProperty=nameWithType>. La tarea `processData` se inicia automáticamente cuando finaliza `getData` y `displayData` se inicia cuando finaliza `processData`. `getData` genera una matriz de enteros, accesible a la tarea `processData` mediante la propiedad `getData` de la tarea <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>. La tarea `processData` procesa dicha matriz y devuelve un resultado cuyo tipo se deduce del tipo de valor devuelto de la expresión lambda pasada al método <xref:System.Threading.Tasks.Task%601.ContinueWith%60%601%28System.Func%7BSystem.Threading.Tasks.Task%7B%600%7D%2C%60%600%7D%29?displayProperty=nameWithType>. La tarea `displayData` se ejecuta automáticamente cuando finaliza `processData` y el objeto <xref:System.Tuple%603> devuelto por la expresión lambda `processData` es accesible para la tarea `displayData` mediante la propiedad `processData` de la tarea <xref:System.Threading.Tasks.Task%601.Result%2A?displayProperty=nameWithType>. La tarea `displayData` toma el resultado de la tarea `processData` y genera un resultado cuyo tipo se deduce de forma similar y que se pone a disposición del programa en la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A>.

[!code-csharp[TPL_TaskIntro#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/continuations1.cs#5)]
[!code-vb[TPL_TaskIntro#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/continuations1.vb#5)]

Dado que <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType> es un método de instancia, puede encadenar llamadas a métodos en lugar de crear instancias de un objeto <xref:System.Threading.Tasks.Task%601> para cada tarea antecedente. El ejemplo siguiente es funcionalmente idéntico al anterior, con la diferencia de que encadena llamadas al método <xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>. Observe que el objeto <xref:System.Threading.Tasks.Task%601> devuelto por la cadena de llamadas al método es la tarea final de continuación.

[!code-csharp[TPL_TaskIntro#24](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/continuations2.cs#24)]
[!code-vb[TPL_TaskIntro#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/continuations2.vb#24)]

Los métodos <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A> y <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A> permiten continuar a partir de varias tareas.

Para más información, consulte [Encadenar tareas mediante tareas de continuación](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).

## <a name="creating-detached-child-tasks"></a>Crear tareas secundarias desasociadas

Cuando el código de usuario que se está ejecutando en una tarea crea una nueva tarea y no especifica la opción <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent>, la nueva tarea no se sincroniza con la tarea principal de ninguna manera especial. Este tipo de tarea no sincronizada se denomina *tarea anidada desasociada* o *tarea secundaria desasociada*. En el siguiente ejemplo se muestra una tarea que crea una tarea secundaria desasociada.

[!code-csharp[TPL_TaskIntro#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/taskintro.cs#07)]
[!code-vb[TPL_TaskIntro#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/tpl_intro.vb#07)]

Observe que la tarea primaria no espera a que la tarea secundaria desasociada se complete.

## <a name="creating-child-tasks"></a>Crear tareas secundarias

Cuando el código de usuario que se está ejecutando en una tarea crea una tarea con la opción <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent>, la nueva tarea se conoce como una *tarea secundaria asociada* de la tarea principal. Puede usar la opción <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> para expresar el paralelismo de tareas estructurado, ya que la tarea primaria espera implícitamente a que todas las tareas secundarias asociadas finalicen. En el ejemplo siguiente se muestra una tarea principal que crea diez tareas secundarias adjuntas. Observe que aunque en el ejemplo se llame al método <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> para esperar a que la tarea primaria finalice, no tiene que esperar explícitamente a que se completen las tareas secundarias asociadas.

[!code-csharp[TPL_TaskIntro#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/child1.cs#8)]
[!code-vb[TPL_TaskIntro#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/child1.vb#8)]

Una tarea principal puede usar la opción <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> para evitar que otras tareas se asocien a la tarea primaria. Para más información, consulte [Attached and Detached Child Tasks](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md) (Tareas secundarias asociadas y desasociadas).

## <a name="waiting-for-tasks-to-finish"></a>Esperar hasta que las tareas finalicen

Los tipos <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> proporcionan varias sobrecargas de los métodos <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> que permiten esperar a que finalice una tarea. Además, las sobrecargas del método <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> estático y del método <xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType> permiten esperar a que finalicen alguna o todas las tareas de una matriz de tareas.

Normalmente, una tarea se espera por una de estas razones:

- El subproceso principal depende del resultado final que se calcula mediante una tarea.

- Hay que controlar las excepciones que pueden producirse en la tarea.

- La aplicación puede finalizar antes de que todas las tareas hayan terminado de ejecutarse. Por ejemplo, las aplicaciones de consola finalizarán en cuanto se ejecute todo el código sincrónico en `Main` (el punto de entrada de la aplicación).

En el siguiente ejemplo se muestra el modelo básico donde el control de excepciones no está implicado.

[!code-csharp[TPL_TaskIntro#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_taskintro/cs/taskintro.cs#06)]
[!code-vb[TPL_TaskIntro#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_taskintro/vb/tpl_intro.vb#06)]

Para un ejemplo que muestra el control de excepciones, consulte [Control de excepciones](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md).

Algunas sobrecargas permiten especificar un tiempo de espera, mientras que otras toman un objeto <xref:System.Threading.CancellationToken> adicional como parámetro de entrada, de modo que la espera puede cancelarse mediante programación o en respuesta a los datos proporcionados por el usuario.

Cuando se espera a una tarea, se espera implícitamente a todos los elementos secundarios de esa tarea que se crearon con la opción <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType>. <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> devuelve un valor inmediatamente si la tarea ya se ha completado. Un método <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> producirá las tareas generadas por una tarea incluso si se llama a este método <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> una vez completada la tarea.

## <a name="composing-tasks"></a>Componer tareas

Las clases <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> proporcionan varios métodos que pueden ayudar a componer varias tareas para implementar patrones comunes y para mejorar el uso de las características de lenguaje asincrónicas proporcionadas por C#, Visual Basic y F#. En esta sección se describen los métodos <xref:System.Threading.Tasks.Task.WhenAll%2A>, <xref:System.Threading.Tasks.Task.WhenAny%2A>, <xref:System.Threading.Tasks.Task.Delay%2A> y <xref:System.Threading.Tasks.Task.FromResult%2A>.

### <a name="taskwhenall"></a>Task.WhenAll

El método <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> espera de forma asincrónica a que finalicen varios <xref:System.Threading.Tasks.Task> objetos <xref:System.Threading.Tasks.Task%601>. Proporciona versiones sobrecargadas que permiten esperar a conjuntos no uniformes de tareas. Por ejemplo, puede esperar a que varios objetos <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> se completen de una llamada al método.

### <a name="taskwhenany"></a>Task.WhenAny

El método <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType> espera de forma asincrónica a que finalice uno de varios <xref:System.Threading.Tasks.Task> objetos <xref:System.Threading.Tasks.Task%601>. Como en el método <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>, este método proporciona versiones sobrecargadas que permiten esperar a conjuntos no uniformes de tareas. El método <xref:System.Threading.Tasks.Task.WhenAny%2A> es especialmente útil en los siguientes escenarios.

- Operaciones redundantes. Considere un algoritmo o una operación que pueda realizarse de muchas maneras. Puede usar el método <xref:System.Threading.Tasks.Task.WhenAny%2A> para seleccionar la operación que finaliza primero y luego cancelar las operaciones restantes.

- Operaciones intercaladas. Puede iniciar varias operaciones, todas las cuales deben finalizar y utilizar el método <xref:System.Threading.Tasks.Task.WhenAny%2A> para procesar los resultados cuando finalice cada operación. Finalizada una operación, puede iniciar una o más tareas adicionales.

- Operaciones limitadas. Puede usar el método <xref:System.Threading.Tasks.Task.WhenAny%2A> para extender el escenario anterior limitando el número de operaciones simultáneas.

- Operaciones que han expirado. Puede usar el método <xref:System.Threading.Tasks.Task.WhenAny%2A> para seleccionar entre una o más tareas y una tarea que termina después de un tiempo concreto, como una tarea devuelta por el método <xref:System.Threading.Tasks.Task.Delay%2A>. El método <xref:System.Threading.Tasks.Task.Delay%2A> se describe en la sección siguiente.

### <a name="taskdelay"></a>Task.Delay

El método <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> produce un objeto <xref:System.Threading.Tasks.Task> que finaliza tras el tiempo especificado. Puede usar este método para crear bucles que sondeen ocasionalmente en busca de datos, introduzcan finales de tiempo de espera, retrasen el control de los datos proporcionados por el usuario durante un tiempo predeterminado, etc.

### <a name="tasktfromresult"></a>Task(T).FromResult

Mediante el método <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType>, puede crear un objeto <xref:System.Threading.Tasks.Task%601> que contenga un resultado previamente calculado. Este método es útil cuando se realiza una operación asincrónica que devuelve un objeto <xref:System.Threading.Tasks.Task%601> y el resultado de ese objeto <xref:System.Threading.Tasks.Task%601> ya se ha calculado. Para obtener un ejemplo en el que se usa <xref:System.Threading.Tasks.Task.FromResult%2A> para recuperar los resultados de las operaciones de descarga asincrónica que se retienen en caché, vea [Procedimiento para crear tareas precalculadas](../../../docs/standard/parallel-programming/how-to-create-pre-computed-tasks.md).

## <a name="handling-exceptions-in-tasks"></a>Controlar excepciones en tareas

Cuando una tarea produce una o más excepciones, las excepciones se encapsulan en una excepción <xref:System.AggregateException>. Esa excepción se propaga de nuevo al subproceso que se combina con la tarea, que normalmente es el subproceso que está esperando a que la tarea termine o al subproceso que tiene acceso a la propiedad <xref:System.Threading.Tasks.Task%601.Result%2A>. Este comportamiento sirve para aplicar la directiva de .NET Framework por la que, de manera predeterminada, todas las excepciones no controladas deben terminar el proceso. El código de llamada puede controlar las excepciones con cualquiera de los siguientes elementos del bloque `try`/`catch`:

- El método <xref:System.Threading.Tasks.Task.Wait%2A>

- El método <xref:System.Threading.Tasks.Task.WaitAll%2A>

- El método <xref:System.Threading.Tasks.Task.WaitAny%2A>

- La propiedad <xref:System.Threading.Tasks.Task%601.Result%2A>

El subproceso de unión también puede controlar excepciones; para ello, obtiene acceso a la propiedad <xref:System.Threading.Tasks.Task.Exception%2A> antes de que la tarea se recolecte como elemento no utilizado. Al obtener acceso a esta propiedad, impide que la excepción no controlada desencadene el comportamiento de propagación de la excepción que termina el proceso cuando el objeto ha finalizado.

Para más información sobre las excepciones y las tareas, consulte [Control de excepciones](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md).

## <a name="canceling-tasks"></a>Cancelar tareas

La clase <xref:System.Threading.Tasks.Task> admite la cancelación cooperativa y está completamente integrada con las clases <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> y <xref:System.Threading.CancellationToken?displayProperty=nameWithType>, que se presentaron en .NET Framework versión 4. Muchos de los constructores de la clase <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> toman un objeto <xref:System.Threading.CancellationToken> como parámetro de entrada. Muchas de las sobrecargas de <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> y <xref:System.Threading.Tasks.Task.Run%2A> incluyen también un parámetro <xref:System.Threading.CancellationToken>.

Puede crear el token y emitir la solicitud de cancelación posteriormente usando la clase <xref:System.Threading.CancellationTokenSource>. A continuación, debe pasar el token a <xref:System.Threading.Tasks.Task> como argumento y hacer referencia al mismo token también en el delegado de usuario, que se encarga de responder a una solicitud de cancelación.

Para más información, vea [Cancelación de tareas](../../../docs/standard/parallel-programming/task-cancellation.md) y [Cómo: Cancelar una tarea y sus elementos secundarios](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md).

## <a name="the-taskfactory-class"></a>Clase TaskFactory

La clase <xref:System.Threading.Tasks.TaskFactory> proporciona métodos estáticos que encapsulan algunos modelos comunes de creación e inicio de tareas y tareas de continuación.

- El modelo más común es <xref:System.Threading.Tasks.TaskFactory.StartNew%2A>, que crea e inicia una tarea en una sola instrucción.

- Cuando cree tareas de continuación a partir de varios antecedentes, use el método <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A> o el método<xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A> o sus equivalentes en la clase <xref:System.Threading.Tasks.Task%601>. Para más información, consulte [Encadenar tareas mediante tareas de continuación](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).

- Para encapsular los métodos `BeginX` y `EndX` del modelo de programación asincrónica en una instancia de <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>, use los métodos <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A>. Para más información, consulte [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) (TPL y la programación asincrónica tradicional de .NET).

Al objeto <xref:System.Threading.Tasks.TaskFactory> predeterminado se puede tener acceso como propiedad estática de la clase <xref:System.Threading.Tasks.Task> o de la clase <xref:System.Threading.Tasks.Task%601>. También pueden crearse directamente instancias de <xref:System.Threading.Tasks.TaskFactory> y especificar varias opciones entre las que se incluyan las opciones <xref:System.Threading.CancellationToken>, <xref:System.Threading.Tasks.TaskCreationOptions>, <xref:System.Threading.Tasks.TaskContinuationOptions> o <xref:System.Threading.Tasks.TaskScheduler>. Cualquier opción que se especifique al crear el generador de tareas se aplicará a todas las tareas que este generador cree, a menos que <xref:System.Threading.Tasks.Task> se cree usando la enumeración <xref:System.Threading.Tasks.TaskCreationOptions>, en cuyo caso las opciones de la tarea reemplazarán a las del generador de tareas.

## <a name="tasks-without-delegates"></a>Tareas sin delegados

En algunos casos, es posible que desee usar un objeto <xref:System.Threading.Tasks.Task> para encapsular alguna operación asincrónica ejecutada por un componente externo en lugar de su propio usuario delegado. Si la operación se basa en el patrón Begin/End del modelo de programación asincrónica, puede usar los métodos <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A>. Si no es este el caso, puede usar el objeto <xref:System.Threading.Tasks.TaskCompletionSource%601> para encapsular la operación en una tarea y, de este modo, aprovechar algunas de las ventajas de programación de <xref:System.Threading.Tasks.Task>, como por ejemplo, su compatibilidad con la propagación de excepciones y el uso de continuaciones. Para más información, consulte <xref:System.Threading.Tasks.TaskCompletionSource%601>.

## <a name="custom-schedulers"></a>Programadores personalizados

La mayoría de los desarrolladores de aplicaciones o bibliotecas no prestan atención al procesador en el que se ejecuta la tarea, al modo en que la tarea sincroniza su trabajo con otras tareas o al modo en que se programa la tarea en el objeto <xref:System.Threading.ThreadPool?displayProperty=nameWithType>. Solo necesitan que la ejecución en el equipo host sea lo más eficaz posible. Si necesita tener un control más minucioso sobre los detalles de programación, la biblioteca TPL permite configurar algunos valores del programador de tareas predeterminado e incluso permite proporcionar un programador personalizado. Para más información, consulte <xref:System.Threading.Tasks.TaskScheduler>.

## <a name="related-data-structures"></a>Estructuras de datos relacionados

TPL tiene varios tipos públicos nuevos que resultan útiles tanto en escenarios en paralelo como en escenarios secuenciales. Entre ellos, se incluyen diversas clases de colecciones multiproceso rápidas y escalables del espacio de nombres <xref:System.Collections.Concurrent?displayProperty=nameWithType> y varios tipos nuevos de sincronización, como <xref:System.Threading.Semaphore?displayProperty=nameWithType> y <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, que resultan más eficaces que sus predecesores en tipos concretos de cargas de trabajo. Otros tipos nuevos de .NET Framework versión 4, como <xref:System.Threading.Barrier?displayProperty=nameWithType> y <xref:System.Threading.SpinLock?displayProperty=nameWithType>, proporcionan una funcionalidad que no estaba disponible en versiones anteriores. Para más información, consulte [Estructuras de datos para la programación paralela](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md).

## <a name="custom-task-types"></a>Tipos de tarea personalizados

Se recomienda no heredar de <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> ni de <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>. En su lugar, se recomienda usar la propiedad <xref:System.Threading.Tasks.Task.AsyncState%2A> para asociar los datos adicionales o el estado a un objeto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. También puede usar métodos de extensión para extender la funcionalidad de las clases <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601>. Para más información sobre los métodos de extensión, consulte [Métodos de extensión (C#)](../../csharp/programming-guide/classes-and-structs/extension-methods.md) y [Métodos de extensión (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).

Si debe heredar de <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>, no puede usar <xref:System.Threading.Tasks.Task.Run%2A>, o las clases <xref:System.Threading.Tasks.TaskFactory?displayProperty=nameWithType>, <xref:System.Threading.Tasks.TaskFactory%601?displayProperty=nameWithType> o <xref:System.Threading.Tasks.TaskCompletionSource%601?displayProperty=nameWithType>, para crear instancias del tipo de tarea personalizada porque estos mecanismos solo crean objetos <xref:System.Threading.Tasks.Task> y objetos <xref:System.Threading.Tasks.Task%601>. Además, no puede usar los mecanismos de continuación de tarea proporcionados por <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.TaskFactory> y <xref:System.Threading.Tasks.TaskFactory%601> para crear instancias del tipo de tarea personalizada porque también estos mecanismos crean solo objetos <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601>.

## <a name="related-topics"></a>Temas relacionados

|Title|DESCRIPCIÓN|
|-|-|
|[Encadenar tareas mediante tareas de continuación](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md)|Describe el funcionamiento de las continuaciones.|
|[Attached and Detached Child Tasks](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md) (Tareas secundarias asociadas y desasociadas)|Describe la diferencia entre las tareas secundarias asociadas y desasociadas.|
|[Cancelación de tareas](../../../docs/standard/parallel-programming/task-cancellation.md)|Describe la compatibilidad con la cancelación que está integrada en el objeto <xref:System.Threading.Tasks.Task>.|
|[Control de excepciones](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md)|Describe cómo se controlan excepciones en subprocesos simultáneos.|
|[Cómo: Usar Parallel.Invoke para ejecutar operaciones en paralelo](../../../docs/standard/parallel-programming/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Describe cómo usar <xref:System.Threading.Tasks.Parallel.Invoke%2A>.|
|[Cómo: Devolver un valor a partir de una tarea](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md)|Describe cómo devolver valores de tareas.|
|[Cómo: Cancelar una tarea y sus elementos secundarios](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)|Describe cómo cancelar tareas.|
|[Cómo: Crear tareas precalculadas](../../../docs/standard/parallel-programming/how-to-create-pre-computed-tasks.md)|Describe cómo utilizar el método <xref:System.Threading.Tasks.Task.FromResult%2A?displayProperty=nameWithType> para recuperar los resultados de las operaciones asincrónicas de descarga que se retienen en una memoria caché.|
|[Cómo: Recorrer un árbol binario con tareas en paralelo](../../../docs/standard/parallel-programming/how-to-traverse-a-binary-tree-with-parallel-tasks.md)|Describe cómo utilizar tareas para atravesar un árbol binario.|
|[Cómo: Desencapsular una tarea anidada](../../../docs/standard/parallel-programming/how-to-unwrap-a-nested-task.md)|Demuestra cómo utilizar el método de extensión <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>.|
|[Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md) (Paralelismo de datos)|Describe cómo usar <xref:System.Threading.Tasks.Parallel.For%2A> y <xref:System.Threading.Tasks.Parallel.ForEach%2A> para crear bucles paralelos sobre los datos.|
|[Programación en paralelo](../../../docs/standard/parallel-programming/index.md)|Nodo de nivel superior de la programación en paralelo de .NET Framework.|

## <a name="see-also"></a>Vea también

- [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)
- [Samples for Parallel Programming with the .NET Framework](https://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364) (Ejemplos de programación en paralelo con .NET Framework)
