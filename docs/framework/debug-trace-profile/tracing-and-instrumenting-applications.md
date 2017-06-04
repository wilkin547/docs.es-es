---
title: "Seguimiento e instrumentaci&#243;n de aplicaciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "seguimiento [.NET Framework]"
  - "instrumentación, de depuración [.NET Framework]"
  - "supervisión del rendimiento, instrumentación"
  - "instrumentación, acerca de la instrumentación"
  - "seguimiento [.NET Framework], acerca del seguimiento"
  - "supervisión del rendimiento, seguimiento de código"
  - "Trace (clase), instrumentación para aplicaciones .NET"
ms.assetid: 773b6fc4-9013-4322-b728-5dec7a72e743
caps.latest.revision: 21
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 21
---
# Seguimiento e instrumentaci&#243;n de aplicaciones
El seguimiento es una manera de supervisar la ejecución de la aplicación mientras se está ejecutando. Puede agregar instrumentación de seguimiento y de depuración a la aplicación de .NET Framework cuando la desarrolle, y puede usar dicha instrumentación mientras desarrolla la aplicación y después de implementarla. Puede usar el <xref:System.Diagnostics.Trace?displayProperty=fullName>, <xref:System.Diagnostics.Debug?displayProperty=fullName>, y <xref:System.Diagnostics.TraceSource?displayProperty=fullName> clases para registrar información sobre errores y ejecución de la aplicación en registros, archivos de texto u otros dispositivos para su posterior análisis.  
  
 El término *instrumentación* hace referencia a la capacidad de supervisar o medir el nivel de rendimiento de un producto y diagnosticar errores. En programación, esto significa la capacidad de una aplicación para incorporar:  
  
-   **Seguimiento de código** -recibir mensajes informativos sobre la ejecución de una aplicación en tiempo de ejecución.  
  
-   **Depuración** : localizar y corregir errores de programación en una aplicación en desarrollo. Para obtener más información, consulte [depuración](../Topic/Debugging%20in%20Visual%20Studio.md).  
  
-   **Contadores de rendimiento** -componentes que permiten supervisar el rendimiento de la aplicación. Para obtener más información, consulte [los contadores de rendimiento](../../../docs/framework/debug-trace-profile/performance-counters.md).  
  
-   **Registros de eventos** -componentes que le permiten recibir y realizar el seguimiento de eventos importantes en la ejecución de la aplicación. Para obtener más información, consulte el <xref:System.Diagnostics.EventLog> clase.  
  
 La instrumentación de la aplicación mediante la colocación de instrucciones de seguimiento en puntos estratégicos del código resulta especialmente útil con aplicaciones distribuidas. Mediante el uso de instrucciones de seguimiento, puede instrumentar una aplicación no solo para mostrar información cuando existe algún problema, sino también para supervisar el rendimiento de la aplicación.  
  
 El <xref:System.Diagnostics.TraceSource> clase proporciona características mejoradas de seguimiento y puede usarse en lugar de los métodos estáticos de la antigua <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug> clases de seguimiento. La conocida <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug> clases se siguen usando ampliamente, pero la <xref:System.Diagnostics.TraceSource> clase se recomienda para nuevos comandos de seguimiento, como <xref:System.Diagnostics.TraceSource.TraceEvent%2A> y <xref:System.Diagnostics.TraceSource.TraceData%2A>.  
  
 El <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug> clases son idénticas, salvo que los procedimientos y funciones de la <xref:System.Diagnostics.Trace> clase se compilan de forma predeterminada en las versiones de lanzamiento, pero los de la <xref:System.Diagnostics.Debug> no son de clase.  
  
 El <xref:System.Diagnostics.Trace> y <xref:System.Diagnostics.Debug> clases proporcionan los medios para supervisar y examinar el rendimiento de la aplicación durante el desarrollo o después de la implementación. Por ejemplo, puede usar el <xref:System.Diagnostics.Trace> clase para realizar un seguimiento de determinados tipos de acciones en una aplicación implementada ya que se producen (por ejemplo, la creación de nuevas conexiones de base de datos) y, por tanto, pueden supervisar la eficiencia de la aplicación.  
  
## <a name="code-tracing-and-debugging"></a>Seguimiento de código y depuración  
 Durante el desarrollo, puede utilizar los métodos de salida de la <xref:System.Diagnostics.Debug> clase para mostrar mensajes en la ventana de salida del entorno de desarrollo integrado (IDE) de Visual Studio. Por ejemplo:  
  
