---
title: Rendimiento de Windows Workflow Foundation
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67d2b3e8-3777-49f8-9084-abbb33b5a766
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae5bf1088ec03229eb996b0e43b3d3395497571a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="windows-workflow-foundation-4-performance"></a>Rendimiento de Windows Workflow Foundation
Dustin Metzgar  
  
 Wenlong Dong  
  
 Microsoft Corporation, septiembre de 2010  
  
 Microsoft [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] incluye una revisión principal de Windows Workflow Foundation (WF) con las inversiones relevantes en rendimiento.  Esta nueva revisión introduce cambios significativos de diseño con respecto a versiones anteriores de [!INCLUDE[wf1](../../../includes/wf1-md.md)] que se proporcionaban como parte de .NET Framework 3.0 y [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. Se ha rediseñado en lo que respecta al núcleo del modelo de programación, el runtime y las herramientas para mejorar significativamente el rendimiento y la facilidad de uso. En este tema se muestran las características de rendimiento más importantes de estas revisiones y se comparan con las de la versión anterior.  
  
 El rendimiento de cada componente de flujo de trabajo se ha aumentado por órdenes de magnitud entre WF3 y WF4.  Esto hace que la separación entre los servicios de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] codificados manualmente y los servicios de flujo de trabajo de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] sea bastante pequeño.  La latencia del flujo de trabajo se ha reducido significativamente en WF4.  El rendimiento de persistencia ha aumentado en un factor comprendido entre 2,5 y 3,0.  Se ha reducido notablemente la sobrecarga del seguimiento de estado por medio del seguimiento de flujo de trabajo.  Estas son razones de peso para migrar a WF4, o adoptarlo, en las aplicaciones.  
  
