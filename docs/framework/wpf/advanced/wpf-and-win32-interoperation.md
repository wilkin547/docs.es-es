---
title: Interoperabilidad de WPF y Win32
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: 71c454edc6a124f732f1e6b56e25c28671fa11b6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053176"
---
# <a name="wpf-and-win32-interoperation"></a>Interoperabilidad de WPF y Win32
En este tema se proporciona información general sobre cómo interoperar código de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Pero, si ha hecho una inversión sustancial en código de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], podría resultar más efectivo reutilizar parte de ese código.  

<a name="basics"></a>   
## <a name="wpf-and-win32-interoperation-basics"></a>Conceptos básicos de interoperación de WPF y Win32  
 Hay dos técnicas básicas de la interoperación entre el código de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
- Hospedar contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Con esta técnica puede usar las capacidades gráficas avanzadas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en el marco de una ventana y aplicación estándar de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
- Hospedar una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] en un contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Con esta técnica puede usar un control personalizado de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] existente en el contexto de otro contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y pasar datos a través de los límites.  
  
 Todas estas técnicas se presentan conceptualmente en este tema. Para ver una ilustración más orientada al código de hospedaje [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], consulte [Tutorial: Hospedar contenido WPF en Win32](walkthrough-hosting-wpf-content-in-win32.md). Para ver una ilustración más orientada al código de hospedaje [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Tutorial: Hospedar un Control de Win32 en WPF](walkthrough-hosting-a-win32-control-in-wpf.md).  
  
<a name="projects"></a>   
## <a name="wpf-interoperation-projects"></a>Proyectos de interoperación de WPF  
 Las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son código administrado, pero la mayoría de los programas existentes de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] están escritos en [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] no administrado.  No puede llamar a las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] desde un auténtico programa no administrado, pero puede usar la opción `/clr` con el compilador de [!INCLUDE[TLA#tla_visualcpp](../../../../includes/tlasharptla-visualcpp-md.md)] para crear un programa mixto (administrado-no administrado), en el que puede combinar perfectamente llamadas de [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] administradas y no administradas.  
  
 Una desventaja a nivel de proyecto es que no puede compilar archivos [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en un proyecto de [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)].  Existen varias técnicas de división de proyectos para compensarlo.  
  
- Cree una DLL de C# que contiene todos sus [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] páginas como un ensamblado compilado y, a continuación, tiene su [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] ejecutable que incluyen [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] como referencia.  
  
- Crear C# ejecutable para el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de contenido y lo hacen referencia a un [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] que contiene el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] contenido.  
  
- Use <xref:System.Windows.Markup.XamlReader.Load%2A> cargará todos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en tiempo de ejecución, en lugar de compilar su [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
- No use [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en absoluto y escribir todo su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en código, compilar el árbol de elementos de <xref:System.Windows.Application>.  
  
 Use el método que se adapte mejor a sus necesidades.  
  
> [!NOTE]
>  Si no ha usado [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] antes, observará algunas palabras clave "nuevas", como `gcnew` y `nullptr`, en los ejemplos de código de interoperación. Estas palabras clave reemplazan la anterior sintaxis de doble subrayado (`__gc`) y proporcionan una sintaxis más natural para el código administrado en [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)].  Para obtener más información sobre las características administradas de [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)], consulte [Extensiones de componentes para plataformas de tiempo de ejecución](/cpp/windows/component-extensions-for-runtime-platforms) y [Hello, C++/CLI](https://go.microsoft.com/fwlink/?LinkId=98739) (Hola, C++/CLI).  
  
<a name="hwnds"></a>   
## <a name="how-wpf-uses-hwnds"></a>Cómo WPF usa los HWND  
 Para aprovechar al máximo la "interoperación de HWND" de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], debe comprender cómo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa los HWND. En ningún HWND se puede mezclar la representación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con la representación de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] o la representación de [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] / [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)]. Esto tiene varias implicaciones. En primer lugar, para poder mezclar estos modelos de representación, debe crear una solución de interoperación y usar segmentos de interoperación designados para cada modelo de representación que quiera usar. Además, el comportamiento de representación crea una restricción de "espacio aéreo" de lo que puede llevar a cabo su solución de interoperación. El concepto "espacio aéreo" se describe más detalladamente en el tema [Información general sobre áreas de la tecnología](technology-regions-overview.md).  
  
 Todos los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de la pantalla están respaldados en última instancia por un HWND. Cuando creas un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window>, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea un HWND de nivel superior y usa un <xref:System.Windows.Interop.HwndSource> para colocar el <xref:System.Windows.Window> y su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido dentro del HWND.  El resto del contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de la aplicación comparte ese HWND en concreto. Una excepción son los menús, los menús desplegables de cuadro combinado y otros elementos emergentes. Estos elementos crean su propia ventana de nivel superior, razón por la cual un menú de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede exceder el borde del HWND de ventana que lo contiene. Cuando usas <xref:System.Windows.Interop.HwndHost> para colocar un HWND dentro de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] informa a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] cómo colocar el nuevo HWND secundario con relación a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND.  
  
 Un concepto relacionado con HWND es la transparencia dentro de cada HWND y entre cada uno de ellos. Esto también se describe en el tema [Información general sobre áreas de la tecnología](technology-regions-overview.md).  
  
