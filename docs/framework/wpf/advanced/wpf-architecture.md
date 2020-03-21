---
title: Architecture
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], attached
- attached properties [WPF]
- architecture [WPF]
- unmanaged components [WPF]
- affinity thread [WPF]
- Storyboards [WPF]
- milcore [WPF]
- components [WPF], unmanaged
- painter's algorithm
- interfaces [WPF], INotifyPropertyChange
- CommandBindings [WPF]
- data templates [WPF]
- thread [WPF], affinity
ms.assetid: 8579c10b-76ab-4c52-9691-195ce02333c8
ms.openlocfilehash: b16be8470a47f3e8e362feb0b13e10aa901baacb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187131"
---
# <a name="wpf-architecture"></a>Arquitectura de WPF
En este tema se proporciona un recorrido guiado por la jerarquía de clases de Windows Presentation Foundation (WPF). Cubre la mayoría de los subsistemas principales de WPFWPF y describe cómo interactúan. También detalla algunas de las opciones tomadas por los arquitectos de WPFWPF.  

<a name="System_Object"></a>
## <a name="systemobject"></a>System.Object  
 El modelo de programación principal de WPFWPF se expone a través del código administrado. Al principio de la fase de diseño de WPFWPF hubo una serie de debates sobre dónde se debe trazar la línea entre los componentes administrados del sistema y los no administrados. CLR proporciona una serie de características que hacen que el desarrollo sea más productivo y robusto (incluida la administración de memoria, el control de errores, el sistema de tipos comunes, etc.), pero tienen un costo.  
  
 Los componentes principales de WPFWPF se ilustran en la figura siguiente. Las secciones rojas del diagrama (PresentationFramework, PresentationCore y milcore) son las partes principales del código WPFWPF. De estos, solo uno es un componente no administrado: Milcore. Milcore se escribe en código no administrado para permitir una integración estrecha con DirectX. Toda la visualización en WPFWPF se realiza a través del motor DirectX, lo que permite una representación eficiente de hardware y software. WPFWPF también requiere un control preciso sobre la memoria y la ejecución. El motor de composición en milcore es extremadamente sensible al rendimiento, y requiere renunciar a muchas ventajas de CLR para obtener rendimiento.  
  
 ![Posición de WPF dentro de .NET Framework.](./media/wpf-architect1.PNG "wpf_architect1")  
  
 La comunicación entre las partes administradas y no administradas de WPFWPF se describe más adelante en este tema. A continuación se describe el resto del modelo de programación administrado.  
  
<a name="System_Threading_DispatcherObject"></a>
## <a name="systemthreadingdispatcherobject"></a>System.Threading.DispatcherObject  
 La mayoría de <xref:System.Windows.Threading.DispatcherObject>los objetos de WPFWPF derivan de , que proporciona las construcciones básicas para tratar con simultaneidad y subprocesos. WPFWPF se basa en un sistema de mensajería implementado por el distribuidor. Esto funciona de forma muy similar a la conocida bomba de mensajes Win32; de hecho, el distribuidor WPFWPF usa mensajes User32 para realizar llamadas entre subprocesos.  
  
 Realmente hay dos conceptos básicos para entender al discutir la simultaneidad en WPFWPF: la afinidad de distribuidor y subprocesos.  
  
 Durante la fase de diseño de WPFWPF, el objetivo era mover a un único subproceso de ejecución, pero un modelo "afines" que no sea de subproceso. La afinidad de subprocesos se produce cuando un componente usa la identidad del subproceso que se está ejecutando para almacenar algún tipo de estado. La forma más común de esta afinidad es usar el almacenamiento local de subprocesos (TLS) para almacenar el estado. La afinidad de subprocesos requiere que cada subproceso lógico de ejecución sea propiedad de un único subproceso físico en el sistema operativo, lo que puede consumir mucha memoria. Finalmente, el modelo de subprocesos de WPF se mantuvo sincronizado con el modelo de subprocesos de User32 existente, que consiste en la ejecución de un solo subproceso con afinidad de subprocesos. La razón principal de esto era la interoperabilidad: sistemas como OLE 2.0, el portapapeles e Internet Explorer requieren la ejecución de afinidad de subproceso único (STA).  
  
 Dado que disponemos de objetos con subprocesos STA, necesitamos un medio de comunicación entre subprocesos y estar seguros de que nos encontramos en el subproceso correcto. A continuación se describe el rol del distribuidor. El distribuidor es un sistema de envío de mensajes básico que dispone de varias colas con prioridad. Por ejemplo, son mensajes las notificaciones de entrada sin formato (el mouse se ha movido), las funciones de marco de trabajo (diseño) o los comandos de usuario (ejecutar este método). Al derivar <xref:System.Windows.Threading.DispatcherObject>de , se crea un objeto CLR que tiene un comportamiento STA y se le dará un puntero a un distribuidor en el momento de la creación.  
  