## <a name="terminology"></a>Terminología  
 La versión de [!INCLUDE[wf1](../../../includes/wf1-md.md)] presentada en [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] se denominará WF4 en el resto de este tema.  [!INCLUDE[wf1](../../../includes/wf1-md.md)] se presentó en .Net 3.0 y tiene algunas revisiones secundarias mediante [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] SP1. La versión de Workflow Foundation para [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] se denominará WF3 en el resto de este tema. WF3 se incluye en [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] en paralelo con WF4. [!INCLUDE[crabout](../../../includes/crabout-md.md)] migrar artefactos de WF3 a WF4, vea: [Guía de migración de Windows Workflow Foundation 4](http://go.microsoft.com/fwlink/?LinkID=153313)  
  
 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] es el modelo de programación unificado de Microsoft para compilar aplicaciones orientadas a servicios. Se introdujo por primera vez como parte de .NET 3.0 junto con WF3 y ahora es uno de los componentes clave de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  
  
 Windows Server AppFabric es un conjunto de tecnologías integradas que permiten compilar, escalar y administrar más fácilmente aplicaciones web y aplicaciones compuestas que se ejecutan en IIS. Proporciona herramientas para supervisar y administrar servicios y flujos de trabajo. Para obtener más información, vea [Windows Server AppFabric](http://msdn.microsoft.com/windowsserver/ee695849.aspx)  
  
## <a name="goals"></a>Objetivos  
 El objetivo de este tema es mostrar las características de rendimiento de WF4 con datos medidos para diferentes escenarios. También se proporcionan en él comparaciones detalladas entre WF4 y WF3, y asimismo se muestran las grandes mejoras realizadas en esta nueva revisión. Los escenarios y los datos presentados en este artículo cuantifican el costo subyacente de distintos aspectos de WF4 y WF3. Estos datos son útiles para entender las características de rendimiento de WF4 y pueden ser útiles para planear migraciones de WF3 a WF4 o utilizar WF4 en el desarrollo de aplicaciones. Sin embargo, se debe ser cauto al considerar las conclusiones extraídas de los datos presentados en este artículo. El rendimiento de una aplicación de flujo de trabajo compuesta depende en gran medida de cómo se implementa el flujo de trabajo y cómo se integran los distintos componentes. Se debe medir cada aplicación para determinar las características de rendimiento de la misma.  
  
## <a name="overview-of-wf4-performance-enhancements"></a>Información general sobre las mejoras de rendimiento de WF4  
 WF4 se ha diseñado e implementado cuidadosamente con un alto grado de rendimiento y escalabilidad que se describe en las siguientes secciones.  
  
### <a name="wf-runtime"></a>Runtime de WF  
 El núcleo del runtime de [!INCLUDE[wf1](../../../includes/wf1-md.md)] lo constituye un programador asincrónico que controla la ejecución de las actividades en un flujo de trabajo. Proporciona un entorno de ejecución predecible y de gran rendimiento para las actividades. El entorno tiene un contrato bien definido en materia de ejecución, continuación, realización, cancelación y control de excepciones, así como un modelo de subprocesos predecible.  
  
 En comparación con WF3, el runtime de WF4 tiene un programador más eficaz. Aprovecha el mismo grupo de subprocesos de E/S que se utiliza para [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], que muestra gran eficacia en la ejecución de elementos de trabajo por lotes. La cola del programador interno de elementos de trabajo se ha optimizado para la mayoría de los patrones de uso comunes. El runtime de WF4 también administra los estados de ejecución de forma muy simple con una lógica de sincronización y control de eventos mínima, mientras que WF3 depende de una invocación y registro complejos de eventos.  
  
### <a name="data-storage-and-flow"></a>Almacenamiento y flujo de datos  
 En WF3, los datos asociados a una actividad se modelan mediante propiedades de dependencia implementadas por el tipo <xref:System.Windows.DependencyProperty>. El patrón de propiedad de dependencia se introdujo en Windows Presentation Foundation (WPF). En general, este patrón es muy flexible para admitir un enlace de datos fácil y otras características de interfaz de usuario. Sin embargo, el patrón requiere que las propiedades se definan como campos estáticos en la definición de flujo de trabajo. El establecimiento o la obtención de los valores de propiedad por parte del runtime de [!INCLUDE[wf1](../../../includes/wf1-md.md)] suponen una lógica de búsqueda compleja.  
  
 WF4 utiliza una lógica clara de ámbito de datos para mejorar sustancialmente la forma de tratar los datos en un flujo de trabajo. Separa los datos almacenados en una actividad de los datos que fluyen por los límites de la actividad utilizando dos conceptos diferentes: variables y argumentos. Mediante el uso de un ámbito jerárquico claro para las variables y argumentos "In/Out/InOut", se reduce drásticamente la complejidad del uso de datos para las actividades y la duración de los datos tiene un ámbito también automáticamente. Las actividades tienen una signatura bien definida descrita por sus argumentos. Mediante la simple inspección de una actividad, se puede determinar qué datos espera recibir y qué datos generará como consecuencia de su ejecución.  
  
 En WF3, las actividades se inicializaban cuando se creaba un flujo de trabajo. En WF4, las actividades se inicializan solo cuando se ejecutan las actividades correspondientes. Esto permite un ciclo de vida más simple de la actividad sin realizar operaciones de inicializar/anular inicialización cuando se crea una nueva instancia de flujo de trabajo, consiguiéndose de este modo una mayor eficacia.  
  
### <a name="control-flow"></a>Flujo de control  
 Como en cualquier lenguaje de programación, [!INCLUDE[wf1](../../../includes/wf1-md.md)] proporciona compatibilidad con los flujos de control para las definiciones de flujo de trabajo introduciendo un conjunto de actividades de flujo de control para la creación de secuencias, bucles, bifurcaciones y otros patrones. En WF3, cuando se necesita volver a ejecutar la misma actividad, se crea un nuevo elemento <xref:System.Workflow.ComponentModel.ActivityExecutionContext> y la actividad se clona mediante una lógica de serialización y deserialización compleja basada en <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. Normalmente, el rendimiento de los flujos de control reiterativos es mucho más lento que la ejecución de una secuencia de actividades.  
  
 WF4 trata este aspecto de forma bastante diferente. Toma la plantilla de actividad, crea un nuevo objeto ActivityInstance y lo agrega a la cola del programador. Este proceso completo solamente implica la creación explícita de objetos y es muy simple.  
  
### <a name="asynchronous-programming"></a>Programación asincrónica  
 Las aplicaciones tienen normalmente mejores niveles de rendimiento y escalabilidad con la programación asincrónica de operaciones de bloqueo de ejecución prolongada, como las operaciones de computación distribuidas o de E/S. WF4 proporciona compatibilidad asincrónica a través de los tipos de actividad base <xref:System.Activities.AsyncCodeActivity> y <xref:System.Activities.AsyncCodeActivity%601>. El runtime entiende las actividades asincrónicas de forma nativa y, por lo tanto, puede colocar automáticamente la instancia en una zona sin persistencia mientras el trabajo asincrónico está pendiente. Las actividades personalizadas pueden derivar de estos tipos para realizar el trabajo asincrónico sin retener el subproceso de programador de flujo de trabajo ni bloquear las actividades que puedan ejecutarse en paralelo.  
  
### <a name="messaging"></a>Mensajería  
 Inicialmente, WF3 tenía compatibilidad de mensajería muy limitada a través de invocaciones de eventos externos o servicios Web. En .NET 3.5, los flujos de trabajo se podían implementar como clientes de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] o exponer como servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] a través de <xref:System.Workflow.Activities.SendActivity> y <xref:System.Workflow.Activities.ReceiveActivity>. En WF4, el concepto de programación de mensajería basada en flujo de trabajo se ha fortalecido más mediante la estrecha integración de la lógica de mensajería de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en WF.  
  
 La canalización de procesamiento de mensajes unificada proporcionada en [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en .NET 4 ayuda a que los servicios de WF4 tengan un rendimiento y una escalabilidad significativamente mejores que WF3. WF4 también proporciona una compatibilidad de programación de mensajería más avanzada que puede modelar patrones de intercambio de mensajes (MEP) complejos. Los desarrolladores pueden utilizar contratos de servicio con tipos para conseguir una programación fácil o contratos de servicio sin tipos para lograr un rendimiento mejor sin pagar costos de serialización. La compatibilidad de almacenamiento en caché de canales del lado cliente mediante la clase <xref:System.ServiceModel.Activities.SendMessageChannelCache> en WF4 ayuda a los desarrolladores a compilar aplicaciones rápidas con el mínimo esfuerzo. Para obtener más información, consulte [cambiar los niveles de uso compartido de caché para las actividades de envío](../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).  
  
### <a name="declarative-programming"></a>Programación declarativa  
 WF4 proporciona un marco de programación declarativa limpio y simple para modelar los procesos y servicios de negocios. El modelo de programación admite la composición totalmente declarativa de actividades, sin código lateral, simplificando enormemente la creación del flujo de trabajo. En [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], el marco de programación declarativa basada en XAML se ha unificado en el ensamblado System.Xaml.dll único para admitir tanto WPF como WF.  
  
 En WF4, XAML proporciona una experiencia realmente declarativa y permite que la definición completa del flujo de trabajo se defina en marcado XML, haciendo referencia a actividades y tipos generados mediante el uso de .NET. Esto resultaba difícil de hacer en WF3 con formato XOML sin la participación de lógica personalizada de código subyacente. La nueva pila de XAML en .NET 4 tiene un rendimiento mucho mejor en la serialización/deserialización de artefactos de flujo de trabajo y hace que la programación declarativa sea más atractiva y sólida.  
  
### <a name="workflow-designer"></a>Diseñador de flujo de trabajo  
 La compatibilidad de la programación totalmente declarativa con WF4 impone explícitamente requisitos más exigentes para el rendimiento en tiempo de diseño de grandes flujos de trabajo. El diseñador de flujos de trabajo en WF4 tiene mejor escalabilidad para grandes flujos de trabajo que el de WF3. Con la compatibilidad de virtualización de interfaz de usuario, el diseñador puede cargar fácilmente un flujo de trabajo grande de 1000 actividades en unos segundos, mientras que es muy difícil cargar un flujo de trabajo de unos pocos cientos de actividades con el diseñador de WF3.  
  
## <a name="component-level-performance-comparisons"></a>Comparaciones de rendimiento en el nivel de componente  
 Esta sección contiene datos sobre comparaciones directas entre actividades individuales en flujos de trabajo de WF3 y WF4.  Áreas clave como la persistencia tienen un impacto más profundo en el rendimiento que los componentes de actividades individuales.  Las mejoras de rendimiento en componentes individuales de WF4 son importantes porque los componentes son ahora bastante rápidos en comparación con la lógica de orquestación codificada manualmente.  Un ejemplo de los cuales se explica en la sección siguiente: "Escenario de composición de servicio".  
  
### <a name="environment-setup"></a>Configuración de entorno  
 ![Entorno de prueba de rendimiento de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/media/wfperfenvironment.gif "WFPerfEnvironment")  
  
 Las ilustración anterior muestra la configuración de una máquina utilizada para la medición del rendimiento en el nivel de componente. Un solo servidor y cinco clientes conectados a través de una interfaz de red Ethernet de 1 Gbps. Para las mediciones fáciles, el servidor se configura para utilizar un núcleo único de un servidor de procesador dual y núcleo cuádruple basado en x86 que ejecuta Windows Server 2008. La utilización de la CPU del sistema se mantiene en casi el 100%.  
  
### <a name="test-details"></a>Detalles de las pruebas  
 <xref:System.Workflow.Activities.CodeActivity> de WF3 es probablemente la actividad más simple que se puede utilizar en un flujo de trabajo de WF3.  La actividad llama a un método en el código subyacente en que el programador de flujos de trabajo puede colocar el código personalizado.  En WF4, no hay ningún equivalente directo a <xref:System.Workflow.Activities.CodeActivity> de WF3 que proporcione la misma funcionalidad.  Observe que hay una clase base <xref:System.Activities.CodeActivity> en WF4 que no está relacionada con <xref:System.Workflow.Activities.CodeActivity> de WF3.  Se recomienda encarecidamente a los autores de flujos de trabajo que creen actividades personalizadas y compilen flujos de trabajo de solo XAML.  En las pruebas siguientes, se utiliza una actividad denominada `Comment` en lugar de un elemento <xref:System.Workflow.Activities.CodeActivity> vacío en flujos de trabajo de WF4.  El código de la actividad `Comment` es el siguiente:  
  
```  
[ContentProperty("Body")]  
    public sealed class Comment : CodeActivity  
    {  
        public Comment()  
            : base()  
        {  
        }  
  
        [DefaultValue(null)]  
        public Activity Body  
        {  
            get;  
            set;  
        }  
  
        protected override void Execute(CodeActivityContext context)  
        {  
        }  
    }  
```  
  
### <a name="empty-workflow"></a>Flujo de trabajo vacío  
 Esta prueba utiliza un flujo de trabajo de secuencia sin actividades secundarias.  
  
### <a name="single-activity"></a>Actividad única  
 El flujo de trabajo es un flujo de trabajo de secuencia que contiene una actividad secundaria.  La actividad es un elemento <xref:System.Workflow.Activities.CodeActivity> sin código en el caso de WF3 y una actividad `Comment` en el caso de WF4.  
  
### <a name="while-with-1000-iterations"></a>While con 1000 iteraciones  
 El flujo de trabajo de la secuencia contiene una actividad <xref:System.Activities.Statements.While> con una actividad secundaria en el bucle que no realiza ningún trabajo.  
  
### <a name="replicator-compared-to-parallelforeach"></a>Replicador comparado con ParallelForEach  
 <xref:System.Workflow.Activities.ReplicatorActivity> en WF3 tiene modos de ejecución paralela y secuencial.  En modo secuencial, el rendimiento de la actividad es similar a <xref:System.Workflow.Activities.WhileActivity>.  <xref:System.Workflow.Activities.ReplicatorActivity> es muy útil para la ejecución paralela.  El equivalente de WF4 es la actividad <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 En el siguiente diagrama se muestran los flujos de trabajo utilizados para esta prueba. El flujo de trabajo de WF3 está en el lado izquierdo y el flujo de trabajo de WF4 está en el derecho.  
  
 ![WF3 ReplicatorActivity y ParallelForEach de WF4](../../../docs/framework/windows-workflow-foundation/media/replicatorandparallelforeach.gif "ReplicatorAndParallelForEach")  
  
### <a name="sequential-workflow-with-five-activities"></a>Flujo de trabajo secuencial con cinco actividades  
 Esta prueba sirve para mostrar el efecto de la ejecución de varias actividades en secuencia.  Hay cinco actividades en la secuencia.  
  
### <a name="transaction-scope"></a>Ámbito de transacción  
 La prueba de ámbito de transacción difiere ligeramente de las demás pruebas en que una nueva instancia de flujo de trabajo no se crea para cada iteración.  En su lugar, el flujo de trabajo se estructura con un bucle While que contiene una actividad <xref:System.Activities.Statements.TransactionScope> que contiene a su vez una sola actividad que no realiza trabajo.  Cada ejecución de un lote de 50 iteraciones mediante el bucle While se cuenta como una operación única.  
  
### <a name="compensation"></a>Compensación  
 El flujo de trabajo de WF3 tiene una actividad compensable única denominada `WorkScope`.  La actividad simplemente implementa la interfaz <xref:System.Workflow.ComponentModel.ICompensatableActivity>:  
  
```  
class WorkScope :   
        CompositeActivity, ICompensatableActivity  
    {  
        public WorkScope() : base() { }  
  
        public WorkScope(string name)  
        {  
            this.Name = name;  
        }  
  
        public ActivityExecutionStatus Compensate(  
            ActivityExecutionContext executionContext)  
        {  
            return ActivityExecutionStatus.Closed;  
        }  
    }  
```  
  
 El destino del controlador de error es la actividad `WorkScope`. El flujo de trabajo de WF4 es igualmente simplista.  Una actividad <xref:System.Activities.Statements.CompensableActivity> tiene un cuerpo y un controlador de compensación.  Una compensación explícita es el elemento siguiente en la secuencia.  La actividad de cuerpo y la actividad de controlador de compensación son implementaciones vacías:  
  
```  
public sealed class CompensableActivityEmptyCompensation : CodeActivity  
    {  
        public CompensableActivityEmptyCompensation()  
            : base() { }  
  
        public Activity Body { get; set; }  
  
        protected override void Execute(CodeActivityContext context) { }  
    }  
    public sealed class CompensableActivityEmptyBody : CodeActivity  
    {  
        public CompensableActivityEmptyBody()  
            : base() { }  
  
        public Activity Body { get; set; }  
  
        protected override void Execute(CodeActivityContext context) { }  
    }  
```  
  
 ![Flujos de trabajo de compensación básicos de WF3 y WF](../../../docs/framework/windows-workflow-foundation/media/basiccompensationworkflows.gif "BasicCompensationWorkflows")  
  
 Figura 2: flujos de trabajo de compensación básicos de WF3 (izquierda) y WF4 (derecha)  
  
### <a name="performance-test-results"></a>Resultados de pruebas de rendimiento  
 ![Resultados de pruebas de rendimiento](../../../docs/framework/windows-workflow-foundation/media/performancedata.gif "rendimiento")  
  
 ![Gráfico de datos de prueba de rendimiento](../../../docs/framework/windows-workflow-foundation/media/performancetestchart.gif "PerformanceTestChart")  
  
 Todas las pruebas se miden en flujos de trabajo por segundo con la excepción de la prueba de ámbito de transacción.  Como se puede ver más arriba, el rendimiento del runtime de [!INCLUDE[wf1](../../../includes/wf1-md.md)] ha mejorado globalmente, sobre todo en áreas que requieren varias ejecuciones de la misma actividad como el bucle While.  
  
## <a name="service-composition-scenario"></a>Escenario de composición de servicio  
 Como se muestra en la sección anterior, "comparaciones de rendimiento de nivel de componente" se ha producido una reducción significativa en la sobrecarga entre WF3 y WF4.  Los servicios de flujo de trabajo de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] pueden casi igualar ahora el rendimiento de los servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] codificados a mano, pero siguen teniendo todas las ventajas del tiempo de ejecución de [!INCLUDE[wf1](../../../includes/wf1-md.md)].  Este escenario de prueba compara un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] con un servicio de flujo de trabajo de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en WF4.  
  