<a name="hosting_a_wpf_page"></a>   
## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>Hospedar contenido de WPF en una ventana de Microsoft Win32  
 La clave para hospedar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana es la <xref:System.Windows.Interop.HwndSource> clase. Esta clase encapsula el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], de manera que el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se puede incorporar en su [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] como una ventana secundaria. El siguiente enfoque combina [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una única aplicación.  
  
1. Implemente su contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (el elemento raíz del contenido) como una clase administrada. Normalmente, la clase hereda de una de las clases que pueden contener varios elementos secundarios o que se usan como un elemento raíz, como <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.Page>. En los siguientes pasos se hace referencia a esta clase como "clase de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]", mientras que las instancias de la clase se denominan "objetos de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]".  
  
2. Implemente una aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] con [!INCLUDE[TLA2#tla_cppcli](../../../../includes/tla2sharptla-cppcli-md.md)]. Si está empezando con una aplicación existente de [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] no administrada, normalmente puede habilitarla para llamar al código administrado cambiando la configuración del proyecto para incluir el indicador del compilador `/clr` (en este tema no se describe el ámbito completo de lo que podría necesitarse para admitir la compilación de `/clr`).  
  
3. Establezca el modelo de subprocesos en Contenedor uniproceso (STA). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa este modelo de subprocesamiento.  
  
4. Controle la notificación WM_CREATE en el procedimiento de ventana.  
  
5. En el controlador (o en una función a la que llama el controlador), haga lo siguiente:  
  
    1. Cree un nuevo <xref:System.Windows.Interop.HwndSource> objeto con la ventana primaria HWND como su `parent` parámetro.  
  
    2. Cree una instancia de su clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3. Asigne una referencia a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objeto de contenido para el <xref:System.Windows.Interop.HwndSource> objeto <xref:System.Windows.Interop.HwndSource.RootVisual%2A> propiedad.  
  
    4. El <xref:System.Windows.Interop.HwndSource> objeto <xref:System.Windows.Interop.HwndSource.Handle%2A> propiedad contiene el identificador de ventana (HWND). Para obtener un HWND que se pueda usar en la parte de la aplicación no administrada, convierta `Handle.ToPointer()` en un HWND.  
  
6. Implemente una clase administrada que contenga un campo estático para contener una referencia al objeto de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Esta clase le permite obtener una referencia a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objeto de contenido de su [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] código, pero más importante impide que su <xref:System.Windows.Interop.HwndSource> se recolecte de forma inadvertida.  
  
7. Adjunte un identificador a uno o varios de los eventos del objeto de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para recibir notificaciones del objeto de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
8. Comuníquese con el objeto de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante la referencia que almacenó en el campo estático para establecer propiedades, llamar a métodos, etc.  
  
> [!NOTE]
>  Puede hacer una parte o toda la definición de clase de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para el primer paso en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usando la clase parcial predeterminada de la clase de contenido. Para ello, debe crear un ensamblado independiente y hacer referencia a este. Aunque se suelen incluir un <xref:System.Windows.Application> objeto como parte de la compilación la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en un ensamblado, no acabará usando que <xref:System.Windows.Application> como parte de la interoperación, usa solo uno o varias de las clases raíz para [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivos hace referenciados para la aplicación y hacer referencia a sus clases parciales. El resto del procedimiento es muy similar al descrito anteriormente.  
>   
>  Cada uno de estos pasos se describen mediante código en el tema [Tutorial: Hospedar contenido WPF en Win32](walkthrough-hosting-wpf-content-in-win32.md).  
  
<a name="hosting_an_hwnd"></a>   
## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>Hospedar una ventana de Microsoft Win32 en WPF  
 La clave para hospedar un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ventana dentro de otros [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] está contenido el <xref:System.Windows.Interop.HwndHost> clase. Esta clase encapsula la ventana en un elemento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que se puede agregar a un árbol de elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Interop.HwndHost> también admite [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] que permiten realizar tareas como procesar los mensajes para la ventana hospedada. El procedimiento básico es el siguiente:  
  
1. Cree un árbol de elementos para una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (se puede efectuar mediante código o mediante marcado). Buscar un punto adecuado y permitido en el árbol de elementos donde el <xref:System.Windows.Interop.HwndHost> implementación puede agregarse como un elemento secundario. En el resto de estos pasos, este elemento se conoce como el "elemento de reserva".  
  
2. Derivar de <xref:System.Windows.Interop.HwndHost> para crear un objeto que contiene su [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] contenido.  
  
3. En esa clase de host, invalide el <xref:System.Windows.Interop.HwndHost> método <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>. Devuelva el HWND de la ventana hospedada. Tal vez quiera encapsular los controles reales como una ventana secundaria de la ventana devuelta; el encapsulamiento de los controles en una ventana host es una manera sencilla que tiene el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para recibir notificaciones de los controles. Esta técnica ayuda a corregir algunos problemas de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] relacionados con el control de los mensajes en el límite del control hospedado.  
  
4. Invalidar el <xref:System.Windows.Interop.HwndHost> métodos <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> y <xref:System.Windows.Interop.HwndHost.WndProc%2A>. Aquí, la intención es procesar una limpieza y quitar las referencias al contenido hospedado, sobre todo si creó referencias a objetos no administrados.  
  
5. En el archivo de código subyacente, cree una instancia del control que hospeda la clase y conviértalo en un elemento secundario del elemento de reserva. Normalmente se usa un controlador de eventos como <xref:System.Windows.FrameworkElement.Loaded>, o utilice el constructor de clase parcial. pero también podría agregar el contenido de interoperación mediante un comportamiento en tiempo de ejecución.  
  
6. Procese los mensajes de la ventana seleccionada, como las notificaciones de control. Existen dos enfoques. Ambos proporcionan el mismo acceso a la secuencia de mensajes, por lo que su elección es más bien una cuestión de comodidad a la hora de programar.  
  
    - Mensaje implemente procesamiento para todos los mensajes (no solo los mensajes de cierre) en la invalidación de la <xref:System.Windows.Interop.HwndHost> método <xref:System.Windows.Interop.HwndHost.WndProc%2A>.  
  
    - Tiene el hospedaje [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento procesar los mensajes administrando el <xref:System.Windows.Interop.HwndHost.MessageHook> eventos. Este evento se genera para cada mensaje que se envía al procedimiento de ventana principal de la ventana hospedada.  
  
    - No se puede procesar mensajes de ventanas que están fuera del proceso utilizando <xref:System.Windows.Interop.HwndHost.WndProc%2A>.  
  
7. Comuníquese con la ventana hospedada usando una invocación de plataforma para llamar a la función `SendMessage` no administrada.  
  
 Si sigue estos pasos, creará una aplicación que funcionará con la entrada del ratón. Puede agregar compatibilidad de tabulación a la ventana hospedada implementando la <xref:System.Windows.Interop.IKeyboardInputSink> interfaz.  
  
 Cada uno de estos pasos se describen mediante código en el tema [Tutorial: Hospedar un Control de Win32 en WPF](walkthrough-hosting-a-win32-control-in-wpf.md).  
  
### <a name="hwnds-inside-wpf"></a>HWND dentro de WPF  
 Puede pensar en <xref:System.Windows.Interop.HwndHost> como un control especial. (Técnicamente, <xref:System.Windows.Interop.HwndHost> es un <xref:System.Windows.FrameworkElement> clase derivada, no un <xref:System.Windows.Controls.Control> clase derivada, pero puede considerarse un control a efectos de interoperación.) <xref:System.Windows.Interop.HwndHost> abstrae subyacente [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] naturaleza del contenido hospedado tal que el resto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] considera que el contenido hospedado como otro objeto de tipo control, que debe representar y procesar la entrada. <xref:System.Windows.Interop.HwndHost> por lo general se comporta como cualquier otro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>, aunque hay algunas diferencias importantes en torno a la salida (dibujos y gráficos) y puede admitir la entrada (ratón y teclado) en función de las limitaciones de los HWND subyacentes.  
  
#### <a name="notable-differences-in-output-behavior"></a>Diferencias notables en el comportamiento de salida  
  
- <xref:System.Windows.FrameworkElement>, que es el <xref:System.Windows.Interop.HwndHost> clase base, tiene varias propiedades que implican cambios en la interfaz de usuario. Estos incluyen propiedades como <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>, que cambia el diseño de elementos dentro de ese elemento como elemento primario. Pero la mayoría de estas propiedades no están asignadas a posibles equivalentes de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], aunque dichos equivalentes existieran. Demasiadas de estas propiedades y de sus significados son tan específicos de la tecnología de representación que las asignaciones no resultan prácticas. Por lo tanto, establecer propiedades como <xref:System.Windows.FrameworkElement.FlowDirection%2A> en <xref:System.Windows.Interop.HwndHost> no tiene ningún efecto.  
  
- <xref:System.Windows.Interop.HwndHost> no puede ser a girar, escala, sesgados o en caso contrario afectada por una transformación.  
  
- <xref:System.Windows.Interop.HwndHost> no admite la <xref:System.Windows.UIElement.Opacity%2A> propiedad (combinación alfa). Si el contenido dentro de la <xref:System.Windows.Interop.HwndHost> realiza <xref:System.Drawing> operaciones que incluyen información alfa, que sí misma no es una infracción, pero el <xref:System.Windows.Interop.HwndHost> como un todo solo admite una opacidad de 1,0 (100%).  
  
- <xref:System.Windows.Interop.HwndHost> aparecerá encima de otro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos en la misma ventana de nivel superior. Sin embargo, un <xref:System.Windows.Controls.ToolTip> o <xref:System.Windows.Controls.ContextMenu> menú generado es una ventana de nivel superior independiente y, por lo tanto, se comportará correctamente con <xref:System.Windows.Interop.HwndHost>.  
  
- <xref:System.Windows.Interop.HwndHost> no respeta la zona de recorte de su elemento primario <xref:System.Windows.UIElement>. Esto es potencialmente un problema si intenta colocar un <xref:System.Windows.Interop.HwndHost> clase dentro de una región desplazable o <xref:System.Windows.Controls.Canvas>.  
  
#### <a name="notable-differences-in-input-behavior"></a>Diferencias notables en el comportamiento de entrada  
  
- En general, mientras que los dispositivos de entrada tienen el ámbito de la <xref:System.Windows.Interop.HwndHost> hospedado [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] región, los eventos de entrada vayan directamente a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
- Mientras el mouse está sobre el <xref:System.Windows.Interop.HwndHost>, la aplicación no recibe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] los eventos del mouse y el valor de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedad <xref:System.Windows.UIElement.IsMouseOver%2A> será `false`.  
  
