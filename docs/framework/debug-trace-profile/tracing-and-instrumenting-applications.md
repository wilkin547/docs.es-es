---
title: Seguimiento e instrumentación de aplicaciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework]
- debugging [.NET Framework], instrumentation
- performance monitoring, instrumentation
- instrumentation, about instrumentation
- tracing [.NET Framework], about tracing
- performance monitoring, tracing code
- Trace class, instrumentation for .NET applications
ms.assetid: 773b6fc4-9013-4322-b728-5dec7a72e743
ms.openlocfilehash: 2dcdbaf50ed053d43fc2df2c80fe7688e7b3e51f
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542616"
---
# <a name="tracing-and-instrumenting-applications"></a>Seguimiento e instrumentación de aplicaciones
El seguimiento es una manera de supervisar la ejecución de la aplicación mientras se está ejecutando. Puede agregar instrumentación de seguimiento y de depuración a la aplicación de .NET Framework cuando la desarrolle, y puede usar dicha instrumentación mientras desarrolla la aplicación y después de implementarla. Puede usar las clases <xref:System.Diagnostics.Trace?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug?displayProperty=nameWithType> y <xref:System.Diagnostics.TraceSource?displayProperty=nameWithType> para registrar información sobre errores y ejecución de la aplicación en registros, archivos de texto u otros dispositivos para su análisis posterior.  
  
 El término *instrumentación* hace referencia a la capacidad de supervisar o medir el nivel de rendimiento de un producto y diagnosticar errores. En programación, esto significa la capacidad de una aplicación para incorporar:  
  
- **Seguimiento de código**: recibir mensajes informativos sobre la ejecución de una aplicación en tiempo de ejecución.  
  
- **Depuración**: localizar y corregir errores de programación en una aplicación en desarrollo. Para más información, vea [Depuración](/visualstudio/debugger/debugger-feature-tour).  
  
- **Contadores de rendimiento**: componentes que permiten realizar el seguimiento del rendimiento de la aplicación. Para más información, consulte [Performance Counters](performance-counters.md).  
  
- **Registros de eventos**: componentes que permiten recibir y realizar el seguimiento de eventos importantes en la ejecución de la aplicación. Para obtener más información, vea la clase <xref:System.Diagnostics.EventLog>.  
  
 La instrumentación de la aplicación mediante la colocación de instrucciones de seguimiento en puntos estratégicos del código resulta especialmente útil con aplicaciones distribuidas. Mediante el uso de instrucciones de seguimiento, puede instrumentar una aplicación no solo para mostrar información cuando existe algún problema, sino también para supervisar el rendimiento de la aplicación.  
  
 La clase <xref:System.Diagnostics.TraceSource> proporciona características mejoradas de seguimiento y puede usarse en lugar de los métodos estáticos de las clases anteriores de seguimiento <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug>. Las ya conocidas clases <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug> se siguen usando ampliamente, pero la clase <xref:System.Diagnostics.TraceSource> se recomienda para nuevos comandos de seguimiento, como <xref:System.Diagnostics.TraceSource.TraceEvent%2A> y <xref:System.Diagnostics.TraceSource.TraceData%2A>.  
  
 Las clases <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug> son idénticas, salvo que los procedimientos y funciones de la clase <xref:System.Diagnostics.Trace> se compilan de forma predeterminada en las versiones de lanzamiento, a diferencia de los de la clase <xref:System.Diagnostics.Debug>.  
  
 Las clases <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug> proporcionan los medios para supervisar y examinar el rendimiento de la aplicación durante el desarrollo o después de la implementación. Por ejemplo, puede usar la clase <xref:System.Diagnostics.Trace> para realizar un seguimiento de determinados tipos de acciones en una aplicación implementada a medida que se producen (por ejemplo, la creación de nuevas conexiones de base de datos) y, por tanto, pueden supervisar la eficiencia de la aplicación.  
  
## <a name="code-tracing-and-debugging"></a>Seguimiento de código y depuración  
 Durante el desarrollo, puede usar los métodos de salida de la clase <xref:System.Diagnostics.Debug> para mostrar mensajes en la ventana de salida del entorno de desarrollo integrado (IDE) de Visual Studio. Por ejemplo:  
  
```vb  
Trace.WriteLine("Hello World!")  
Debug.WriteLine("Hello World!")  
```  
  