```vb  
Trace.WriteLine("Hello World!")  
Debug.WriteLine("Hello World!")  
  
```  
  
```csharp  
System.Diagnostics.Trace.WriteLine("Hello World!");  
System.Diagnostics.Debug.WriteLine("Hello World!");  
  
```  
  
 Cada uno de estos ejemplos mostrará "¡Hello World!" en la ventana de resultados cuando se ejecuta la aplicación en el depurador.  
  
 Esto le permite depurar las aplicaciones y optimizar su rendimiento en función de su comportamiento en el entorno de prueba. Puede depurar la aplicación en la compilación de depuración con el <xref:System.Diagnostics.Debug> atributo condicional activado para que reciban todos los resultados de depuración. Cuando la aplicación está lista para el lanzamiento, puede compilar la versión de lanzamiento sin activar el <xref:System.Diagnostics.Debug> atributo condicional, lo que el compilador no incluirá el código de depuración en el ejecutable final. Para obtener más información, consulte [Cómo: compilación condicional con Trace y Debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md). Para obtener más información sobre diferentes configuraciones de compilación para su aplicación, consulte [compilar y generar](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md).  
  
 Asimismo, puede seguir la ejecución de código en una aplicación instalada, utilizando métodos de la <xref:System.Diagnostics.Trace> clase. Colocando [modificadores de seguimiento](../../../docs/framework/debug-trace-profile/trace-switches.md) en el código, puede controlar si se realiza el seguimiento y su alcance. Esto le permite supervisar el estado de la aplicación en un entorno de producción. Este aspecto es especialmente importante en aplicaciones empresariales que usen varios componentes que se ejecutan en varios equipos. El control sobre el uso de los modificadores después de la implementación se realiza a través del archivo de configuración. Para obtener más información, consulte [Cómo: crear, inicializar y configurar modificadores de seguimiento](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md).  
  
 Al desarrollar una aplicación para la que se va a usar seguimiento, normalmente se incluyen en el código de la aplicación tanto mensajes de seguimiento como mensajes de depuración. Cuando esté listo para implementar la aplicación, puede compilar la versión de lanzamiento sin activar el **depurar** atributo condicional. Sin embargo, puede activar la **seguimiento** atributo condicional para que el compilador incluya el código de seguimiento en el ejecutable. Para obtener más información, consulte [Cómo: compilación condicional con Trace y Debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md).  
  
### <a name="phases-of-code-tracing"></a>Fases del seguimiento de código  
 El seguimiento de código consta de tres fases:  
  
1.  **Instrumentación** : agregar código de seguimiento a la aplicación.  
  
2.  **Seguimiento de** : el código de seguimiento escribe información en el destino especificado.  
  
3.  **Análisis** : evaluar la información de seguimiento para identificar y comprender los problemas de la aplicación.  
  
 Durante el desarrollo, todos los métodos de salida debug y trace escriben información en la ventana de salida de Visual Studio de forma predeterminada. En una aplicación implementada, los métodos escriben información de seguimiento en los destinos que se especifiquen. Para obtener más información sobre cómo especificar un destino de salida para el seguimiento o depuración, vea [los agentes de escucha de seguimiento](../../../docs/framework/debug-trace-profile/trace-listeners.md).  
  
 A continuación se ofrece una visión general de los pasos principales que intervienen en el uso del seguimiento para analizar y corregir posibles problemas en aplicaciones implementadas. Para obtener más información sobre cómo realizar estos pasos, vea el vínculo apropiado.  
  
##### <a name="to-use-tracing-in-an-application"></a>Para usar el seguimiento en una aplicación  
  
1.  Considere qué salida de seguimiento desea recibir in situ después de haber implementado la aplicación.  
  
2.  Cree un conjunto de conmutadores. Para obtener más información, consulte [Cómo: configurar modificadores de seguimiento](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md).  
  
3.  Agregue las instrucciones de seguimiento al código de aplicación.  
  
4.  Determine dónde desea que aparezca la salida del seguimiento y agregue los agentes de escucha apropiados. Para obtener más información, consulte [Creating and inicializar agentes de escucha de seguimiento](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-listeners.md).  
  
5.  Pruebe y depure la aplicación y el código de seguimiento que contiene.  
  
