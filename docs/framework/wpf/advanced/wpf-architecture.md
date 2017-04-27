---
title: "Arquitectura de WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "afinidad de subprocesos"
  - "arquitectura"
  - "propiedades asociadas"
  - "clases, System.Object"
  - "clases, System.Threading.DispatcherObject"
  - "clases, System.Windows.Controls.Control"
  - "clases, System.Windows.DependencyObject"
  - "clases, System.Windows.FrameworkElement"
  - "clases, System.Windows.Media.Visual"
  - "clases, System.Windows.UIElement"
  - "CommandBindings"
  - "componentes, unmanaged"
  - "Control (clase)"
  - "plantillas de datos"
  - "DependencyObject (clase)"
  - "DispatcherObject (clase)"
  - "FrameworkElement (clase)"
  - "INotifyPropertyChange (interfaz)"
  - "interfaces, INotifyPropertyChange"
  - "milcore"
  - "algoritmo de pintor"
  - "propiedades, asociadas"
  - "Guiones gráficos"
  - "System.Object (clase)"
  - "System.Threading.DispatcherObject (clase)"
  - "System.Windows.Controls.Control (clase)"
  - "System.Windows.DependencyObject (clase)"
  - "System.Windows.FrameworkElement (clase)"
  - "System.Windows.Media.Visual (clase)"
  - "System.Windows.UIElement (clase)"
  - "subproceso, afinidad"
  - "UIElement (clase)"
  - "componentes no administrados"
  - "Visual (clase)"
ms.assetid: 8579c10b-76ab-4c52-9691-195ce02333c8
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Arquitectura de WPF
En este tema se proporciona un paseo guiado de la jerarquía de clases de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  En él se explican la mayoría de los subsistemas principales de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] y se describe cómo interactúan.  También se detallan algunas de las decisiones tomadas por los arquitectos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
   
  
<a name="System_Object"></a>   
## System.Object  
 El modelo de programación primario de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se expone a través de código administrado.  En las primeras fases del proceso de diseño de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], hubo varios debates acerca de dónde se debería fijar el límite entre los componentes administrados del sistema y los no administrados.  [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] proporciona varias características que pueden hacer el proceso más sólido y productivo \(como son la administración de memoria, el control de errores, el sistema de tipos común, etc.\) pero todas ellas tienen su costo.  
  
 Los componentes principales de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se muestran en la ilustración siguiente.  Las secciones rojas del diagrama \(PresentationFramework, PresentationCore y milcore\) son los componentes principales del código de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  De éstos, sólo uno es un componente no administrado, milcore.  Milcore se ha escrito en código no administrado para conseguir una estrecha integración con [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)].  La visualización en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se realiza a través del motor de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)], lo que permite una presentación eficaz mediante hardware y software.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] también requirió un control preciso sobre la memoria y la ejecución.  El motor de composición de milcore es sumamente sensible al rendimiento, y requirió renunciar a muchas de las ventajas de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] para obtener mejoras en el rendimiento.  
  
 ![Posición de WPF dentro de .NET Framework.](../../../../docs/framework/wpf/advanced/media/wpf-architect1.png "wpf\_architect1")  
  
 La comunicación entre las partes administradas y no administradas de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se describe más adelante en este tema.  A continuación se describe el resto del modelo de programación administrado.  
  