### <a name="online-store-service"></a>Servicio de tienda en línea  
 Uno de los puntos fuertes de Windows Workflow Foundation es la capacidad de crear procesos mediante varios servicios.  En este ejemplo, hay un servicio de tienda en línea que orquesta dos llamadas de servicio para realizar un pedido.  El primer paso es validar el pedido utilizando un servicio de validación de pedidos.  El segundo paso es rellenar el pedido utilizando un servicio de almacén.  
  
 Los dos servicios back-end, el servicio de validación de pedidos y el servicio de almacén, siguen siendo los mismos en ambas pruebas.  La parte que cambia es el servicio de tienda en línea que realiza la orquestación.  En un caso, el servicio se codifica manualmente como un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  En el otro caso, el servicio se escribe como un servicio de flujo de trabajo de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en WF4. Las características específicas de [!INCLUDE[wf1](../../../includes/wf1-md.md)], como el seguimiento y la persistencia, se desactivan para esta prueba.  
  
### <a name="environment"></a>Entorno  
 ![Entorno de prueba de rendimiento de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/media/wfperfenvironment.gif "WFPerfEnvironment")  
  
 Las solicitudes del cliente se realizan al servicio de tienda en línea a través de HTTP desde varios equipos.  Un equipo único hospeda los tres servicios.  La capa de transporte entre el servicio de tienda en línea y los servicios back-end es TCP o HTTP.  La medición de operaciones por segundo se basa en el número de llamadas a `PurchaseOrder` completadas realizadas al servicio de tienda en línea.  La agrupación de canales es una nueva característica disponible en WF4.  En la parte de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] de esta prueba, la agrupación de canales no se proporciona para su uso inmediato, por lo que se utilizó una implementación codificada manualmente de una técnica de agrupación simple en el servicio de tienda en línea.  
  