<a name="System_Windows_DependencyObject"></a>
## <a name="systemwindowsdependencyobject"></a>System.Windows.DependencyObject  
 Una de las filosofías arquitectónicas principales utilizadas en la creación de WPFWPF era una preferencia por las propiedades sobre los métodos o eventos. Las propiedades son declarativas y le permiten especificar más fácilmente la intención en lugar de la acción. Esto también ha permitido el uso de un sistema basado en modelos, o en datos, para mostrar el contenido de la interfaz de usuario. Esta filosofía tenía como objetivo crear más propiedades con las que poder enlazar, y así tener un mejor control del comportamiento de una aplicación.  
  
 Para tener más del sistema controlado por propiedades, se necesitaba un sistema de propiedades más enriquecido que lo que proporciona CLR. Un ejemplo sencillo de esto son las notificaciones de cambios. Para poder habilitar los enlaces bidireccionales, será necesario que ambos lados del enlace admitan la notificación de cambios. Para poder tener el comportamiento vinculado a los valores de propiedad, deberá recibir una notificación cuando cambie el valor de la propiedad. Microsoft .NET Framework tiene una interfaz, **INotifyPropertyChange**, que permite a un objeto publicar notificaciones de cambio, sin embargo, es opcional.  
  
 WPFWPF proporciona un sistema de <xref:System.Windows.DependencyObject> propiedades más enriquecido, derivado del tipo. El sistema de propiedades puede considerarse un sistema de "dependencias" porque realiza el seguimiento de las dependencias entre las expresiones de las propiedades y vuelve a validar automáticamente los valores de propiedad cuando cambian las dependencias. Por ejemplo, si tiene una propiedad <xref:System.Windows.Controls.Control.FontSize%2A>que hereda (como ), el sistema se actualiza automáticamente si la propiedad cambia en un elemento primario de un elemento que hereda el valor.  
  
 La base del sistema de propiedades WPFWPF es el concepto de una expresión de propiedad. En esta primera versión de WPFWPF, el sistema de expresiones de propiedad está cerrado y las expresiones se proporcionan como parte del marco de trabajo. Las expresiones son el motivo de que el sistema de propiedades no tenga características de enlace de datos, de estilo o de herencia incluidas en el código, sino que son proporcionadas por capas posteriores dentro del marco de trabajo.  
  
 El sistema de propiedades también proporciona almacenamiento disperso de valores de propiedades. Debido a que los objetos pueden tener docenas (o incluso cientos) de propiedades, y la mayoría de los valores está en su estado predeterminado (heredado, establecido por estilos, etc.), no todas las instancias de un objeto necesitan tener definidas todas las propiedades.  
  
 La última de las características nuevas del sistema de propiedades es el concepto de propiedades adjuntas. WPFWPF elementos se basan en el principio de composición y reutilización de componentes. A menudo es el caso de <xref:System.Windows.Controls.Grid> que algunos elementos que contienen (como un elemento de diseño) necesitan datos adicionales sobre elementos secundarios para controlar su comportamiento (como la información de fila/columna). En lugar de asociar todas estas propiedades a cada elemento, cualquier objeto puede proporcionar las definiciones de las propiedades para cualquier otro objeto. Esto es similar a las características "expando" de JavaScript.  
  