<a name="System_Threading_DispatcherObject"></a>   
## System.Threading.DispatcherObject  
 La mayoría de los objetos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se derivan de <xref:System.Windows.Threading.DispatcherObject>, que proporciona las estructuras básicas para tratar con la simultaneidad y el subprocesamiento.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] está basado en un sistema de mensajería implementado por el distribuidor.  Funciona de modo similar al conocido suministro de mensajes de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]; de hecho, el distribuidor de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] utiliza los mensajes de User32 para realizar las llamadas entre subprocesos.  
  
 Es necesario comprender dos conceptos básicos al hablar de simultaneidad en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]: el distribuidor y la afinidad de subprocesos.  
  
 Durante la fase de diseño de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], el objetivo era adoptar un único subproceso de ejecución, pero perteneciente a un modelo con afinidad y sin subprocesos.  La afinidad de subprocesos se produce cuando un componente utiliza la identidad del subproceso que se está ejecutando para almacenar algún tipo de estado.  La forma más común de esta afinidad es utilizar el almacenamiento local de subprocesos \(TLS\) para almacenar el estado.  La afinidad de subprocesos requiere que cada subproceso lógico de ejecución sea propiedad de un único subproceso físico en el sistema operativo, lo que puede consumir mucha memoria.  Finalmente, el modelo de subprocesos de WPF se mantuvo sincronizado con el modelo de subprocesos de User32 existente, que consiste en la ejecución de un solo subproceso con afinidad de subprocesos.  La principal razón para esto fue la interoperabilidad; los sistemas como [!INCLUDE[TLA2#tla_ole2.0](../../../../includes/tla2sharptla-ole2-0-md.md)], el Portapapeles e Internet Explorer requieren la ejecución de afinidad con subproceso único \(STA\).  
  
 Dado que disponemos de objetos con subprocesamiento STA, necesitamos un medio de comunicación entre subprocesos y estar seguros de que nos encontramos en el subproceso correcto.  A continuación se describe el rol del distribuidor.  El distribuidor es un sistema de envío de mensajes básico que dispone de varias colas con prioridad.  Por ejemplo, son mensajes las notificaciones de entrada sin formato \(el mouse se ha movido\), las funciones de marco de trabajo \(diseño\) o los comandos de usuario \(ejecutar este método\).  Al realizar una derivación de <xref:System.Windows.Threading.DispatcherObject>, se crea un objeto de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] que tiene el comportamiento de STA y al que se le proporcionará un puntero a un distribuidor en el momento de la creación.  
  
<a name="System_Windows_DependencyObject"></a>   
## System.Windows.DependencyObject  
 Una de las principales filosofías arquitectónicas utilizadas al crear [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] fue la preferencia por las propiedades en lugar de los métodos o los eventos.  Las propiedades son declarativas y le permiten especificar más fácilmente la intención en lugar de la acción.  Esto también permitió el uso de un sistema basado en modelos, o en datos, para mostrar el contenido de la interfaz de usuario.  Esta filosofía tenía como objetivo crear más propiedades con las que poder enlazar, y así tener un mejor control del comportamiento de una aplicación.  
  
 Para conseguir que más partes del sistema estuviesen controladas por propiedades, era necesario un sistema de propiedades más completo que el proporcionado por [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Un ejemplo sencillo de esto son las notificaciones de cambios.  Para poder habilitar los enlaces bidireccionales, será necesario que ambos lados del enlace admitan la notificación de cambios.  Para poder tener el comportamiento vinculado a los valores de propiedad, deberá recibir una notificación cuando cambie el valor de la propiedad.  [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] tiene una interfaz, **INotifyPropertyChange**, que permite a un objeto publicar las notificaciones de cambios, aunque es opcional.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proporciona un sistema de propiedades más completo, derivado del tipo <xref:System.Windows.DependencyObject>.  El sistema de propiedades puede considerarse un sistema de "dependencias" porque realiza el seguimiento de las dependencias entre las expresiones de las propiedades y vuelve a validar automáticamente los valores de propiedad cuando cambian las dependencias.  Por ejemplo, si tenemos una propiedad que hereda \(como <xref:System.Windows.Controls.Control.FontSize%2A>\), el sistema se actualiza automáticamente si la propiedad cambia en un elemento primario de un elemento que hereda el valor.  
  
 La base del sistema de propiedades de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es el concepto de una expresión de propiedad.  En esta primera versión de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], el sistema de expresión de propiedades es cerrado y todas las expresiones que se proporcionan forman parte del marco de trabajo.  Las expresiones son el motivo de que el sistema de propiedades no tenga características de enlace de datos, de estilo o de herencia incluidas en el código, sino que son proporcionadas por capas posteriores dentro del marco de trabajo.  
  
 El sistema de propiedades también proporciona almacenamiento disperso de valores de propiedades.  Debido a que los objetos pueden tener docenas \(o incluso cientos\) de propiedades, y la mayoría de los valores está en su estado predeterminado \(heredado, establecido por estilos, etc.\), no todas las instancias de un objeto necesitan tener definidas todas las propiedades.  
  
 La última de las características nuevas del sistema de propiedades es el concepto de [propiedades adjuntas](GTMT).  Los elementos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se basan en el principio de composición y reutilización de componentes.  Con frecuencia, un elemento contenedor \(como un elemento de diseño <xref:System.Windows.Controls.Grid>\) necesita datos adicionales sobre los elementos secundarios para controlar su comportamiento \(como la información de Fila\/Columna\).  En lugar de asociar todas estas propiedades a cada elemento, cualquier objeto puede proporcionar las definiciones de las propiedades para cualquier otro objeto.  Esto es similar a las características "expando" de JavaScript.  
  
<a name="System_Windows_Media_Visual"></a>   
## System.Windows.Media.Visual  
 Con un sistema ya definido, el paso siguiente consiste en conseguir que se dibujen los píxeles en la pantalla.  La clase <xref:System.Windows.Media.Visual> permite compilar un árbol de objetos visuales, cada uno de los cuales puede contener instrucciones de dibujo y metadatos sobre cómo presentar esas instrucciones \(recorte, transformación, etc.\).  <xref:System.Windows.Media.Visual> está diseñado para ser sumamente ligero y flexible, por lo que la mayoría de las características no tienen ninguna exposición en la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] pública y dependen casi exclusivamente de funciones de devolución de llamada protegidas.  
  
 En realidad, <xref:System.Windows.Media.Visual> es el punto de entrada al sistema de composición de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  <xref:System.Windows.Media.Visual> es el punto de conexión entre estos dos subsistemas, la [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] administrada y el milcore no administrado.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] muestra los datos recorriendo las estructuras de datos no administradas de cuya administración se encarga milcore.  Estas estructuras, denominadas nodos de composición, representan un árbol de presentación jerárquica con instrucciones de representación en cada nodo.  Sólo se puede tener acceso a este árbol, mostrado en el lado derecho de la ilustración siguiente, a través de un protocolo de mensajería.  
  
 Al programar [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], se crean los elementos <xref:System.Windows.Media.Visual>, así como los tipos derivados, que se comunican internamente con el árbol de composición a través de este protocolo de mensajería.  Cada elemento <xref:System.Windows.Media.Visual> de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] puede crear uno, ninguno o varios nodos de composición.  
  
 ![Árbol visual de Windows Presentation Foundation.](../../../../docs/framework/wpf/advanced/media/wpf-architecture2.png "wpf\_architecture2")  
  
 Conviene observar aquí un detalle arquitectónico muy importante, y es que el árbol completo de objetos visuales e instrucciones de dibujo se guarda en la memoria caché.  Usando terminología de gráficos, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] utiliza un sistema de representación retenido.  Esto permite al sistema volver a dibujar con frecuencias de actualización altas sin que el sistema de composición bloquee las devoluciones de llamada al código del usuario.  Esto ayuda a evitar la sensación de que la aplicación no responde.  
  
 Otro detalle importante que no es muy evidente en el diagrama es la forma en la que el sistema realiza realmente la composición.  
  
 En User32 y [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)], el sistema se basa en un método de recorte de modo inmediato.  Cuando es necesario representar un componente, el sistema establece un límite de recorte en cuyo exterior no permite al componente tocar los píxeles y, a continuación, solicita a éste que pinte los píxeles en ese cuadro.  Este método funciona muy bien en sistemas con restricciones de memoria, ya que cuando algo cambia sólo se debe modificar el componente afectado; nunca hay dos componentes que afecten al color de un mismo píxel.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] utiliza un modelo de representación "algoritmo de pintor".  Esto significa que, en lugar de recortar cada componente, se solicita a éste que efectúe la representación desde la parte trasera hacia la parte delantera de la imagen.  Esto permite a cada componente pintar sobre la imagen generada por el componente anterior.  La ventaja de este modelo es que permite tener formas complejas parcialmente transparentes.  Con el moderno hardware gráfico actual, este modelo es relativamente rápido \(lo que no ocurría cuando se crearon User32\/ [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)]\).  
  
 Como se ha mencionado previamente, la filosofía básica de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es adoptar un modelo de programación más declarativo y centrado en las propiedades.  En el sistema visual, esto se pone de manifiesto en un par de lugares interesantes.  
  
 En primer lugar, si piensa en el sistema de gráficos de modo retenido, éste se está alejando de un modelo de tipo DrawLine\/DrawLine imperativo hacia un modelo orientado a datos, new Line\(\)\/new Line\(\).  Esta migración hacia la representación controlada por datos permite expresar operaciones complejas en las instrucciones de dibujo mediante propiedades.  Los tipos que se derivan de <xref:System.Windows.Media.Drawing> son el modelo de objetos para la representación.  
  
 En segundo lugar, si evalúa el sistema de animación, verá que es declarativo casi por completo.  En lugar de exigir al programador que calcule la ubicación o el color siguiente, las animaciones pueden expresarse como un conjunto de propiedades en un objeto de animación.  Estas animaciones permitirán expresar la intención del programador o del diseñador \(mueva este botón de aquí a allí en 5 segundos\) y el sistema podrá determinar la manera más eficaz de lograrlo.  
  