- Mientras el <xref:System.Windows.Interop.HwndHost> tiene el foco de teclado, la aplicación no recibirá [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventos de teclado y el valor de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedad <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> será `false`.  
  
- Cuando el foco está en el <xref:System.Windows.Interop.HwndHost> y los cambios realizados en otro control dentro de la <xref:System.Windows.Interop.HwndHost>, la aplicación no recibirá la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventos <xref:System.Windows.UIElement.GotFocus> o <xref:System.Windows.UIElement.LostFocus>.  
  
- Relacionadas con eventos y propiedades de lápiz son análogos y no proporcionan información mientras el lápiz está sobre <xref:System.Windows.Interop.HwndHost>.  
  
<a name="tabbing_mnemonics_accelerators"></a>   
## <a name="tabbing-mnemonics-and-accelerators"></a>Tabulación, teclas de acceso y aceleradores  
 El <xref:System.Windows.Interop.IKeyboardInputSink> y <xref:System.Windows.Interop.IKeyboardInputSite> interfaces le permiten crear una experiencia perfecta de teclado para mixto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] aplicaciones:  
  
- Tabulación entre componentes de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
- Las teclas de acceso y los aceleradores que funcionan tanto si el foco está dentro de un componente de Win32 como si está dentro de un componente de WPF.  
  
 El <xref:System.Windows.Interop.HwndHost> y <xref:System.Windows.Interop.HwndSource> clases proporcionan implementaciones de <xref:System.Windows.Interop.IKeyboardInputSink>, pero no pueden administrar todos los mensajes de entrada que desee para escenarios más avanzados. Invalide los métodos adecuados para obtener el comportamiento de teclado que quiera.  
  
 Las interfaces solo proporcionan compatibilidad para lo que ocurre en la transición entre las zonas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Dentro de la zona de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], el comportamiento de la tabulación está totalmente controlado por la lógica implementada de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] de la tabulación, en el caso de que la haya.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.HwndHost>
- <xref:System.Windows.Interop.HwndSource>
- <xref:System.Windows.Interop>
- [Tutorial: Hospedar un Control de Win32 en WPF](walkthrough-hosting-a-win32-control-in-wpf.md)
- [Tutorial: Hospedar contenido WPF en Win32](walkthrough-hosting-wpf-content-in-win32.md)