<a name="System_Windows_Media_Visual"></a>
## <a name="systemwindowsmediavisual"></a>System.Windows.Media.Visual  
 Con un sistema ya definido, el paso siguiente consiste en conseguir que se dibujen los píxeles en la pantalla. La <xref:System.Windows.Media.Visual> clase proporciona la creación de un árbol de objetos visuales, cada uno de los cuales contiene opcionalmente instrucciones de dibujo y metadatos sobre cómo representar esas instrucciones (recorte, transformación, etc.). <xref:System.Windows.Media.Visual>está diseñado para ser extremadamente ligero y flexible, por lo que la mayoría de las características no tienen exposición API pública y dependen en gran medida de las funciones de devolución de llamada protegidas.  
  
 <xref:System.Windows.Media.Visual>es realmente el punto de entrada al sistema de composición WPF. <xref:System.Windows.Media.Visual>es el punto de conexión entre estos dos subsistemas, la API administrada y el milcore no administrado.  
  
 WPFWPF muestra datos recorriendo las estructuras de datos no administradas administradas por el milcore. Estas estructuras, denominadas nodos de composición, representan un árbol de presentación jerárquica con instrucciones de representación en cada nodo. Solo se puede tener acceso a este árbol, mostrado en el lado derecho de la ilustración siguiente, a través de un protocolo de mensajería.  
  
 Al programar WPFWPF, se crean <xref:System.Windows.Media.Visual> elementos y tipos derivados, que se comunican internamente con el árbol de composición a través de este protocolo de mensajería. Cada <xref:System.Windows.Media.Visual> uno en WPFWPF puede crear uno, ninguno o varios nodos de composición.  
  
 ![Árbol visual de Windows Presentation Foundation.](./media/wpf-architecture2.PNG "wpf_architecture2")  
  
 Hay que observar aquí un detalle arquitectónico muy importante, y es que el árbol completo de objetos visuales e instrucciones de dibujo se guarda en la memoria caché. En términos de gráficos, WPFWPF usa un sistema de representación retenido. Esto permite al sistema volver a dibujar con frecuencias de actualización altas sin que el sistema de composición bloquee las devoluciones de llamada al código del usuario. Esto ayuda a evitar la sensación de que la aplicación no responde.  
  
 Otro detalle importante que no es muy evidente en el diagrama es la forma en la que el sistema realiza realmente la composición.  
  
 En User32 y GDI, el sistema funciona en un sistema de recorte de modo inmediato. Cuando es necesario representar un componente, el sistema establece un límite de recorte en cuyo exterior no permite al componente tocar los píxeles y, después, le pide que pinte los píxeles en ese cuadro. Este método funciona muy bien en sistemas con restricciones de memoria, ya que cuando algo cambia solo se debe modificar el componente afectado; nunca hay dos componentes que afecten al color de un mismo píxel.  
  
 WPFWPF usa un modelo de pintura de "algoritmo de pintor". Esto significa que, en lugar de recortar cada componente, se pide a este que efectúe la representación desde la parte trasera hacia la parte delantera de la imagen. Esto permite a cada componente pintar sobre la imagen generada por el componente anterior. La ventaja de este modelo es que permite tener formas complejas parcialmente transparentes. Con el hardware gráfico moderno de hoy en día, este modelo es relativamente rápido (que no era el caso cuando se crearon User32 / GDI).  
  
 Como se mencionó anteriormente, una filosofía central de WPFWPF es pasar a un modelo de programación más declarativo, "centrado en la propiedad". En el sistema visual, esto se pone de manifiesto en un par de lugares interesantes.  
  
 En primer lugar, si piensa en el sistema de gráficos de modo retenido, este se está alejando de un modelo de tipo DrawLine/DrawLine imperativo hacia un modelo orientado a datos, new Line()/new Line(). Esta migración hacia la representación controlada por datos permite expresar operaciones complejas en las instrucciones de dibujo mediante propiedades. Los tipos derivados son <xref:System.Windows.Media.Drawing> efectivamente el modelo de objetos para la representación.  
  
 En segundo lugar, si evalúa el sistema de animación, verá que es declarativo casi por completo. En lugar de exigir al desarrollador que calcule la ubicación o el color siguiente, las animaciones pueden expresarse como un conjunto de propiedades en un objeto de animación. Estas animaciones permitirán expresar la intención del desarrollador o del diseñador (mueva este botón de aquí a allí en 5 segundos) y el sistema podrá determinar la manera más eficaz de lograrlo.  
  