<a name="System_Windows_UIElement"></a>   
## System.Windows.UIElement  
 <xref:System.Windows.UIElement> define los subsistemas básicos: diseño, entrada y eventos.  
  
 El diseño es un concepto básico en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Son muchos los sistemas en los que, o existe un conjunto fijo de modelos de diseño \(HTML admite tres modelos de diseño; flujo, absoluto y tablas\), o no existe ningún modelo de diseño \(en realidad, User32 sólo admite el posicionamiento absoluto\).  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se concibió dando por sentado que los desarrolladores y diseñadores deseaban un modelo de diseño flexible y extensible, que pudiera ser controlado por valores de propiedades en lugar de por lógica imperativa.  El contrato básico para el diseño se introduce en el nivel <xref:System.Windows.UIElement>, un modelo de dos fases con una pasada <xref:System.Windows.UIElement.Measure%2A> y otra <xref:System.Windows.UIElement.Arrange%2A>.  
  
 La fase <xref:System.Windows.UIElement.Measure%2A> permite a un componente determinar el tamaño que le gustaría tener.  Se trata de una fase independiente de <xref:System.Windows.UIElement.Arrange%2A>, ya que hay muchas situaciones en las que un elemento primario solicitará a un elemento secundario que se "mida" varias veces para determinar su posición y tamaño óptimos.  El hecho de que los elementos primarios soliciten a los elementos secundarios que se midan demuestra otra filosofía clave de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], el ajuste al contenido.  Todos los controles de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] admiten la capacidad de ajustarse al tamaño natural de su contenido.  Esto facilita enormemente la localización y permite un diseño dinámico de los elementos cuando los objetos cambian de tamaño.  La fase <xref:System.Windows.UIElement.Arrange%2A> permite a un elemento primario colocar y determinar el tamaño final de cada elemento secundario.  
  
 A menudo, se habla mucho sobre la salida de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. <xref:System.Windows.Media.Visual> y los objetos relacionados.  Sin embargo, también hay una gran cantidad de innovaciones en cuanto a la entrada.  Probablemente el cambio más importante en el modelo de entrada para [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es el modelo coherente mediante el cual los eventos de entrada se enrutan a través del sistema.  
  
 La entrada se origina en forma de señal en un controlador de dispositivo de modo kernel y se vuelve a enrutar al proceso y subproceso correctos a través de un intrincado procedimiento que implica el kernel de Windows y User32.  Una vez que el mensaje de User32 correspondiente a la entrada se ha enrutado a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], se convierte en un mensaje de entrada sin formato de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] y se envía al distribuidor.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] permite convertir los eventos de entrada sin formato en varios eventos reales, lo que permite la implementación de características como "MouseEnter" en un nivel bajo del sistema con entrega garantizada.  
  
 Cada evento de entrada se convierte en al menos dos eventos, un evento de "vista previa" y el evento real.  Todos los eventos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] tienen información de enrutamiento a través del árbol de elementos.  Se dice que los eventos "se traspasan" si van subiendo por el árbol desde un destino hasta la raíz, y se dice que " tunelizan " si se inician en la raíz y pasan a un destino situado más abajo.  Los eventos de vista previa de entrada tunelizan, lo que ofrece a cualquiera de los elementos del árbol una oportunidad para filtrar o realizar acciones cuando se produce un evento.  Los eventos normales \(sin vista previa\) se traspasan a continuación desde el destino hasta la raíz.  
  
 Esta diferencia entre la fase de túnel y de traspaso permite que la implementación de características como los aceleradores de teclado funcione de forma coherente en un universo compuesto.  En User32, la implementación de los aceleradores de teclado se realizaría teniendo una tabla global única con todos los aceleradores admitidos \(Ctrl\+N asignado a "Nuevo"\).  En el distribuidor de la aplicación se llamaría a **a TranslateAccelerator**, que examinaría los mensajes de entrada en User32 y determinaría si alguno de ellos coincide con un acelerador registrado.  En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] esto no funcionaría, ya que el sistema es totalmente "ajustable", es decir, que cualquier elemento puede controlar y utilizar cualquier acelerador de teclado.  Tener este modelo de dos fases para la entrada permite a los componentes implementar su propio "TranslateAccelerator".  
  
 Para ir incluso un poco más lejos, <xref:System.Windows.UIElement> introduce también el concepto de CommandBindings.  El sistema de comandos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] permite a los programadores definir la funcionalidad en función de un punto final de comando, algo que implementa <xref:System.Windows.Input.ICommand>.  Los enlaces de comandos permiten a un elemento definir una asignación entre un gesto de entrada \(Ctrl\+N\) y un comando \(Nuevo\).  Tanto los gestos de entrada como las definiciones de comandos son extensibles, y pueden conectarse en el momento de su uso.  Esto hace que resulte trivial, por ejemplo, permitir que un usuario final personalice los enlaces de teclado que desea utilizar dentro de una aplicación.  
  
 Hasta ahora, este tema se ha centrado en las características "básicas" de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], es decir, las características implementadas en el ensamblado PresentationCore.  Al concebir [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], el resultado deseado era una separación limpia entre las partes fundamentales \(como el contrato para el diseño con **Measure** y **Arrange**\) y las partes del marco de trabajo \(como la implementación de un diseño concreto como <xref:System.Windows.Controls.Grid>\).  El objetivo era proporcionar un punto de extensibilidad en la zona inferior de la pila que permitiría a los programadores externos crear sus propios marcos de trabajo en caso necesario.  
  
