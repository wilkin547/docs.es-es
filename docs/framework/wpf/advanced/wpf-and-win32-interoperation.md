---
title: "Interoperabilidad de WPF y Win32 | Microsoft Docs"
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
  - "hospedar contenido de WPF en ventana de Win32"
  - "interoperabilidad con HWND [WPF]"
  - "interoperabilidad [WPF], Win32"
  - "código Win32, interoperabilidad con WPF"
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Interoperabilidad de WPF y Win32
En este tema se proporciona información general sobre cómo interoperar código [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno enriquecido para la creación de aplicaciones.  Sin embargo, cuando tenga que una inversión sustancial en código [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], puede que sea más efectivo parte de ese código.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="basics"></a>   
## Fundamentos de interoperación entre WPF y Win32  
 Hay dos técnicas básicas para la interoperación entre código [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
-   Hospedar el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Con esta técnica, puede utilizar las capacidades gráficas avanzadas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro del marco de una ventana estándar y una aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
-   Hospedar una ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] en contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Con esta técnica, puede utilizar un control de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] personalizado existente en el contexto de otro contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y pasar datos a través de los límites.  
  
 Cada una de estas técnicas se presenta conceptualmente en este tema.  Para ver una ilustración más orientada al código del hospedaje de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], vea [Tutorial: Hospedar contenido de WPF en Win32](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md).  Para ver una ilustración más orientada al código del hospedaje de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Tutorial: Hospedar un control de Win32 en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md).  
  
<a name="projects"></a>   
## Proyectos de interoperación WPF  
 Las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son código administrado, pero la mayoría de los programas [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] existentes están escritos en [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] no administrado.  No es posible llamar a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] desde un verdadero programa no administrado.  Sin embargo, utilizando la opción `/clr` con el compilador [!INCLUDE[TLA#tla_visualcpp](../../../../includes/tlasharptla-visualcpp-md.md)], es posible crear un programa mixto administrado\-no administrado, donde puede mezclar de manera transparente llamadas [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] administradas y no administradas.  
  
 Una complicación del nivel del proyecto es que no es posible compilar archivos [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en un proyecto [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)].  Hay varias técnicas de división de proyectos para compensarlo.  
  
-   Cree una DLL [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] que contenga todas las páginas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como un ensamblado de compilación y, a continuación, haga que el ejecutable [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] incluya esa [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] como una referencia.  
  
-   Cree un ejecutable [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] para el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y haga que use como referencia una [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] que incluya el contenido [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
-   Utilice <xref:System.Windows.Markup.XamlReader.Load%2A> para cargar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], en tiempo de ejecución, en lugar de compilar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
-   No utilice en absoluto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y escriba todo el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en código, construyendo al árbol de elementos desde <xref:System.Windows.Application>.  
  
 Utilice el enfoque que funcione mejor para usted.  
  
> [!NOTE]
>  Si no ha utilizado [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] antes, quizás observe algunas palabras clave “nuevas” como `gcnew` y `nullptr` en los ejemplos de código de interoperación. Estas palabras clave reemplazan la sintaxis más antigua de doble\- subrayado \(`__gc`\) y proporcionan una sintaxis más natural para el código administrado en [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)].  Para obtener más información sobre las características administradas de [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)], vea [Extensiones de componentes para plataformas de tiempo de ejecución](../Topic/Component%20Extensions%20for%20Runtime%20Platforms.md) y [Hello, C\+\+\/CLI](http://go.microsoft.com/fwlink/?LinkId=98739).  
  
<a name="hwnds"></a>   
## Cómo WPF utiliza Hwnd  
 Para aprovechar al máximo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] "HWND interop", debe entender cómo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza HWND.  Para cualquier HWND, no es posible mezclar la representación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la representación de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] o la de [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] \/ [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)].  Esto tiene varias implicaciones.  En primer lugar, para mezclar estos modelos de representación debe crear una solución de interoperación y usar segmentos designados de interoperación para cada modelo de la representación que decida utilizar.  Además, el comportamiento de representación crea una restricción de "espacio aéreo" para lo que la solución de interoperación puede lograr.  El concepto de "espacio aéreo" se explica con mayor detalle en el tema [Información general sobre áreas de la tecnología](../../../../docs/framework/wpf/advanced/technology-regions-overview.md).  
  
 Todos los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de la pantalla están respaldados, en último término, por un HWND.  Al crear un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Window>, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se crea un HWND de nivel superior, que utiliza un objeto <xref:System.Windows.Interop.HwndSource> para colocar el objeto <xref:System.Windows.Window> y su contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro del HWND.  El resto del contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de la aplicación comparte ese HWND singular.  Una excepción son los menús, los elementos desplegables de los cuadros combinados y otros elementos emergentes.  Estos elementos crean su propia ventana de nivel superior, que es la causa de que un menú de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pueda ir más allá del borde del HWND de la ventana que lo contiene.  Al utilizar <xref:System.Windows.Interop.HwndHost> para colocar un HWND dentro de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] informa a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] de cómo colocar el nuevo HWND secundario respecto al HWND <xref:System.Windows.Window> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Un concepto relacionado con HWND es la transparencia dentro de y entre HWND.  Esto también se explica en el tema [Información general sobre áreas de la tecnología](../../../../docs/framework/wpf/advanced/technology-regions-overview.md).  
  