### <a name="performance"></a>Rendimiento  
 ![Gráfico de rendimiento del servicio de tienda en línea](../../../docs/framework/windows-workflow-foundation/media/onlinestoreperfgraph.gif "OnlineStorePerfGraph")  
  
 La conexión de los servicios TCP back-end sin agrupación de canales hace que el servicio de [!INCLUDE[wf1](../../../includes/wf1-md.md)] tenga un impacto del 17,2% en el rendimiento.  Con la agrupación de canales, la reducción es de aproximadamente el 23,8%.  Para HTTP, el impacto es mucho menor: el 4,3% sin agrupación y el 8,1% con agrupación.  También es importante tener en cuenta que la agrupación de canales proporciona muy pocas ventajas cuando se utiliza HTTP.  
  
 Aunque hay una sobrecarga del runtime de WF4 en comparación con un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] codificado manualmente en esta prueba, se pudo considerar un escenario más desfavorable.  Los dos servicios back-end de esta prueba realizan muy poco trabajo.  En un escenario real de extremo a extremo, estos servicios realizarían operaciones más costosas, como llamadas de base de datos, con lo que el impacto en el rendimiento de la capa de transporte sería menos importante.  Esto, más las ventajas de las características disponibles en WF4, hace de Workflow Foundation una opción viable para crear servicios de orquestación.  
  
## <a name="key-performance-considerations"></a>Consideraciones clave de rendimiento  
 Las áreas de características de esta sección, con la excepción de la interoperabilidad, han cambiado radicalmente entre WF3 y WF4.  Esto afecta al diseño de las aplicaciones de flujo de trabajo, así como al rendimiento.  
  
#### <a name="workflow-activation-latency"></a>Latencia de activación de flujo de trabajo  
 En una aplicación de servicio de flujo de trabajo de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], la latencia para iniciar un nuevo flujo de trabajo o cargar un flujo de trabajo existente es tan importante como puede ser el bloqueo.  Este caso de prueba mide un host XOML de WF3 en comparación con un host XAMLX de WF4 en un escenario típico.  
  
##### <a name="environment-setup"></a>Configuración de entorno  
 ![Configuración del entorno para pruebas de latencia y rendimiento](../../../docs/framework/windows-workflow-foundation/media/latencyandthroughputenvironment.gif "LatencyAndThroughputEnvironment")  
  
##### <a name="test-setup"></a>Configuración de prueba  
 En el escenario, un equipo cliente se pone en contacto con un servicio de flujo de trabajo de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] utilizando la correlación basada en contexto.  La correlación basada en contexto requiere un enlace de contexto especial y utiliza un encabezado de contexto o una cookie para relacionar los mensajes con la instancia de flujo de trabajo correcta.  Tiene una mejora de rendimiento ya que el identificador de la correlación se encuentra en el encabezado del mensaje, por lo que no es necesario el análisis del cuerpo del mensaje. [!INCLUDE[crabout](../../../includes/crabout-md.md)] consulta de correlación del contexto [correlación de intercambio de contexto](../../../docs/framework/wcf/feature-details/context-exchange-correlation.md)  
  
 El servicio creará un nuevo flujo de trabajo con la solicitud y enviará una respuesta inmediata para que la medición de la latencia no incluya el tiempo empleado en la ejecución del flujo de trabajo.  El flujo de trabajo de WF3 es XOML con un código subyacente y el flujo de trabajo de WF4 es totalmente XAML.  El flujo de trabajo de WF4 tiene el siguiente aspecto:  
  
 ![Ámbito WF 4 correlación](../../../docs/framework/windows-workflow-foundation/media/correlationscopeworkflow.gif "CorrelationScopeWorkflow")  
  
 La actividad <xref:System.ServiceModel.Activities.Receive> crea la instancia del flujo de trabajo.  Un valor pasado al mensaje recibido se refleja en el mensaje de respuesta.  Una secuencia que sigue a la respuesta contiene el resto del flujo de trabajo.  En el caso anterior, solo se muestra una actividad Comment.  El número de actividades Comment se cambia para simular la complejidad del flujo de trabajo.  Una actividad de comentario es equivalente a una <xref:System.Workflow.Activities.CodeActivity> de WF3 que no realiza ningún trabajo. [!INCLUDE[crabout](../../../includes/crabout-md.md)] la actividad de comentario, vea la sección "comparación de rendimiento de nivel de componente" anteriormente en este artículo.  
  
##### <a name="test-results"></a>Resultados de pruebas  
 ![Resultados de latencia](../../../docs/framework/windows-workflow-foundation/media/latencyresultsgraph.gif "LatencyResultsGraph")  
  
 Figura 3: latencia en frío y en caliente para los servicios de flujo de trabajo de WCF  
  
 En el gráfico anterior, frío hace referencia al caso en que no hay un <xref:System.ServiceModel.WorkflowServiceHost> existente para el flujo de trabajo dado.  En otras palabras, la latencia en frío se produce cuando el flujo de trabajo se utiliza por primera vez y el XOML o el XAML deben compilarse.  La latencia en caliente es el tiempo necesario para crear una nueva instancia de flujo de trabajo cuando el tipo de flujo de trabajo ya se ha compilado.  La complejidad del flujo de trabajo apenas si sufre diferencias en el caso de WF4, pero tiene una progresión lineal en el caso de WF3.  
  
#### <a name="correlation-throughput"></a>Rendimiento de la correlación  
 WF4 introduce una nueva característica de correlación basada en contenido.  WF3 proporcionaba solamente correlación basada en contexto.  La correlación basada en contexto solo se podía realizar en enlaces de canal de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] específicos.  El identificador del flujo de trabajo se inserta en el encabezado del mensaje cuando se utilizan estos enlaces.  El runtime de WF3 solo podía identificar un flujo de trabajo por su identificador.  Con correlación basada en contenido, el autor del flujo de trabajo puede crear una clave de correlación fuera una parte relevante de datos, como un número de cuenta o el identificador de cliente [!INCLUDE[crabout](../../../includes/crabout-md.md)] correlación basada en contenido, vea [una correlación basada en contenido](../../../docs/framework/wcf/feature-details/content-based-correlation.md).  
  
 En la correlación basada en contexto hay un incremento de rendimiento ya que la clave de correlación se encuentra en el encabezado del mensaje.  La clave se puede leer desde el mensaje sin que sea necesaria la deserialización/copia del mensaje.  En la correlación basada en contenido, la clave de correlación se almacena en el cuerpo del mensaje.  Se utiliza una expresión XPath para buscar la clave.  El costo de este procesamiento adicional depende del tamaño del mensaje, la profundidad de la clave en el cuerpo y el número de claves.  Esta prueba compara la correlación basada en contexto con la correlación basada en contenido y también muestra el descenso del rendimiento cuando se utilizan varias claves.  
  
#### <a name="environment-setup"></a>Configuración de entorno  
 ![Entorno de prueba de rendimiento de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/media/wfperfenvironment.gif "WFPerfEnvironment")  
  
#### <a name="test-setup"></a>Configuración de prueba  
 ![Prueba de flujo de trabajo de rendimiento de correlación](../../../docs/framework/windows-workflow-foundation/media/correlationthroughputworkflow.gif "CorrelationThroughputWorkflow")  
  
 El flujo de trabajo mostrado anteriormente es el mismo que se usa en la sección "Persistencia" más adelante.  Para las pruebas de la correlación sin persistencia no hay ningún proveedor de persistencia instalado en el runtime.  La correlación se produce en dos lugares: CreateOrder y CompleteOrder.  
  