6.  Compile la aplicación en código ejecutable mediante uno de los siguientes procedimientos:  
  
    -   Utilice la **crear** menú junto con el **depurar** página de la **páginas de propiedades** cuadro de diálogo de **el Explorador de soluciones**. Use este procedimiento si compila en Visual Studio.  
  
         \- o -  
  
    -   Utilice la **seguimiento** y **depurar** directivas de compilador para el método de línea de comandos de compilación. Para obtener más información, consulte [compilación condicional con Trace y Debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md). Use este procedimiento si compila desde la línea de comandos.  
  
7.  Si se produce un problema durante el tiempo de ejecución, active el modificador de seguimiento adecuado. Para obtener más información, consulte [configurar modificadores de seguimiento](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md).  
  
     El código de seguimiento escribe mensajes de seguimiento en un destino especificado, por ejemplo, una pantalla, un archivo de texto o un registro de eventos. El tipo de agente de escucha incluido en la **Trace.Listeners** colección determina el destino.  
  
8.  Analice los mensajes de seguimiento para identificar y comprender los problemas de la aplicación.  
  
## <a name="trace-instrumentation-and-distributed-applications"></a>Instrumentación de seguimiento y aplicaciones distribuidas  
 Con las aplicaciones distribuidas no resulta fácil probar la aplicación de la manera en que se usará. No hay muchos equipos de desarrollo que tengan la capacidad de probar todas las posibles combinaciones de sistemas operativos o exploradores web (incluidas todas las opciones de idiomas de localización), o de simular el elevado número de usuarios que tendrán acceso simultáneo a la aplicación. En estas circunstancias, no es posible probar cómo responderá una aplicación distribuida ante grandes volúmenes, diferentes instalaciones y comportamientos únicos de usuario final. Además, muchas de las partes de una aplicación distribuida no disponen de ninguna interfaz de usuario con la que poder interactuar directamente o ver la actividad de esas partes.  
  
 Sin embargo, es posible compensar esto habilitando las aplicaciones distribuidas describan determinados eventos de interés para los administradores del sistema, especialmente aquello que no funciona bien, mediante *instrumentación* la aplicación, es decir, mediante la colocación de instrucciones de seguimiento en puntos estratégicos del código. A continuación, si ocurre algo inesperado en tiempo de ejecución (por ejemplo, un tiempo de respuesta excesivamente lento), podrá determinar la causa probable.  
  
 Con las instrucciones de seguimiento puede evitar la difícil tarea de examinar el código fuente original, modificarlo, volver a compilar e intentar reproducir el error de tiempo de ejecución dentro del entorno de depuración. Recuerde que puede instrumentar una aplicación no solo para mostrar errores, sino también para supervisar el rendimiento.  
  
## <a name="strategic-placement-of-trace-statements"></a>Colocación estratégica de las instrucciones de seguimiento  
 Debe tener especial cuidado al colocar las instrucciones de seguimiento para su uso durante el tiempo de ejecución. Considere qué información de seguimiento puede ser necesaria en una aplicación implementada de modo que estén bien cubiertos todos los escenarios de seguimiento probables. Puesto que las diferencias entre aplicaciones que usan el seguimiento son enormes, no existen directrices generales para la colocación estratégica del seguimiento. Para obtener más información sobre cómo colocar instrucciones de seguimiento, consulte [Cómo: agregar instrucciones de seguimiento al código de la aplicación](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md).  
  
## <a name="output-from-tracing"></a>Salida del seguimiento  
 Resultados del seguimiento se recopilan mediante objetos denominados *los agentes de escucha*. Un agente de escucha es un objeto que recibe la salida de seguimiento y la escribe en un dispositivo de salida (normalmente un archivo de texto, registro o ventana). Cuando se crea un agente de escucha, normalmente se agrega a la <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=fullName> colección, lo que le permite recibir todos los resultados de seguimiento.  
  
 La información de seguimiento siempre se escribe al menos en el valor predeterminado <xref:System.Diagnostics.Trace> destino de salida, el <xref:System.Diagnostics.DefaultTraceListener>. Si por algún motivo se ha eliminado el <xref:System.Diagnostics.DefaultTraceListener> sin agregar otros agentes de escucha para el <xref:System.Diagnostics.Trace.Listeners%2A> colección, no recibirá ningún mensaje de seguimiento. Para obtener más información, consulte [los agentes de escucha de seguimiento](../../../docs/framework/debug-trace-profile/trace-listeners.md).  
  
 Los seis <xref:System.Diagnostics.Debug> miembros y <xref:System.Diagnostics.Trace> métodos que escriben información de seguimiento se enumeran en la tabla siguiente.  
  