<a name="System_Windows_UIElement"></a>
## <a name="systemwindowsuielement"></a>System.Windows.UIElement  
 <xref:System.Windows.UIElement>define los subsistemas principales, incluidos Layout, Input y Events.  
  
 Diseño es un concepto básico en WPFWPF. Son muchos los sistemas en los que, o existe un conjunto fijo de modelos de diseño (HTML admite tres modelos de diseño; flujo, absoluto y tablas), o no existe ningún modelo de diseño (en realidad, User32 solo admite el posicionamiento absoluto). WPFWPF comenzó con la suposición de que los desarrolladores y diseñadores querían un modelo de diseño flexible y extensible, que pudiera estar controlado por valores de propiedad en lugar de lógica imperativa. En <xref:System.Windows.UIElement> el nivel, se introduce el contrato básico para <xref:System.Windows.UIElement.Measure%2A> <xref:System.Windows.UIElement.Arrange%2A> el diseño - un modelo de dos fases con y pasa.  
  
 <xref:System.Windows.UIElement.Measure%2A>permite que un componente determine cuánto tamaño le gustaría tomar. Esta es una <xref:System.Windows.UIElement.Arrange%2A> fase independiente de porque hay muchas situaciones en las que un elemento primario le pedirá a un elemento secundario que mida varias veces para determinar su posición y tamaño óptimos. El hecho de que los elementos primarios pidan a los elementos secundarios que midan se muestra otra filosofía clave de WPFWPF: tamaño al contenido. Todos los controles de WPFWPF admiten la capacidad de tamaño para el tamaño natural de su contenido. Esto facilita enormemente la localización y permite un diseño dinámico de los elementos cuando los objetos cambian de tamaño. La <xref:System.Windows.UIElement.Arrange%2A> fase permite a un padre posicionar y determinar el tamaño final de cada niño.  
  
 A menudo se pasa mucho tiempo hablando <xref:System.Windows.Media.Visual> sobre el lado de salida de WPFWPF y objetos relacionados. En cambio, también hay una gran cantidad de innovaciones en cuanto a la entrada. Probablemente el cambio más fundamental en el modelo de entrada para WPFWPF es el modelo coherente por el que los eventos de entrada se enrutan a través del sistema.  
  
 La entrada se origina en forma de señal en un controlador de dispositivo de modo kernel y se vuelve a enrutar al proceso y subproceso correctos a través de un intrincado procedimiento que implica el kernel de Windows y User32. Una vez que el User32 mensaje correspondiente a la entrada se enruta a WPFWPF, se convierte en un mensaje de entrada sin formato WPFWPF y se envía al distribuidor. WPFWPF permite que los eventos de entrada sin procesar se conviertan en varios eventos reales, lo que permite que características como "MouseEnter" se implementen en un nivel bajo del sistema con entrega garantizada.  
  
 Cada evento de entrada se convierte en al menos dos eventos, un evento de "vista previa" y el evento real. Todos los eventos de WPFWPF tienen una noción de enrutamiento a través del árbol de elementos. Se dice que los eventos "burbujan" si atraviesan desde un objetivo hasta la raíz, y se dice que "túnel" si comienzan en la raíz y atraviesan hacia un objetivo. Los eventos de vista previa de entrada tunelizan, lo que ofrece a cualquiera de los elementos del árbol una oportunidad para filtrar o realizar acciones cuando se produce un evento. Los eventos normales (sin vista previa) se traspasan a continuación desde el destino hasta la raíz.  
  
 Esta diferencia entre la fase de túnel y de traspaso permite que la implementación de características como los aceleradores de teclado funcione de manera coherente en un universo compuesto. En User32, la implementación de los aceleradores de teclado se realizaría teniendo una tabla global única con todos los aceleradores admitidos (Ctrl+N asignado a "Nuevo"). En el distribuidor de la aplicación se llamaría a **TranslateAccelerator**, que examinaría los mensajes de entrada en User32 y determinaría si alguno de ellos coincide con un acelerador registrado. En WPFWPF esto no funcionaría porque el sistema es totalmente "composable": cualquier elemento puede controlar y usar cualquier acelerador de teclado. Tener este modelo de dos fases para la entrada permite a los componentes implementar su propio "TranslateAccelerator".  
  
 Para dar este paso <xref:System.Windows.UIElement> más, también presenta la noción de CommandBindings. El sistema de comandos WPFWPF permite a los desarrolladores definir <xref:System.Windows.Input.ICommand>la funcionalidad en términos de un punto final del comando, algo que implementa . Los enlaces de comandos permiten a un elemento definir una asignación entre un gesto de entrada (Ctrl+N) y un comando (Nuevo). Tanto los gestos de entrada como las definiciones de comandos son extensibles, y pueden conectarse en el momento de su uso. Esto hace que resulte trivial, por ejemplo, permitir que un usuario final personalice los enlaces de teclado que quiere usar dentro de una aplicación.  
  
 Hasta este punto del tema, las características "fundamentales" de WPFWPF: las características implementadas en el ensamblado PresentationCore, han sido el foco. Al compilar WPFWPF, una separación limpia entre piezas fundamentales (como el contrato de diseño <xref:System.Windows.Controls.Grid>con **Measure** y **Arrange**) y piezas de marco de trabajo (como la implementación de un diseño específico como ) era el resultado deseado. El objetivo era proporcionar un punto de extensibilidad en la zona inferior de la pila que permitiría a los programadores externos crear sus propios marcos de trabajo en caso necesario.  
  