```csharp  
System.Diagnostics.Trace.WriteLine("Hello World!");  
System.Diagnostics.Debug.WriteLine("Hello World!");  
```  
  
 Cada uno de estos ejemplos mostrará "Hello World!" en la ventana de resultados cuando se ejecute la aplicación en el depurador.  
  
 Esto le permite depurar las aplicaciones y optimizar su rendimiento en función de su comportamiento en el entorno de prueba. Puede depurar la aplicación en la compilación de depuración con el atributo condicional <xref:System.Diagnostics.Debug> activado para así recibir toda la salida de la depuración. Cuando la aplicación está lista para el lanzamiento, puede compilar la versión de lanzamiento sin activar el atributo condicional <xref:System.Diagnostics.Debug>, con lo que el compilador no incluirá el código de depuración en el ejecutable final. Para más información, vea [Cómo: Realizar compilación condicional con Trace y Debug](how-to-compile-conditionally-with-trace-and-debug.md). Para más información sobre diferentes configuraciones de compilación para la aplicación, vea [Compilar y generar](/visualstudio/ide/compiling-and-building-in-visual-studio).  
  
 Asimismo, puede usar métodos de la clase <xref:System.Diagnostics.Trace> para seguir la ejecución de código en una aplicación instalada. Al colocar [modificadores de seguimiento](trace-switches.md) en el código, puede controlar si se realiza el seguimiento y cuál es su alcance. Con ello puede supervisar el estado de la aplicación en un entorno de producción. Esto es especialmente importante en una aplicación empresarial que usa varios componentes que se ejecutan en varios equipos. El control sobre el uso de los modificadores después de la implementación se realiza a través del archivo de configuración. Para más información, vea [Cómo: Crear, inicializar y configurar modificadores de seguimiento](how-to-create-initialize-and-configure-trace-switches.md).  
  
 Al desarrollar una aplicación para la que se va a usar seguimiento, normalmente se incluyen en el código de la aplicación tanto mensajes de seguimiento como mensajes de depuración. Cuando la aplicación esté lista para implementarse, se puede compilar la versión de lanzamiento sin necesidad de activar el atributo condicional **Debug**. No obstante, se puede activar el atributo condicional **Trace** para que el compilador incluya el código de seguimiento en el ejecutable. Para más información, vea [Cómo: Realizar compilación condicional con Trace y Debug](how-to-compile-conditionally-with-trace-and-debug.md).  
  
### <a name="phases-of-code-tracing"></a>Fases del seguimiento de código  
 El seguimiento de código consta de tres fases:  
  
1. **Instrumentación**: agregar código de seguimiento a la aplicación.  
  
2. **Seguimiento**: el código de seguimiento escribe información en el destino especificado.  
  
3. **Análisis**: se evalúa la información de seguimiento para identificar y comprender los problemas de la aplicación.  
  
 Durante el desarrollo, todos los métodos de salida debug y trace<bpt i="1000001" x="1000001" type="formatting">{i&gt;</bpt><ept i="1000001">&lt;i}</ept>escriben información en la ventana de salida de Visual Studio de forma predeterminada. En una aplicación implementada, los métodos escriben información de seguimiento en los destinos que se especifiquen. Para más información sobre cómo especificar un destino de salida para el seguimiento o la depuración, vea [Agentes de escucha de seguimiento](trace-listeners.md).  
  
 A continuación se ofrece una visión general de los pasos principales que intervienen en el uso del seguimiento para analizar y corregir posibles problemas en aplicaciones implementadas. Para obtener más información sobre cómo realizar estos pasos, vea el vínculo apropiado.  
  
##### <a name="to-use-tracing-in-an-application"></a>Para usar el seguimiento en una aplicación  
  
1. Considere qué salida de seguimiento desea recibir in situ después de haber implementado la aplicación.  
  
2. Cree un conjunto de conmutadores. Para obtener más información, consulte [Procedimientos: configuración de modificadores de seguimiento](how-to-create-initialize-and-configure-trace-switches.md).  
  
3. Agregue las instrucciones de seguimiento al código de aplicación.  
  
4. Determine dónde desea que aparezca la salida del seguimiento y agregue los agentes de escucha apropiados. Para más información, vea [Creación e inicialización de agentes de escucha de seguimiento](how-to-create-and-initialize-trace-listeners.md).  
  