<a name="System_Windows_FrameworkElement"></a>   
## System.Windows.FrameworkElement  
 <xref:System.Windows.FrameworkElement> se puede examinar de dos maneras diferentes.  Introduce un conjunto de directivas y personalizaciones en los subsistemas incluidos en las capas inferiores de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  También introduce un conjunto de nuevos subsistemas.  
  
 La directiva primaria introducida por <xref:System.Windows.FrameworkElement> trata sobre el diseño de la aplicación.  <xref:System.Windows.FrameworkElement> se basa en el contrato del diseño básico introducido por <xref:System.Windows.UIElement> y agrega el concepto de una "ranura" de diseño que facilita a los autores del diseño la disponibilidad de un conjunto coherente de elementos de semántica del diseño orientados a propiedades.  Propiedades como <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.MinWidth%2A> y <xref:System.Windows.FrameworkElement.Margin%2A> \(por nombrar algunas\) proporcionan a todos los componentes derivados de <xref:System.Windows.FrameworkElement> un comportamiento coherente dentro de los contenedores de diseño.  
  
 <xref:System.Windows.FrameworkElement> también facilita la exposición de la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] a muchas características situadas en las capas básicas de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Por ejemplo, <xref:System.Windows.FrameworkElement> proporciona acceso directo a la animación a través del método <xref:System.Windows.FrameworkElement.BeginStoryboard%2A>.  Un objeto <xref:System.Windows.Media.Animation.Storyboard> proporciona una manera de crear scripts para varias animaciones con un conjunto de propiedades.  
  
 Las dos características más importantes introducidas por <xref:System.Windows.FrameworkElement> son el enlace de datos y los estilos.  
  
 El subsistema de enlace de datos de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] debería resultarle relativamente familiar a cualquiera que haya utilizado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)] para crear la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de una aplicación.  En cada uno de estos sistemas, hay una manera sencilla de expresar que se desea enlazar una o varias propiedades de un elemento determinado a un fragmento de datos.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ofrece compatibilidad total para el enlace de propiedades, la transformación y el enlace de listas.  
  
 Una de las características más interesantes del enlace de datos en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] es la introducción de plantillas de datos.  Las plantillas de datos le permiten especificar mediante declaración cómo se debería visualizar un fragmento de datos.  En lugar de crear una interfaz de usuario personalizada que se puede enlazar a los datos, puede solucionar el problema permitiendo que los datos determinen la presentación que se va a crear.  
  
 La aplicación de estilos es realmente una forma ligera de enlace de datos.  El uso de estilos le permite enlazar un conjunto de propiedades de una definición compartida a una o varias instancias de un elemento.  Los estilos se aplican a un elemento, bien mediante una referencia explícita \(estableciendo la propiedad <xref:System.Windows.FrameworkElement.Style%2A> \) o bien de forma implícita asociando un estilo al tipo [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] del elemento.  
  