<a name="System_Windows_FrameworkElement"></a>
## <a name="systemwindowsframeworkelement"></a>System.Windows.FrameworkElement  
 <xref:System.Windows.FrameworkElement>se puede mirar de dos maneras diferentes. Presenta un conjunto de directivas y personalizaciones en los subsistemas introducidos en las capas inferiores de WPFWPF. También presenta un conjunto de nuevos subsistemas.  
  
 La directiva principal <xref:System.Windows.FrameworkElement> introducida por está en torno al diseño de la aplicación. <xref:System.Windows.FrameworkElement>se basa en el contrato <xref:System.Windows.UIElement> de diseño básico introducido por y agrega la noción de un diseño "ranura" que facilita a los autores de diseño tener un conjunto coherente de semántica de diseño basada en propiedades. Propiedades <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>como <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> , , y (por nombrar algunos) proporcionan a todos los componentes derivados del comportamiento <xref:System.Windows.FrameworkElement> coherente dentro de los contenedores de diseño.  
  
 <xref:System.Windows.FrameworkElement>También proporciona una exposición más fácil a la API a muchas características que se encuentran en las capas principales de WPFWPF. Por ejemplo, <xref:System.Windows.FrameworkElement> proporciona acceso directo <xref:System.Windows.FrameworkElement.BeginStoryboard%2A> a la animación a través del método. A <xref:System.Windows.Media.Animation.Storyboard> proporciona una manera de crear scripts de varias animaciones con un conjunto de propiedades.  
  
 Las dos cosas <xref:System.Windows.FrameworkElement> más críticas que se introducen son el enlace de datos y los estilos.  
  
 El subsistema de enlace de datos de WPFWPF debe ser relativamente [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]familiar para cualquier persona que haya utilizado Windows Forms o ASP.NET para crear una aplicación. En cada uno de estos sistemas, hay una manera sencilla de expresar que quiere enlazar una o varias propiedades de un elemento determinado a un fragmento de datos. WPFWPF tiene compatibilidad completa para el enlace de propiedades, la transformación y el enlace de lista.  
  
 Una de las características más interesantes del enlace de datos en WPFWPF es la introducción de plantillas de datos. Las plantillas de datos le permiten especificar mediante declaración cómo se debería visualizar un fragmento de datos. En lugar de crear una interfaz de usuario personalizada que se puede enlazar a los datos, puede solucionar el problema permitiendo que los datos determinen la presentación que se va a crear.  
  
 La aplicación de estilos es realmente una forma ligera de enlace de datos. El uso de estilos le permite enlazar un conjunto de propiedades de una definición compartida a una o varias instancias de un elemento. Los estilos se aplican a un elemento <xref:System.Windows.FrameworkElement.Style%2A> por referencia explícita (estableciendo la propiedad) o implícitamente asociando un estilo con el tipo CLR del elemento.  
  