5. Pruebe y depure la aplicación y el código de seguimiento que contiene.  
  
6. Compile la aplicación en código ejecutable mediante uno de los siguientes procedimientos:  
  
    - Use el menú **Compilación** junto con la página **Depurar** del cuadro de diálogo **Páginas de propiedades** del **Explorador de soluciones**. Use este procedimiento si compila en Visual Studio.  
  
         \- O bien  
  
    - Use las directivas de compilador **Trace** y **Debug** para el método de línea de comandos de compilación. Para más información, vea [Compilación condicional con Trace y Debug](how-to-compile-conditionally-with-trace-and-debug.md). Use este procedimiento si compila desde la línea de comandos.  
  
7. Si se produce un problema durante el tiempo de ejecución, active el modificador de seguimiento adecuado. Para más información, vea [Configuración de modificadores de seguimiento](how-to-create-initialize-and-configure-trace-switches.md).  
  
     El código de seguimiento escribe mensajes de seguimiento en un destino especificado, por ejemplo, una pantalla, un archivo de texto o un registro de eventos. El tipo de agente de escucha incluido en la colección de <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> determina el destino.  
  
8. Analice los mensajes de seguimiento para identificar y comprender los problemas de la aplicación.  
  
## <a name="trace-instrumentation-and-distributed-applications"></a>Instrumentación de seguimiento y aplicaciones distribuidas  
 Con las aplicaciones distribuidas no resulta fácil probar la aplicación de la manera en que se usará. No hay muchos equipos de desarrollo que tengan la capacidad de probar todas las posibles combinaciones de sistemas operativos o exploradores web (incluidas todas las opciones de idiomas de localización), o de simular el elevado número de usuarios que tendrán acceso simultáneo a la aplicación. En estas circunstancias, no es posible probar cómo responderá una aplicación distribuida ante grandes volúmenes, diferentes instalaciones y comportamientos únicos de usuario final. Además, muchas de las partes de una aplicación distribuida no disponen de ninguna interfaz de usuario con la que poder interactuar directamente o ver la actividad de esas partes.  
  
 Pero es posible compensar esto permitiendo a las aplicaciones distribuidas describir determinados eventos de interés para los administradores del sistema, especialmente aquello que no funciona bien, mediante la *instrumentación* de la aplicación, es decir, mediante la colocación de instrucciones de seguimiento en puntos estratégicos del código. A continuación, si ocurre algo inesperado en tiempo de ejecución (por ejemplo, un tiempo de respuesta excesivamente lento), podrá determinar la causa probable.  
  
 Con las instrucciones de seguimiento puede evitar la difícil tarea de examinar el código fuente original, modificarlo, volver a compilar e intentar reproducir el error de tiempo de ejecución dentro del entorno de depuración. Recuerde que puede instrumentar una aplicación no solo para mostrar errores, sino también para supervisar el rendimiento.  
  
## <a name="strategic-placement-of-trace-statements"></a>Colocación estratégica de las instrucciones de seguimiento  
 Debe tener especial cuidado al colocar las instrucciones de seguimiento para su uso durante el tiempo de ejecución. Considere qué información de seguimiento puede ser necesaria en una aplicación implementada de modo que estén bien cubiertos todos los escenarios de seguimiento probables. Puesto que las diferencias entre aplicaciones que usan el seguimiento son enormes, no existen directrices generales para la colocación estratégica del seguimiento. Para más información sobre cómo colocar instrucciones de seguimiento, vea [Cómo: Agregar instrucciones de seguimiento al código de la aplicación](how-to-add-trace-statements-to-application-code.md).  
  
## <a name="output-from-tracing"></a>Salida del seguimiento  
 La salida del seguimiento se recopila mediante objetos denominados *agentes de escucha*. Un agente de escucha es un objeto que recibe la salida de seguimiento y la escribe en un dispositivo de salida (normalmente un archivo de texto, registro o ventana). Cuando se crea un agente de escucha, normalmente se agrega a la colección <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>, lo que le permite recibir toda la salida del seguimiento.  
  
 La información de seguimiento siempre se escribe al menos en el destino de salida predeterminado de <xref:System.Diagnostics.Trace>, que es <xref:System.Diagnostics.DefaultTraceListener>. Si por algún motivo se ha eliminado <xref:System.Diagnostics.DefaultTraceListener> sin agregar otros agentes de escucha a la colección <xref:System.Diagnostics.Trace.Listeners%2A>, no recibirá ningún mensaje de seguimiento. Para más información, vea [Agentes de escucha de seguimiento](trace-listeners.md).  
  
 En la tabla siguiente se enumeran los seis miembros <xref:System.Diagnostics.Debug> y los métodos <xref:System.Diagnostics.Trace> que escriben información de seguimiento.  
  