|Método|Salida|  
|------------|------------|  
|**Assert**|Es el texto especificado o, si no se especifica ninguno, la pila de llamadas. El resultado sólo se escribe si la condición especificada como argumento en la **Assert** instrucción es **false**.|  
|**Un error**|Es el texto especificado o, si no se especifica ninguno, la pila de llamadas.|  
|**Escribir**|Es el texto especificado.|  
|**WriteIf**|El texto especificado, si la condición especificada como argumento en la **WriteIf** satisface la instrucción.|  
|**WriteLine**|Es el texto especificado y un retorno de carro.|  
|**WriteLineIf**|El texto especificado y un retorno de carro, si la condición especificada como argumento en la **WriteLineIf** satisface la instrucción.|  
  
 Todos los agentes de escucha de la <xref:System.Diagnostics.Trace.Listeners%2A> colección reciben los mensajes descritos en la tabla anterior, pero las acciones emprendidas pueden variar según el tipo de agente de escucha recibe el mensaje. Por ejemplo, el <xref:System.Diagnostics.DefaultTraceListener> muestra un cuadro de diálogo de aserción cuando recibe una **producirá un error** o error **Assert** notificación, pero un <xref:System.Diagnostics.TextWriterTraceListener> simplemente escribe el resultado en su secuencia.  
  
 Si implementa su propio agente de escucha podrá obtener resultados personalizados. Un agente de escucha de seguimiento personalizado puede, por ejemplo, mostrar los mensajes en un cuadro de mensaje o conectarse a una base de datos para agregar mensajes a una tabla. Todos los agentes de escucha personalizados deben admitir los seis métodos mencionados anteriormente. Para obtener más información sobre cómo crear agentes de escucha definidos por el desarrollador, consulte <xref:System.Diagnostics.TraceListener> en la referencia de .NET Framework.  
  
> [!NOTE]
>  En [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], **Debug.Write**, **Debug.WriteIf**, **Debug.WriteLine**, y **Debug.WriteLineIf** han reemplazado el **Debug.Print** método que estaba disponible en versiones anteriores de Visual Basic.  
  
 El **escribir** y **WriteLine** métodos siempre escriben el texto que especifique. **Assert**, **WriteIf**, y **WriteLineIf** requieren un argumento booleano que determina si deben escribir el texto especificado; escriben el texto sólo si la expresión es **true** (para **WriteIf** y **WriteLineIf**), o **false** (para **Assert**). El **errores** método siempre escribe el texto especificado. Para obtener más información, consulte [Cómo: agregar instrucciones de seguimiento al código de la aplicación](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md) y la referencia de .NET Framework.  
  
## <a name="security-concerns"></a>Cuestiones de seguridad  
 Si no deshabilita el seguimiento y la depuración antes de implementar una aplicación ASP.NET, la aplicación puede revelar información sobre sí misma que podría ser aprovechada por un programa malintencionado. Para obtener más información, consulte [Cómo: compilación condicional con Trace y Debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md), [compilar y generar](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md), y [Cómo: crear, inicializar y configurar modificadores de seguimiento](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md). La depuración también es configurable a través de Internet Information Services (IIS).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.TraceSource>   
 [Contratos de código](../../../docs/framework/debug-trace-profile/code-contracts.md)   
 [C#, F # y tipos de proyecto de Visual Basic](../Topic/Debugging%20Preparation:%20C%23,%20F%23,%20and%20Visual%20Basic%20Project%20Types.md)   
 [Cómo: agregar instrucciones de seguimiento al código de aplicación](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)   
 [Cómo: compilación condicional con Trace y Debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)   
 [Cómo: crear, inicializar y configurar modificadores de seguimiento](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)   
 [Cómo: crear e inicializar orígenes de seguimiento](../../../docs/framework/debug-trace-profile/how-to-create-and-initialize-trace-sources.md)   
 [Cómo: Utilizar TraceSource y filtros con agentes de escucha de seguimiento](../../../docs/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md)   
 [Agentes de escucha de seguimiento](../../../docs/framework/debug-trace-profile/trace-listeners.md)   
 [Modificadores de seguimiento](../../../docs/framework/debug-trace-profile/trace-switches.md)