<a name="hosting_a_wpf_page"></a>   
## Hospedar contenido WPF en una ventana Microsoft Win32  
 La clave para hospedar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] es la clase <xref:System.Windows.Interop.HwndSource>.  Esta clase envuelve el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], para que el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se pueda incorporar en la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] como una ventana secundaria.  El enfoque siguiente combina [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una aplicación única.  
  
1.  Implemente el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \(el elemento raíz del contenido\) como una clase administrada.  Normalmente, la clase hereda de una de las clases que pueden contener varios elementos secundarios y\/o utilizarse como un elemento raíz, tales como <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.Page>.  En pasos subsiguientes, esta clase se conoce como la clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y a las instancias de la clase se hace referencia como objetos de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
2.  Implemente una aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] con [!INCLUDE[TLA2#tla_cppcli](../../../../includes/tla2sharptla-cppcli-md.md)].  Si se está empezando con una aplicación de [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] no administrada existente, normalmente se puede habilitar para que llame al código administrado cambiando la configuración del proyecto, de modo que incluya la marca de compilador `/clr` \(en este tema no se describe el ámbito completo de lo que puede ser necesario para admitir la compilación `/clr`\).  
  
3.  Establezca el modelo de subprocesos en apartamento de un único subproceso \(STA\).  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza este modelo de subprocesos.  
  
4.  Administre la notificación WM\_CREATE en el procedimiento de la ventana.  
  
5.  Dentro del controlador \(o de una función a la que llame el controlador\), haga lo siguiente:  
  
    1.  Cree un nuevo objeto <xref:System.Windows.Interop.HwndSource> con el HWND de la ventana primaria como su parámetro `parent`.  
  
    2.  Cree una instancia de la clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3.  Asigne una referencia al contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la propiedad <xref:System.Windows.Interop.HwndSource.RootVisual%2A> del objeto <xref:System.Windows.Interop.HwndSource>.  
  
    4.  La propiedad <xref:System.Windows.Interop.HwndSource.Handle%2A> del objeto <xref:System.Windows.Interop.HwndSource> contiene el controlador de la ventana \(HWND\).  Para obtener un HWND que pueda utilizar en la parte no administrada de la aplicación, convierta `Handle.ToPointer()` en un HWND.  
  
6.  Implemente una clase administrada que contiene un campo estático que contiene una referencia al objeto de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Esta clase permite recibir una referencia al objeto de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] desde el código [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] pero, lo que es más importante, evita que <xref:System.Windows.Interop.HwndSource> se someta inadvertidamente a la recolección de elementos no utilizados.  
  
7.  Reciba las notificaciones del objeto de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] adjuntando un controlador a uno o más de los eventos del objeto de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
8.  Comunicar con el objeto de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante la referencia almacenada en el campo estático para establecer propiedades, llamar a métodos, etc..  
  
> [!NOTE]
>  Puede hacer una parte o toda la definición de tipo de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para el paso Uno en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] mediante la clase parcial predeterminada de la clase de contenido, si genera un ensamblado independiente y haga referencia. Aunque se incluye normalmente un objeto de <xref:System.Windows.Application> como parte de la compilación de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en un ensamblado, no finaliza para anteriormente mediante ese <xref:System.Windows.Application> como parte de la interoperabilidad, solo usa uno o más de las clases de la raíz de los archivos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] referidos por la aplicación y hace referencia a sus clases parciales.  El resto del procedimiento es esencialmente idéntico al perfilado anteriormente.  
>   
>  Cada uno de estos pasos se muestra mediante código en el tema [Tutorial: Hospedar contenido de WPF en Win32](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md).  
  