|Método|Output|  
|------------|------------|  
|`Assert`|Es el texto especificado o, si no se especifica ninguno, la pila de llamadas. La salida solo se escribe si la condición especificada como argumento en la instrucción `Assert` es **false**.|  
|`Fail`|Es el texto especificado o, si no se especifica ninguno, la pila de llamadas.|  
|`Write`|Es el texto especificado.|  
|`WriteIf`|El texto especificado si se cumple la condición especificada como argumento en la instrucción `WriteIf`.|  
|`WriteLine`|Es el texto especificado y un retorno de carro.|  
|`WriteLineIf`|El texto especificado y un retorno de carro si se satisface la condición especificada como argumento en la instrucción `WriteLineIf`.|  
  
 Todos los agentes de escucha de la colección <xref:System.Diagnostics.Trace.Listeners%2A> reciben los mensajes descritos en la tabla anterior, pero las acciones emprendidas pueden variar según el tipo de agente de escucha que recibe el mensaje. Por ejemplo, el <xref:System.Diagnostics.DefaultTraceListener> muestra un cuadro de diálogo de aserción cuando recibe una notificación de `Assert` `Fail` o con errores, pero un <xref:System.Diagnostics.TextWriterTraceListener> simplemente escribe el resultado en su secuencia.  
  
 Si implementa su propio agente de escucha podrá obtener resultados personalizados. Un agente de escucha de seguimiento personalizado puede, por ejemplo, mostrar los mensajes en un cuadro de mensaje o conectarse a una base de datos para agregar mensajes a una tabla. Todos los agentes de escucha personalizados deben admitir los seis métodos mencionados anteriormente. Para obtener más información sobre cómo crear agentes de escucha definidos por el desarrollador, consulte <xref:System.Diagnostics.TraceListener> en la documentación de .NET Framework.  
  
 Los métodos `Write` y `WriteLine` siempre escriben el texto que especifique. `Assert`, `WriteIf`y `WriteLineIf` requieren un argumento booleano que controla si escriben o no el texto especificado. solo escriben el texto especificado si la expresión es **true** (para `WriteIf` y `WriteLineIf`) o **false** (para `Assert`). El método `Fail` siempre escribe el texto especificado. Para más información, vea [Cómo: Agregar instrucciones de seguimiento al código de la aplicación](how-to-add-trace-statements-to-application-code.md) y la referencia de .NET Framework.  
  
## <a name="security-concerns"></a>Cuestiones de seguridad  
 Si no deshabilita el seguimiento y la depuración antes de implementar una aplicación ASP.NET, la aplicación puede revelar información sobre sí misma que podría ser aprovechada por un programa malintencionado. Para más información, vea [Cómo: Realizar compilación condicional con Trace y Debug](how-to-compile-conditionally-with-trace-and-debug.md), [Compilar y generar](/visualstudio/ide/compiling-and-building-in-visual-studio) y [Cómo: Crear, inicializar y configurar modificadores de seguimiento](how-to-create-initialize-and-configure-trace-switches.md). La depuración también es configurable a través de Internet Information Services (IIS).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceSource>
- [Contratos de código](code-contracts.md)
- [Tipos de proyectos de C#, F# y Visual Basic](/visualstudio/debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types)
- [Adición de instrucciones de seguimiento al código de la aplicación](how-to-add-trace-statements-to-application-code.md)
- [Compilación condicional con Trace y Debug](how-to-compile-conditionally-with-trace-and-debug.md)
- [Creación, inicialización y configuración de modificadores de seguimiento](how-to-create-initialize-and-configure-trace-switches.md)
- [Creación e inicialización de orígenes de seguimiento](how-to-create-and-initialize-trace-sources.md)
- [Uso de TraceSource y filtros con agentes de escucha de seguimiento](how-to-use-tracesource-and-filters-with-trace-listeners.md)
- [Agentes de escucha de seguimiento](trace-listeners.md)
- [Modificadores de seguimiento](trace-switches.md)