<a name="System_Windows_Controls_Control"></a>   
## System.Windows.Controls.Control  
 La característica más significativa del control es la definición de plantillas.  Si piensa en el sistema de composición de WPF como en un sistema de presentación de modo retenido, la definición de plantillas permite a un control describir su presentación de una manera parametrizada y declarativa.  En realidad, <xref:System.Windows.Controls.ControlTemplate> es simplemente un script que permite crear un conjunto de elementos secundarios, con enlaces a las propiedades proporcionadas por el control.  
  
 <xref:System.Windows.Controls.Control> proporciona un conjunto de propiedades estándar, como <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.Background%2A> y <xref:System.Windows.Controls.Control.Padding%2A>, por citar algunas, que los autores de las plantillas pueden utilizar para personalizar la presentación de un control.  La implementación de un control proporciona un modelo de datos y un modelo de interacción.  El modelo de interacción define un conjunto de comandos \(como Cerrar para una ventana\) y enlaces a gestos de entrada \(como hacer clic en la X roja situada en la esquina superior de la ventana\).  El modelo de datos proporciona un conjunto de propiedades para personalizar el modelo de interacción o la presentación \(determinado por la plantilla\).  
  
 Esta diferencia entre el modelo de datos \(propiedades\), el modelo de interacción \(comandos y eventos\) y el modelo de presentación \(plantillas\) permite una total personalización de la apariencia y el comportamiento de un control.  
  
 Un aspecto común del modelo de datos de los controles es el modelo de contenido.  Si examina un control como <xref:System.Windows.Controls.Button>, verá que tiene una propiedad denominada "Content" de tipo <xref:System.Object>.  En [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)], esta propiedad sería normalmente una cadena; sin embargo, esto limita el tipo de contenido que puede colocar en un botón.  El contenido de un botón puede ser una cadena simple, un objeto de datos complejo o un árbol de elementos completo.  En el caso de un objeto de datos, la plantilla de datos se utiliza para construir una presentación.  
  