<a name="hosting_an_hwnd"></a>   
## Hospedar una ventana Microsoft Win32 en WPF  
 La clave para hospedar una ventana [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dentro de otro contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es la clase <xref:System.Windows.Interop.HwndHost>.  Esta clase envuelve la ventana en un elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que se puede agregar a un árbol de elementos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  <xref:System.Windows.Interop.HwndHost> también admite [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] que permiten realizar tales tareas como mensajes de proceso para la ventana hospedada.  El procedimiento básico es:  
  
1.  Crear un árbol de elementos para una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \(puede hacerse mediante código o mediante marcado\).  Buscar un punto adecuado y permitido en el árbol de elementos donde la implementación <xref:System.Windows.Interop.HwndHost> se pueda agregar como un elemento secundario.  En el resto de estos pasos, este elemento se conoce como el elemento de reserva.  
  
2.  Derivar de <xref:System.Windows.Interop.HwndHost> para crear un objeto que contenga el contenido [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
3.  En esa clase de host, invalidar el método <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> de <xref:System.Windows.Interop.HwndHost>.  Devolver el HWND de la ventana hospedada.  Quizá desee envolver los controles reales como una ventana secundaria de la ventana devuelta; envolver los controles en una ventana de host es una medio sencillo para que el contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reciba notificaciones de los controles.  Esta técnica ayuda a corregir algunos problemas [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] relativos al control de mensajes en el límite del control hospedado.  
  
4.  Invalidar los métodos <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> y <xref:System.Windows.Interop.HwndHost.WndProc%2A> de <xref:System.Windows.Interop.HwndHost>.  La intención aquí es procesar la limpieza y quitar las referencias al contenido hospedado, en particular si se creó alguna referencia a objetos no administrados.  
  
5.  En el archivo de código subyacente, cree una instancia de la clase que hospeda el control y conviértala en un elemento secundario del elemento de reserva.  Normalmente utilizaría un controlador de eventos como <xref:System.Windows.FrameworkElement.Loaded> o el constructor de clase parcial.  Pero también podría agregar el contenido de interoperación mediante un comportamiento en tiempo de ejecución.  
  
6.  Procesar los mensajes de ventana seleccionados, tales como las notificaciones de control.  Hay dos enfoques.  Ambos proporcionan idéntico acceso a la secuencia de mensajes, por lo que la elección es, en gran medida, una cuestión de comodidad de programación.  
  
    -   Implementar el procesamiento de mensajes para todos los mensajes \(no solamente para los mensajes de cierre del sistema\) en la invalidación del método  <xref:System.Windows.Interop.HwndHost.WndProc%2A> de <xref:System.Windows.Interop.HwndHost>.  
  
    -   Haga que el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedador procese los mensajes administrando el evento <xref:System.Windows.Interop.HwndHost.MessageHook>.  Este evento se provoca para cada mensaje que se envía al procedimiento de ventana principal de la ventana hospedada.  
  
    -   No se puede procesar mensajes de ventanas que estén fuera del proceso utilizando <xref:System.Windows.Interop.HwndHost.WndProc%2A>.  
  
7.  Realice la comunicación con la ventana hospedada utilizando la invocación de plataforma para llamar a la función `SendMessage` no administrada.  
  
 Al seguir estos pasos, se crea una aplicación que funciona con la entrada de mouse.  Puede agregar compatibilidad con tabulación a la ventana hospedada implementando la interfaz <xref:System.Windows.Interop.IKeyboardInputSink>.  
  
 Cada uno de estos pasos se muestra mediante código en el tema [Tutorial: Hospedar un control de Win32 en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md).  
  
### Hwnds dentro de WPF  
 Puede pensar en <xref:System.Windows.Interop.HwndHost> como en un control especial.  \(Técnicamente, <xref:System.Windows.Interop.HwndHost> es una clase derivada de <xref:System.Windows.FrameworkElement>, no una clase derivada de <xref:System.Windows.Controls.Control>, pero puede considerarse un control a efectos de la interoperación\). <xref:System.Windows.Interop.HwndHost> abstrae la naturaleza de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] subyacente del contenido hospedado de modo que el resto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] considera que el contenido hospedado es otro objeto de tipo control, que debe presentar y procesar entradas.  <xref:System.Windows.Interop.HwndHost> se comporta generalmente como cualquier otro objeto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>, aunque hay algunas diferencias importantes relacionadas con la salida \(dibujo y gráficos\) y la entrada \(mouse y teclado\) basadas en las limitaciones de compatibilidad de los HWND subyacentes.  
  
#### Diferencias notables en el comportamiento de salida  
  