#### <a name="test-results"></a>Resultados de pruebas  
 ![Rendimiento de la correlación](../../../docs/framework/windows-workflow-foundation/media/correlationthroughputgraph.gif "CorrelationThroughputGraph")  
  
 Este gráfico muestra una disminución del rendimiento cuando aumenta el número de claves utilizadas en la correlación basada en contenido.  La similitud de las curvas entre TCP y HTTP indica la sobrecarga asociada a estos protocolos.  
  
#### <a name="correlation-with-persistence"></a>Correlación con persistencia  
 Con un flujo de trabajo conservado, la presión de CPU debida a la correlación basada en contexto pasa del runtime de flujo de trabajo a la base de datos SQL.  Los procedimientos almacenados en el proveedor de persistencia de SQL realizan el trabajo de hacer coincidir las claves para buscar el flujo de trabajo adecuado.  
  
 ![Resultados de correlación y persistencia](../../../docs/framework/windows-workflow-foundation/media/correlationandpersistencegraph.gif "CorrelationAndPersistenceGraph")  
  
 La correlación basada en contexto es todavía más rápida que la correlación basada en contenido.  Sin embargo, la diferencia es menos pronunciada, ya que la persistencia tiene un impacto mayor en el rendimiento que la correlación.  
  
### <a name="complex-workflow-throughput"></a>Rendimiento de un flujo de trabajo complejo  
 La complejidad de un flujo de trabajo no se mide solamente por el número de actividades.  Las actividades compuestas pueden contener muchas actividades secundarias y esas actividades secundarias también pueden ser actividades compuestas.  Según aumenta el número de niveles de anidamiento, también aumenta el número de actividades que pueden estar actualmente en estado de ejecución y el número de variables que pueden estar en este estado.  Esta prueba compara el rendimiento entre WF3 y WF4 cuando se ejecutan flujos de trabajo complejos.  
  
### <a name="test-setup"></a>Configuración de prueba  
 Estas pruebas se ejecutaron en un equipo de 4 vías con procesador Intel Xeon X5355, de 2,66 GHz y 4 GB de RAM que ejecuta Windows Server 2008 basado en x64.  El código de prueba se ejecuta en un proceso único con un subproceso por núcleo para alcanzar el 100% de utilización de la CPU.  
  
 Los flujos de trabajo generados para esta prueba tienen dos variables principales: la profundidad y el número de actividades en cada secuencia.  Cada nivel de profundidad incluye una actividad paralela, un bucle While, decisiones, asignaciones y secuencias.  En el diseñador de WF4 que se muestra más abajo, se representa el diagrama de flujo de nivel superior.  Cada actividad de diagrama de flujo es similar al diagrama de flujo principal.  Puede ser útil pensar en un fractal al representar este flujo de trabajo, donde la profundidad se limita a los parámetros de la prueba.  
  
 El número de actividades en una prueba dada viene determinado por la profundidad y el número de actividades por secuencia.  La siguiente ecuación calcula el número de actividades en la prueba de WF4:  
  
 ![Ecuación para calcular el número de actividades](../../../docs/framework/windows-workflow-foundation/media/numberofactivitiesequation.gif "NumberOfActivitiesEquation")  
  
 El número de actividades en la prueba de WF3 se puede calcular con una ecuación algo diferente debido a una secuencia adicional:  
  
 ![Ecuación para calcular el número de actividades](../../../docs/framework/windows-workflow-foundation/media/w3numberofactivitiesequation.gif "W3NumberOfActivitiesEquation")  
  
 Donde d es la profundidad y a es el número de actividades por secuencia.  La lógica que subyace a estas ecuaciones es que la primera constante, multiplicada por a, es el número de secuencias y la segunda constante es el número estático de actividades en el nivel actual.  Hay tres actividades secundarias de diagrama de flujo en cada diagrama de flujo.  En el nivel de profundidad inferior estos diagramas de flujo están vacíos, pero en los demás niveles hay copias del diagrama de flujo principal.  El número de actividades en la definición de flujo de trabajo de cada variación de prueba se indica en la siguiente tabla:  
  
 ![Compara el número de actividades que se utilizan en cada prueba](../../../docs/framework/windows-workflow-foundation/media/comparechart.gif "CompareChart")  
  
 El número de actividades en la definición de flujo de trabajo aumenta claramente con cada nivel de profundidad.  Pero solo una ruta por punto de decisión se ejecuta en una instancia de flujo de trabajo dada, por lo que solo se ejecuta un pequeño subconjunto de las actividades reales.  
  
 ![Flujo de trabajo complejo](../../../docs/framework/windows-workflow-foundation/media/complexworkflowthroughputworkflow.gif "ComplexWorkflowThroughputWorkflow")  
  
 Se creó un flujo de trabajo equivalente para WF3. El diseñador de WF3 muestra el flujo de trabajo completo en el área de diseño en lugar de anidarlo; por consiguiente, es demasiado extenso para mostrarlo en este tema. A continuación se muestra un fragmento de código del flujo de trabajo.  
  
 ![WF3 Flujo de trabajo](../../../docs/framework/windows-workflow-foundation/media/wf3workflow.gif "WF3Workflow")  
  
 Para ejercer el anidamiento en un caso extremo, otro flujo de trabajo que forma parte de esta prueba utiliza 100 secuencias anidadas.  En la secuencia más interna hay una actividad `Comment` o <xref:System.Workflow.Activities.CodeActivity> única.  
  
 ![Anidar secuencias](../../../docs/framework/windows-workflow-foundation/media/nestedsequencewf.gif "NestedSequenceWF")  
  
 El seguimiento y la persistencia no se utilizan como parte de esta prueba.  
  
### <a name="test-results"></a>Resultados de pruebas  
 ![Gráfico de rendimiento](../../../docs/framework/windows-workflow-foundation/media/testresults1.gif "TestResults1")  
  
 Incluso con flujos de trabajo complejos con gran profundidad y un alto número de actividades, los resultados del rendimiento son coherentes con otras cifras mostradas anteriormente en este artículo.  El rendimiento de WF4 es más rápido en órdenes de magnitud y tiene que compararse en una escala logarítmica.  
  