<a name="Summary"></a>   
## Resumen  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] está diseñado para permitirle crear sistemas de presentación dinámicos y controlados por datos.  Cada parte del sistema está diseñada para crear objetos mediante conjuntos de propiedades que controlan el comportamiento.  El enlace de datos es una parte fundamental del sistema y está integrado en cada capa.  
  
 Las aplicaciones tradicionales crean una presentación y, a continuación, enlazan a algunos datos.  En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], todo lo concerniente al control, cada aspecto de la presentación, está generado por algún tipo de enlace de datos.  El texto situado dentro de un botón se muestra creando un control compuesto dentro de éste y enlazando su presentación a la propiedad de contenido del botón.  
  
 Cuando comience a desarrollar aplicaciones basadas en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], encontrará un entorno muy familiar.  Podrá establecer propiedades, utilizar objetos y enlazar datos de la misma manera que con [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)].  Un examen más profundo de la arquitectura de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] le permitirá descubrir que existe la posibilidad de crear aplicaciones mucho más ricas controladas fundamentalmente por los datos.  
  
## Vea también  
 <xref:System.Windows.Media.Visual>   
 <xref:System.Windows.UIElement>   
 <xref:System.Windows.Input.ICommand>   
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.Threading.DispatcherObject>   
 <xref:System.Windows.Input.CommandBinding>   
 <xref:System.Windows.Controls.Control>   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Diseño](../../../../docs/framework/wpf/advanced/layout.md)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)