-   <xref:System.Windows.FrameworkElement>, que es la clase base de <xref:System.Windows.Interop.HwndHost>, tiene varias propiedades que implican cambios en la interfaz de usuario.  Entre ellas hay propiedades como <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=fullName>, que cambia el diseño de los elementos que hay dentro de ese elemento como un elemento primario.  Sin embargo, la mayoría de estas propiedades no están asignadas a posibles equivalentes [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], aun cuando puedan existir tales equivalentes.  Demasiadas de estas propiedades y sus significados son demasiado específicas de la tecnología de representación para que las asignaciones resulten prácticas.  Por consiguiente, establecer propiedades como <xref:System.Windows.FrameworkElement.FlowDirection%2A> en <xref:System.Windows.Interop.HwndHost> no tiene ningún efecto.  
  
-   <xref:System.Windows.Interop.HwndHost> no se puede rotar, escalar, sesgar ni verse afectada de ningún otro modo por una transformación.  
  
-   <xref:System.Windows.Interop.HwndHost> no admite la propiedad <xref:System.Windows.UIElement.Opacity%2A> \(mezcla alfa\).  Si el contenido de <xref:System.Windows.Interop.HwndHost> realiza operaciones <xref:System.Drawing> que incluyan información alfa, no se trata de una infracción, pero el objeto <xref:System.Windows.Interop.HwndHost> en conjunto sólo admite Opacidad \= 1,0 \(100%\).  
  
-   <xref:System.Windows.Interop.HwndHost> aparecerá encima de otros elementos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en la misma ventana de nivel superior.  Sin embargo, un menú generado por <xref:System.Windows.Controls.ToolTip> o <xref:System.Windows.Controls.ContextMenu> es una ventana de nivel superior independiente y, por lo tanto, se comporta correctamente con <xref:System.Windows.Interop.HwndHost>.  
  
-   <xref:System.Windows.Interop.HwndHost> no respeta la zona de recorte de su objeto <xref:System.Windows.UIElement> primario.  Esto puede ser un problema si intenta colocar una clase <xref:System.Windows.Interop.HwndHost> dentro de un área de desplazamiento o de un control <xref:System.Windows.Controls.Canvas>.  
  
#### Diferencias notables en el comportamiento de entrada  
  
-   En general, mientras los dispositivos de entrada estén en el ámbito de la región [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] hospedad en <xref:System.Windows.Interop.HwndHost>, los eventos de entrada van directamente a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
-   Aunque el mouse esté encima del objeto <xref:System.Windows.Interop.HwndHost>, la aplicación no recibirá eventos del mouse [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y el valor de la propiedad [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.UIElement.IsMouseOver%2A> será `false`.  
  
-   Aunque <xref:System.Windows.Interop.HwndHost> tiene el foco de teclado, la aplicación no recibirá eventos de teclado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y el valor de la propiedad [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> será `false`.  
  
-   Cuando el foco está dentro de <xref:System.Windows.Interop.HwndHost> y cambia a otro control dentro del objeto <xref:System.Windows.Interop.HwndHost>, la aplicación no recibirá los eventos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.UIElement.GotFocus> o <xref:System.Windows.UIElement.LostFocus>.  
  
-   Las propiedades y eventos de lápiz relacionados son análogos y no proporcionan información mientras el lápiz está encima del objeto <xref:System.Windows.Interop.HwndHost>.  
  
<a name="tabbing_mnemonics_accelerators"></a>   
## Tabulación, teclas de acceso y aceleradores  
 Las interfaces <xref:System.Windows.Interop.IKeyboardInputSink> y <xref:System.Windows.Interop.IKeyboardInputSite> permiten usar el teclado sin diferencias en una mezcla de aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]:  
  
-   Tabulación entre componentes [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
-   Las teclas de acceso y los aceleradores funcionan tanto cuando el foco está dentro de un componente Win32 como cuando está dentro de un componente WPF.  
  
 Las clases <xref:System.Windows.Interop.HwndHost> y <xref:System.Windows.Interop.HwndSource> proporcionan implementaciones de <xref:System.Windows.Interop.IKeyboardInputSink>, pero no pueden administrar todos los mensajes de entrada que se desean para escenarios más avanzados.  Invalide los métodos adecuados para obtener el comportamiento de teclado que desee.  
  
 Las interfaces solamente proporcionan compatibilidad para lo que ocurre en la transición entre las regiones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Dentro de la región [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], el comportamiento de tabulación está completamente controlado por la lógica [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] implementada para la tabulación, si existe.  
  
## Vea también  
 <xref:System.Windows.Interop.HwndHost>   
 <xref:System.Windows.Interop.HwndSource>   
 <xref:System.Windows.Interop>   
 [Tutorial: Hospedar un control de Win32 en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md)   
 [Tutorial: Hospedar contenido de WPF en Win32](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md)