<a name="System_Windows_Controls_Control"></a>
## <a name="systemwindowscontrolscontrol"></a>System.Windows.Controls.Control  
 La característica más significativa del control es la definición de plantillas. Si piensa en el sistema de composición de WPF como en un sistema de representación de modo retenido, la definición de plantillas permite a un control describir su representación de una manera parametrizada y declarativa. A <xref:System.Windows.Controls.ControlTemplate> es realmente nada más que un script para crear un conjunto de elementos secundarios, con enlaces a las propiedades ofrecidas por el control.  
  
 <xref:System.Windows.Controls.Control>proporciona un conjunto de <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.Background%2A>propiedades <xref:System.Windows.Controls.Control.Padding%2A>de stock, , , , , para nombrar algunas, que los autores de plantillas pueden usar para personalizar la presentación de un control. La implementación de un control proporciona un modelo de datos y un modelo de interacción. El modelo de interacción define un conjunto de comandos (como Cerrar para una ventana) y enlaces a gestos de entrada (como hacer clic en la X roja situada en la esquina superior de la ventana). El modelo de datos proporciona un conjunto de propiedades para personalizar el modelo de interacción o la presentación (determinado por la plantilla).  
  
 Esta diferencia entre el modelo de datos (propiedades), el modelo de interacción (comandos y eventos) y el modelo de presentación (plantillas) permite una total personalización de la apariencia y el comportamiento de un control.  
  
 Un aspecto común del modelo de datos de los controles es el modelo de contenido. Si observa un control <xref:System.Windows.Controls.Button>como , verá que tiene una propiedad <xref:System.Object>denominada "Contenido" de tipo . En Windows Forms y ASP.NET, esta propiedad normalmente sería una cadena, sin embargo, que limita el tipo de contenido que puede colocar en un botón. El contenido de un botón puede ser una cadena simple, un objeto de datos complejo o un árbol de elementos completo. En el caso de un objeto de datos, la plantilla de datos se usa para construir una presentación.  
  
<a name="Summary"></a>
## <a name="summary"></a>Resumen  
 WPFWPF está diseñado para permitirle crear sistemas de presentación dinámicos controlados por datos. Cada parte del sistema está diseñada para crear objetos mediante conjuntos de propiedades que controlan el comportamiento. El enlace de datos es una parte fundamental del sistema y está integrado en cada capa.  
  
 Las aplicaciones tradicionales crean una presentación y, después, enlazan a algunos datos. En WPFWPF, todo lo que tiene el control, cada aspecto de la presentación, se genera mediante algún tipo de enlace de datos. El texto situado dentro de un botón se muestra creando un control compuesto dentro de este y enlazando su presentación a la propiedad de contenido del botón.  
  
 Cuando comience a desarrollar aplicaciones basadas en WPFWPF, debería ser muy familiar. Puede establecer propiedades, usar objetos y enlazar datos de la misma manera que puede usar formularios Windows Forms o ASP.NET. Con una investigación más profunda sobre la arquitectura de WPFWPF, encontrará que existe la posibilidad de crear aplicaciones mucho más ricas que tratan fundamentalmente los datos como el controlador principal de la aplicación.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Threading.DispatcherObject>
- <xref:System.Windows.Input.CommandBinding>
- <xref:System.Windows.Controls.Control>
- [Descripción general del enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Diseño](layout.md)
- [Información general sobre animaciones](../graphics-multimedia/animation-overview.md)