### <a name="memory"></a>Memoria  
 La sobrecarga de la memoria de Windows Workflow Foundation se mide en dos áreas clave: la complejidad del flujo de trabajo y el número de definiciones de flujo de trabajo.  Las mediciones de memoria se tomaron en una estación de trabajo de 64 bits con Windows 7.  Hay muchas maneras de obtener la medición del tamaño del conjunto como supervisión de contadores de rendimiento, sondeando Environment.WorkingSet o mediante una herramienta como VMMap disponible en trabajo [VMMap](http://technet.microsoft.com/sysinternals/dd535533.aspx). Se utilizó una combinación de métodos para obtener y comprobar los resultados de cada prueba.  
  
### <a name="workflow-complexity-test"></a>Prueba de complejidad de flujo de trabajo  
 La prueba de complejidad de flujo de trabajo mide la diferencia del espacio de trabajo basándose en la complejidad del flujo de trabajo.  Además de los flujos de trabajo complejos utilizados en la sección anterior, las nuevas variaciones se agregan para cubrir dos casos básicos: un flujo de trabajo de una sola actividad y una secuencia con 1000 actividades.  Para estas pruebas, los flujos de trabajo se inicializan y ejecutan hasta su finalización en un bucle serie único durante un período de un minuto.  Cada variación de prueba se ejecuta tres veces y los datos registrados son la media de estas tres ejecuciones.  
  
 Las dos nuevas pruebas básicas tienen flujos de trabajo parecidos a los que se muestran a continuación:  
  
 ![Flujos de trabajo complejos](../../../docs/framework/windows-workflow-foundation/media/complexworkflowboth.gif "ComplexWorkflowBoth")  
  
 En el flujo de trabajo de WF3 mostrado más arriba, se utilizan actividades <xref:System.Workflow.Activities.CodeActivity> vacías.  El flujo de trabajo de WF4 anterior utiliza actividades `Comment`.  La actividad `Comment` se describió en la sección Comparaciones de rendimiento en el nivel de componente, anteriormente en este artículo.  
  
 ![Gráfico de uso de memoria](../../../docs/framework/windows-workflow-foundation/media/complexmemoryusage.gif "ComplexMemoryUsage")  
  
 Una de las tendencias claras que se observan en este gráfico es que el anidamiento tiene un impacto relativamente mínimo en el uso de memoria tanto en WF3 como en WF4.  El impacto en la memoria más significativo procede del número de actividades en un flujo de trabajo determinado.  Dados los datos de las variaciones de la secuencia 1000, la secuencia 5 de profundidad compleja 5 y la secuencia 1 de profundidad  compleja 7, es evidente que, a partir de la cifra de mil actividades, el aumento del uso de memoria se hace más apreciable.  En el caso extremo (secuencia 1 de profundidad 7) donde hay 29.000 actividades aproximadamente, WF4 utiliza casi un 79% menos de memoria que WF3.  
  
### <a name="multiple-workflow-definitions-test"></a>Prueba de varias definiciones de flujo de trabajo  
 La medición de memoria por cada definición de flujo de trabajo se divide en dos pruebas diferentes debido a las opciones disponibles para hospedar flujos de trabajo en WF3 y WF4.  La ejecución de estas pruebas se diferencia de la ejecución de la prueba de complejidad de flujo de trabajo en que se crean instancias de un flujo de trabajo determinado y se ejecutan solo una vez por definición.  Esto se debe a que la definición de flujo de trabajo y su host permanecen en memoria durante la vigencia de AppDomain.  La memoria utilizada en la ejecución de una instancia de flujo de trabajo determinada se debe limpiar durante la recolección de elementos no utilizados.  La guía de migración de WF4 contiene información más detallada acerca de las opciones de hospedaje. Para obtener más información, consulte [manual de migraciones de WF: hospedaje del flujo de trabajo](http://go.microsoft.com/fwlink/?LinkID=153313).  
  
 La creación de muchas definiciones de flujo de trabajo para una prueba de definición de flujo de trabajo se puede realizar de varias maneras.  Por ejemplo, se puede utilizar generación de código para crear un conjunto de 1000 flujos de trabajo idénticos excepto en el nombre y guardar cada uno de ellos en archivos independientes.  Se adoptó este enfoque para la prueba hospedada en consola.  En WF3, se utilizó la clase <xref:System.Workflow.Runtime.WorkflowRuntime> para ejecutar las definiciones de flujo de trabajo.  WF4 puede usar <xref:System.Activities.WorkflowApplication> para crear una única instancia de flujo de trabajo o usar directamente <xref:System.Activities.WorkflowInvoker> para ejecutar la actividad como si fuera una llamada al método.  <xref:System.Activities.WorkflowApplication> es un host de una única instancia de flujo de trabajo y tiene una paridad de características más cercana a <xref:System.Workflow.Runtime.WorkflowRuntime> de modo que se usa en esta prueba.  
  
 Cuando se hospedan flujos de trabajo en IIS, es posible utilizar <xref:System.Web.Hosting.VirtualPathProvider> para crear un nuevo <xref:System.ServiceModel.WorkflowServiceHost> en lugar de generar todos los archivos XAMLX o XOML.  El <xref:System.Web.Hosting.VirtualPathProvider> gestiona la solicitud entrante y responde con un "archivo virtual" que se pueden cargar desde una base de datos o, en este caso, se generan sobre la marcha.  Por consiguiente, no es necesario crear 1000 archivos físicos.  
  
 Las definiciones de flujo de trabajo utilizadas en la prueba de consola fueron flujos de trabajo secuenciales simples con una sola actividad.  Esta actividad única fue una actividad <xref:System.Workflow.Activities.CodeActivity> vacía en el caso de WF3 y una actividad `Comment` en el caso de WF4.  El caso hospedado en IIS utilizó flujos de trabajo que empiezan en la recepción de un mensaje y finalizan en el envío de una respuesta:  
  
 ![Servicios de flujo de trabajo de WF3 y WF4](../../../docs/framework/windows-workflow-foundation/media/receiveworkflowboth.gif "ReceiveWorkflowBoth")  
  
 Figura 4: flujo de trabajo de WF3 con ReceiveActivity y flujo de trabajo de WF4 con patrón de solicitud/respuesta  
  
 En la siguiente tabla se muestra el incremento de espacio de trabajo entre una definición de flujo de trabajo única y 1001 definiciones:  
  
|Opciones de hospedaje|Incremento de espacio de trabajo de WF3|Incremento de espacio de trabajo de WF4|  
|---------------------|---------------------------|---------------------------|  
|Flujos de trabajo hospedados en aplicación de consola|18 MB|9 MB|  
|Servicios de flujo de trabajo hospedados en IIS|446 MB|364 MB|  
  
 El hospedaje de definiciones de flujo de trabajo en IIS consume mucha más memoria debido a <xref:System.ServiceModel.WorkflowServiceHost>, los artefactos detallados del servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y la lógica de procesamiento de mensajes asociada al host.  
  
 Para el hospedaje en consola en WF3 los flujos de trabajo se implementaron en código, en lugar de XOML.  En WF4, la opción predeterminada es usar XAML.  El XAML se almacena como un recurso incrustado en el ensamblado y se compila en tiempo de ejecución para proporcionar la implementación del flujo de trabajo.  Hay alguna sobrecarga asociada a este proceso.  Para realizar una comparación objetiva entre WF3 y WF4, se utilizaron flujos de trabajo codificados en lugar de XAML.  A continuación se muestra un ejemplo de uno de los flujos de trabajo de WF4:  
  
```  
public class Workflow1 : Activity  
{  
    protected override Func<Activity> Implementation  
    {  
        get  
        {  
            return new Func<Activity>(() =>  
            {  
                return new Sequence  
                {  
                    Activities = {  
                        new Comment()  
                    }  
                };  
            });  
        }  
        set  
        {  
            base.Implementation = value;  
        }  
    }  
}  
```  
  
 Hay otros muchos factores que pueden afectar al consumo de memoria. Sigue siendo aplicable el mismo consejo para todos los programas administrados.  En entornos hospedados en IIS, el objeto <xref:System.ServiceModel.WorkflowServiceHost> creado para una definición de flujo de trabajo permanece en memoria hasta que se recicla el grupo de aplicaciones.  Debe tenerse en cuenta este aspecto al escribir extensiones.  Además, es mejor evitar variables "globales" (variables cuyo ámbito es el flujo de trabajo completo) y limitar el ámbito de las variables siempre que sea posible.  
  
## <a name="workflow-runtime-services"></a>Servicios de runtime de flujo de trabajo  
  
### <a name="persistence"></a>Persistencia  
 WF3 y WF4 se proporcionan con un proveedor de persistencia de SQL.  El proveedor de persistencia de SQL de WF3 es una implementación simple que serializa la instancia de flujo de trabajo y la almacena en un blob.  Por esta razón, el rendimiento de este proveedor depende en gran medida del tamaño de la instancia de flujo de trabajo.  En WF3, el tamaño de las instancias podía aumentar por muchas razones, como se ha analizado anteriormente en este documento.  Muchos clientes prefieren no utilizar el proveedor de persistencia de SQL predeterminado porque el almacenamiento de una instancia serializada en una base de datos no proporciona visibilidad en el estado del flujo de trabajo.  Para encontrar un flujo de trabajo determinado sin conocer su identificador, se tendría que deserializar cada instancia persistente y examinar el contenido.  Muchos desarrolladores prefieren escribir sus propios proveedores de persistencia para superar este obstáculo.  
  
 El proveedor de persistencia de SQL de WF4 ha intentado solucionar algunas de estas cuestiones.  Las tablas de persistencia exponen cierto tipo de información como los marcadores activos y las propiedades que se pueden convertir.  La nueva característica de correlación basada en contenido en WF4 no se comportaría correctamente utilizando el enfoque de persistencia de SQL de WF3, que ha impulsado algún cambio en la organización de la instancia de flujo de trabajo persistente.  Esto hace que el trabajo del proveedor de persistencia sea más complejo y provoca un esfuerzo adicional en la base de datos.  
  
### <a name="environment-setup"></a>Configuración de entorno  
 ![Entorno de prueba de rendimiento de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/media/wfperfenvironment.gif "WFPerfEnvironment")  
  
### <a name="test-setup"></a>Configuración de prueba  
 Incluso con un conjunto de características mejorado y un control de simultaneidad superior, el proveedor de persistencia de SQL en WF4 es más rápido que el proveedor en WF3.  Para ilustrar esta afirmación, a continuación se comparan dos flujos de trabajo que realizan fundamentalmente las mismas operaciones en WF3 y WF4.  
  
 ![Los flujos de trabajo de persistencia](../../../docs/framework/windows-workflow-foundation/media/persistworkflow.gif "PersistWorkflow")  
  
 Figura 5: flujo de trabajo de persistencia en WF3 (izquierda) y WF4 (derecha)  
  
 Los dos flujos de trabajo los crea un mensaje recibido.  Después de enviar una respuesta inicial, el flujo de trabajo se conserva.  En el caso de WF3, se utiliza una actividad <xref:System.Workflow.ComponentModel.TransactionScopeActivity> vacía para iniciar la persistencia.  El mismo se puede lograr en WF3 marcando una actividad como "conservar al cerrar".  Un segundo mensaje correlacionado completa el flujo de trabajo.  Los flujos de trabajo se conservan pero no se descargan.  
  
### <a name="test-results"></a>Resultados de pruebas  
 ![Persistencia del rendimiento](../../../docs/framework/windows-workflow-foundation/media/throughputpersistence.gif "ThroughputPersistence")  
  
 Cuando el transporte entre el cliente y el nivel intermedio es HTTP, la persistencia en WF4 mejora 2,6 veces más.  El transporte TCP aumenta ese valor hasta 3 veces más.  En todos los casos, la utilización de la CPU en el nivel intermedio es del 98% o un valor superior.  La razón de que el rendimiento de WF4 sea mayor se debe a que el runtime de flujo de trabajo es más rápido.  El tamaño de la instancia serializada es bajo en ambos casos y no es un elemento de gran contribución en esta situación.  
  
 Los flujos de trabajo de WF4 y WF3 en esta prueba utilizan una actividad para indicar explícitamente cuándo debe producirse la persistencia.  Esto tiene la ventaja de que el flujo de trabajo se conserva sin descargarlo.  En WF3, también es posible la persistencia utilizando la característica <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A>, pero en este caso se descarga la instancia de flujo de trabajo de la memoria.  Si un desarrollador que utiliza WF3 desea asegurarse de que un flujo de trabajo se conserva en determinados puntos, tiene que modificar la definición de flujo de trabajo o pagar el costo de descargar y volver a cargar la instancia de flujo de trabajo.  Una nueva característica de WF4 hace posible la persistencia sin descargar: <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A>.  Esta característica permite que la instancia de flujo de trabajo se conserve en estado inactivo, pero permanezca en memoria hasta que se satisfaga el umbral de <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> o se reanude la ejecución.  
  
 Observe que el proveedor de persistencia de SQL de WF4 realiza más trabajo en el nivel de base de datos.  La base de datos SQL puede convertirse en un cuello de botella, por lo que es importante supervisar el uso de CPU y disco en ella.  Asegúrese de incluir los siguientes contadores de rendimiento de la base de datos SQL al realizar la prueba de rendimiento de las aplicaciones de flujo de trabajo:  
  
-   PhysicalDisk\\tiempo de lectura de disco %  
  
-   PhysicalDisk\\% de tiempo de disco  
  
-   PhysicalDisk\\tiempo de escritura en disco de %  
  
-   PhysicalDisk\\% promedio Longitud de cola de disco  
  
-   PhysicalDisk\Avg. Longitud de cola de lectura de disco  
  
-   PhysicalDisk\Avg. Longitud de cola de escritura de disco  
  
-   Disco físico\Longitud de cola de disco actual  
  
-   Información del procesador\\% de tiempo de procesador  
  
-   Bloqueos temporales de SQL\Media de tiempo de espera de bloqueo temporal (ms)  
  
-   Bloqueos temporales de SQL\Esperas de bloqueo temporal por segundo  
  
### <a name="tracking"></a>Seguimiento  
 El seguimiento de flujo de trabajo se puede utilizar para realizar el seguimiento del progreso de un flujo de trabajo.  La información incluida en los eventos de seguimiento la determina un perfil de seguimiento.  Cuanto más complejo sea el perfil de seguimiento, más costoso será el seguimiento.  
  
 WF3 se proporcionó con un servicio de seguimiento basado en SQL.  Este servicio podía funcionar en modo por lotes y en modo sin lotes.  En el modo sin lotes, los eventos de seguimiento se escriben directamente en la base de datos.  En modo por lotes, los eventos de seguimiento se recopilan en el mismo lote como estado de instancia de flujo de trabajo.  El modo por lotes tiene el máximo rendimiento para la gama más amplia de diseños de flujo de trabajo.  Sin embargo, el procesamiento por lotes puede tener un impacto negativo en el rendimiento si el flujo de trabajo ejecuta muchas actividades sin persistencia y se realiza un seguimiento de esas actividades.  Esto sucedería normalmente en los bucles y la mejor manera de evitar este escenario es diseñar bucles grandes para que contengan un punto de persistencia.  La introducción de un punto de persistencia en un bucle también puede afectar negativamente al rendimiento, por lo que es importante medir los costos de cada uno y lograr un equilibrio.  
  
 WF4 no se proporciona con un servicio de seguimiento de SQL.  El registro de la información de seguimiento en una base de datos SQL se puede controlar mejor desde un servidor de aplicaciones que si está integrado en [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Por lo tanto, el seguimiento de SQL lo controla ahora AppFabric.  El proveedor de seguimiento para uso inmediato en WF4 está basado en el Seguimiento de eventos para Windows (ETW).  
  
 ETW es un sistema de eventos de baja latencia en el nivel de kernel integrado en Windows.  Utiliza un modelo de proveedor/consumidor que permite que solo exista sanción en el seguimiento de eventos cuando haya realmente un consumidor.  Además de los eventos de kernel como procesador, disco, memoria y uso de red, muchas aplicaciones también se benefician de las ventajas de ETW.  Los eventos ETW son más eficaces que los contadores de rendimiento porque los eventos se pueden personalizar para la aplicación.  Un evento puede contener texto, como un identificador de flujo de trabajo o un mensaje informativo.  Además, los eventos se categorizan con máscaras de bits, por lo que la utilización de un determinado subconjunto de eventos tendrá un impacto menor en el rendimiento que la captura de todos los eventos.  
  
 Estas son algunas de las ventajas del enfoque de utilizar ETW en lugar de SQL para el seguimiento:  
  
-   La recopilación de eventos de seguimiento se puede separar a otro proceso.  Esto proporciona mayor flexibilidad en la forma de grabar los eventos.  
  
-   Los eventos de seguimiento ETW se combinan fácilmente con los eventos ETW de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] u otros proveedores de ETW tales como un proveedor de kernel o SQL Server.  
  
-   Los autores de flujos de trabajo no necesitan modificar un flujo de trabajo para trabajar mejor con una implementación de seguimiento en particular, como el modo por lotes del servicio de seguimiento de SQL de WF3.  
  
-   Un administrador puede activar o desactivar el seguimiento sin reciclar el proceso de host.  
  
 Las ventajas en cuanto a rendimiento para el seguimiento ETW plantean una desventaja.  Los eventos ETW se pueden perder si el sistema está sometido a una intensa presión de recursos.  El procesamiento de eventos no puede bloquear la ejecución normal de programas y, por consiguiente, no se garantiza que todos los eventos ETW se difundan a sus suscriptores.  Esto hace que el seguimiento ETW sea apropiado para la supervisión de estado pero no para el proceso de auditoría.  
  
 WF4 no tiene un proveedor de seguimiento de SQL, pero AppFabric sí lo tiene.  El enfoque de seguimiento de SQL de AppFabric es la suscripción a eventos ETW con un servicio de Windows que procesa por lotes los eventos y los escribe en una tabla SQL diseñada para inserciones rápidas.  Un trabajo independiente descarga los datos de esta tabla y los reforma en tablas de informes que se pueden ver en el panel de AppFabric.  Esto significa que un lote de eventos de seguimiento se controla con independencia del flujo de trabajo del que procede y, por consiguiente, no tiene que esperar un punto de persistencia antes de su grabación.  
  
 Los eventos ETW se pueden grabar con herramientas como logman o xperf.  El archivo ETL compacto puede verse con una herramienta como xperfview o convertirse a un formato más legible, como XML, con tracerpt.  En WF3, la única opción para obtener los eventos de seguimiento sin una base de datos SQL es crear un servicio de seguimiento personalizado. [!INCLUDE[crabout](../../../includes/crabout-md.md)] ETW, vea [servicios WCF y seguimiento de eventos para Windows](../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md) y [seguimiento de eventos para Windows](http://msdn.microsoft.com/library/ff190903.aspx\)).  
  
 La habilitación del seguimiento de flujo de trabajo influirá en el rendimiento de diversas maneras.  El banco de pruebas que figura más abajo utiliza la herramienta logman para usar los eventos de seguimiento de ETW y grabarlos en un archivo ETL.  El costo del seguimiento de SQL en AppFabric no pertenece al ámbito de este artículo.  El perfil de seguimiento básico, que también se utiliza en AppFabric, se muestra en este banco de pruebas.  También se incluye el costo de realizar solamente el seguimiento de los eventos de supervisión de estado.  Estos eventos son útiles para la solución de problemas y la determinación del rendimiento medio del sistema.  
  
### <a name="environment-setup"></a>Configuración de entorno  
 ![Entorno de prueba de rendimiento de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/media/wfperfenvironment.gif "WFPerfEnvironment")  
  
### <a name="test-results"></a>Resultados de pruebas  
 ![Costo de la traza de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/media/workflowtracingcost.gif "WorkflowTracingCost")  
  
 La supervisión de estado tiene un impacto en el rendimiento de un 3%, aproximadamente.  El costo del perfil básico se sitúa en torno al 8%.  
  
## <a name="interop"></a>Interop  
 WF4 es prácticamente una nueva escritura completa de [!INCLUDE[wf1](../../../includes/wf1-md.md)] y, por consiguiente, los flujos de trabajo y actividades de WF3 no son directamente compatibles con WF4.  Muchos clientes que adoptaron pronto Windows Workflow Foundation tendrán definiciones de flujo de trabajo internas o de otro fabricante y actividades personalizadas para WF3.  Una forma de facilitar la transición a WF4 es utilizar la actividad Interop, que puede ejecutar actividades de WF3 desde un flujo de trabajo de WF4.  Se recomienda que la actividad <xref:System.Activities.Statements.Interop> solo se use cuando sea necesario. [!INCLUDE[crabout](../../../includes/crabout-md.md)] migrar a WF4 desproteger la [Guía de migración de WF4](http://go.microsoft.com/fwlink/?LinkID=153313).  
  
### <a name="environment-setup"></a>Configuración de entorno  
 ![Entorno de prueba de rendimiento de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/media/wfperfenvironment.gif "WFPerfEnvironment")  
  
### <a name="test-results"></a>Resultados de pruebas  
 En la tabla siguiente se muestran los resultados de ejecutar un flujo de trabajo que contiene cinco actividades en una secuencia en varias configuraciones.  
  
|Prueba|Rendimiento (flujos de trabajo/segundo)|  
|----------|-----------------------------------|  
|Secuencia de WF3 en runtime de WF3|1,576|  
|Secuencia de WF3 en runtime de WF4 utilizando Interop|2,745|  
|Secuencia de WF4|153,582|  
  
 Se observa un aumento notable de rendimiento cuando se utiliza Interop en WF3 directamente.  Sin embargo, cuando se compara con las actividades de WF4, el aumento es insignificante.  
  
## <a name="summary"></a>Resumen  
 Las inversiones relevantes en rendimiento para WF4 han dado buenos resultados en muchas áreas cruciales.  El rendimiento de cada componente de flujo de trabajo es, en algunos casos, cien veces mayor en cuanto a rapidez en WF4 si se compara con WF3; la causa es un runtime [!INCLUDE[wf1](../../../includes/wf1-md.md)] más ligero.  Las cifras de latencia también son significativamente mejores.  Esto significa que la reducción de rendimiento por el uso de [!INCLUDE[wf1](../../../includes/wf1-md.md)] en oposición a los servicios de orquestación de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] codificados manualmente es muy pequeña frente a las ventajas añadidas derivadas de utilizar [!INCLUDE[wf1](../../../includes/wf1-md.md)].  El rendimiento de persistencia ha aumentado en un factor comprendido entre 2,5 y 3,0.  La sobrecarga de la supervisión de estado por medio del seguimiento de flujo de trabajo es ahora muy pequeña.  Hay disponible un conjunto completo de guías de migración para quienes están considerando la posibilidad de cambiar de WF3 a WF4.  Todo esto hace que WF4 sea una opción atractiva para escribir aplicaciones complejas.  
  
## <a name="acknowledgements"></a>Reconocimientos  
 Muchas gracias a los siguientes colaboradores y revisores por sus esfuerzos:  
  
-   Leon Welicki, Microsoft Corporation  
  
-   Ryszard Kwiecinski, Microsoft Corporation  
  
-   Emil Velinov, Microsoft Corporation  
  
-   Nate Talbert, Microsoft Corporation  
  
-   Bob Schmidt, Microsoft Corporation  
  
-   Stefan Batres, Microsoft Corporation
