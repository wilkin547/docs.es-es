---
title: Interoperabilidad de WPF y Win32
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: a942d72f27d394d31a52fd02ecaa158add4d2e0f
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484631"
---
# <a name="wpf-and-win32-interoperation"></a>Interoperabilidad de WPF y Win32
En este tema se proporciona información general sobre cómo interoperar código de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Pero, si ha hecho una inversión sustancial en código de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], podría resultar más efectivo reutilizar parte de ese código.  

<a name="basics"></a>   
## <a name="wpf-and-win32-interoperation-basics"></a>Conceptos básicos de interoperación de WPF y Win32  
 Hay dos técnicas básicas de la interoperación entre el código de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
- Hospedar contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Con esta técnica puede usar las capacidades gráficas avanzadas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en el marco de una ventana y aplicación estándar de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
- Hospedar una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] en un contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Con esta técnica puede usar un control personalizado de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] existente en el contexto de otro contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y pasar datos a través de los límites.  
  
 Todas estas técnicas se presentan conceptualmente en este tema. Para obtener más información orientada al código sobre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]hospedaje en [, vea Tutorial: Hospedar contenido de WPF](walkthrough-hosting-wpf-content-in-win32.md)en Win32. Para obtener más información orientada al código sobre [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]hospedaje en [, vea Tutorial: Hospedar un control de Win32](walkthrough-hosting-a-win32-control-in-wpf.md)en WPF.  
  
<a name="projects"></a>   
## <a name="wpf-interoperation-projects"></a>Proyectos de interoperación de WPF  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Las API son código administrado, pero la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] mayoría de los programas existentes están escritos C++en no administrado.  No se puede [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llamar a las API desde un auténtico programa no administrado. Sin embargo, si se `/clr` usa la opción [!INCLUDE[TLA#tla_visualcpp](../../../../includes/tlasharptla-visualcpp-md.md)] con el compilador, se puede crear un programa mixto administrado-no administrado en el que se puedan combinar sin problemas llamadas API administradas y no administradas.  
  
 Una complicación de nivel de proyecto es que no [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] se pueden compilar archivos en un C++ proyecto.  Existen varias técnicas de división de proyectos para compensarlo.  
  
- Cree un C# archivo DLL que contenga [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] todas las páginas como un ensamblado compilado y, C++ después, haga que [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] el ejecutable lo incluya como referencia.  
  
- Cree un C# archivo ejecutable para el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido y haga referencia a un C++ [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] que contenga el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] contenido.  
  
- Use <xref:System.Windows.Markup.XamlReader.Load%2A> para cargar cualquier [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en tiempo de ejecución, en lugar de compilar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
- No use [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en absoluto y escriba [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] todo en el código, creando el árbol de elementos a partir de <xref:System.Windows.Application>.  
  
 Use el método que se adapte mejor a sus necesidades.  
  
> [!NOTE]
>  Si no ha usado C++/CLI antes, es posible que observe algunas palabras clave "nuevas" como `gcnew` y `nullptr` en los ejemplos de código de interoperación. Estas palabras clave reemplazan la sintaxis de doble subrayado`__gc`anterior () y proporcionan una sintaxis más natural para el C++código administrado en.  Para obtener más información sobre C++las características administradas de/CLI, vea [extensiones de componentes para plataformas en tiempo de ejecución](/cpp/windows/component-extensions-for-runtime-platforms) y [Hola, C++/CLI](https://go.microsoft.com/fwlink/?LinkId=98739).  
  
<a name="hwnds"></a>   
## <a name="how-wpf-uses-hwnds"></a>Cómo WPF usa los HWND  
 Para aprovechar al máximo la "interoperación de HWND" de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], debe comprender cómo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa los HWND. En ningún HWND se puede mezclar la representación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con la representación de [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] o la representación de [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] / [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)]. Esto tiene varias implicaciones. En primer lugar, para poder mezclar estos modelos de representación, debe crear una solución de interoperación y usar segmentos de interoperación designados para cada modelo de representación que quiera usar. Además, el comportamiento de representación crea una restricción de "espacio aéreo" de lo que puede llevar a cabo su solución de interoperación. El concepto "espacio aéreo" se describe más detalladamente en el tema [Información general sobre áreas de la tecnología](technology-regions-overview.md).  
  
 Todos los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de la pantalla están respaldados en última instancia por un HWND. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Al crear un <xref:System.Windows.Window>, <xref:System.Windows.Interop.HwndSource> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]creaunHWNDde nivel superior y utiliza para colocar ysucontenidodentrodelHWND.<xref:System.Windows.Window> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  El resto del contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de la aplicación comparte ese HWND en concreto. Una excepción son los menús, los menús desplegables de cuadro combinado y otros elementos emergentes. Estos elementos crean su propia ventana de nivel superior, razón por la cual un menú de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede exceder el borde del HWND de ventana que lo contiene. Cuando se usa <xref:System.Windows.Interop.HwndHost> para colocar un HWND dentro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , informa [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] a cómo colocar el nuevo HWND secundario en relación con el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND.  
  
 Un concepto relacionado con HWND es la transparencia dentro de cada HWND y entre cada uno de ellos. Esto también se describe en el tema [Información general sobre áreas de la tecnología](technology-regions-overview.md).  
  
<a name="hosting_a_wpf_page"></a>   
## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>Hospedar contenido de WPF en una ventana de Microsoft Win32  
 La clave para hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un en [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] una ventana de <xref:System.Windows.Interop.HwndSource> es la clase. Esta clase encapsula el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], de manera que el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se puede incorporar en su [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] como una ventana secundaria. El siguiente enfoque combina [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una única aplicación.  
  
1. Implemente su contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (el elemento raíz del contenido) como una clase administrada. Normalmente, la clase hereda de una de las clases que pueden contener varios elementos secundarios o usarse como un elemento raíz, <xref:System.Windows.Controls.DockPanel> como o. <xref:System.Windows.Controls.Page> En los siguientes pasos se hace referencia a esta clase como "clase de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]", mientras que las instancias de la clase se denominan "objetos de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]".  
  
2. Implementar una aplicación de Windows C++con/CLI. Si está empezando con una C++ aplicación no administrada existente, normalmente puede habilitarla para llamar a código administrado cambiando la configuración del proyecto para incluir la `/clr` marca del compilador (el ámbito completo de lo que podría ser necesario admitir `/clr` ). la compilación no se describe en este tema).  
  
3. Establezca el modelo de subprocesos en Contenedor uniproceso (STA). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa este modelo de subprocesamiento.  
  
4. Controle la notificación WM_CREATE en el procedimiento de ventana.  
  
5. En el controlador (o en una función a la que llama el controlador), haga lo siguiente:  
  
    1. Cree un nuevo <xref:System.Windows.Interop.HwndSource> objeto con el HWND de la ventana primaria `parent` como su parámetro.  
  
    2. Cree una instancia de su clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3. Asigne una referencia al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objeto de contenido a la <xref:System.Windows.Interop.HwndSource> propiedad de objeto. <xref:System.Windows.Interop.HwndSource.RootVisual%2A>  
  
    4. La <xref:System.Windows.Interop.HwndSource> propiedad <xref:System.Windows.Interop.HwndSource.Handle%2A> de objeto contiene el identificador de ventana (HWND). Para obtener un HWND que se pueda usar en la parte de la aplicación no administrada, convierta `Handle.ToPointer()` en un HWND.  
  
6. Implemente una clase administrada que contenga un campo estático para contener una referencia al objeto de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Esta clase le permite obtener una referencia al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] objeto de contenido desde el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] código, pero lo más importante es que impide que <xref:System.Windows.Interop.HwndSource> se recopile involuntariamente el elemento no utilizado.  
  
7. Adjunte un identificador a uno o varios de los eventos del objeto de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para recibir notificaciones del objeto de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
8. Comuníquese con el objeto de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante la referencia que almacenó en el campo estático para establecer propiedades, llamar a métodos, etc.  
  
> [!NOTE]
>  Puede hacer una parte o toda la definición de clase de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para el primer paso en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usando la clase parcial predeterminada de la clase de contenido. Para ello, debe crear un ensamblado independiente y hacer referencia a este. Aunque <xref:System.Windows.Application> normalmente incluye un objeto como parte de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compilación en un ensamblado, <xref:System.Windows.Application> no termina de usarlo como parte de la interoperación, solo se usan una o varias de las clases raíz para los archivos a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] los que se hace referencia. a por la aplicación y hacen referencia a sus clases parciales. El resto del procedimiento es muy similar al descrito anteriormente.  
>   
>  Cada uno de estos pasos se muestra en el código del [tema Tutorial: Hospedar contenido de WPF](walkthrough-hosting-wpf-content-in-win32.md)en Win32.  
  
<a name="hosting_an_hwnd"></a>   
## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>Hospedar una ventana de Microsoft Win32 en WPF  
 La clave para hospedar [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] una ventana dentro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de otro contenido <xref:System.Windows.Interop.HwndHost> es la clase. Esta clase encapsula la ventana en un elemento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que se puede agregar a un árbol de elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Interop.HwndHost>también admite las API que le permiten realizar tareas como procesar mensajes para la ventana hospedada. El procedimiento básico es el siguiente:  
  
1. Cree un árbol de elementos para una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (se puede efectuar mediante código o mediante marcado). Busque un punto adecuado y permisible en el árbol de elementos donde <xref:System.Windows.Interop.HwndHost> la implementación se puede agregar como elemento secundario. En el resto de estos pasos, este elemento se conoce como el "elemento de reserva".  
  
2. Derive de <xref:System.Windows.Interop.HwndHost> para crear un objeto que contenga [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] el contenido.  
  
3. En esa clase de host, invalide el <xref:System.Windows.Interop.HwndHost> método. <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> Devuelva el HWND de la ventana hospedada. Tal vez quiera encapsular los controles reales como una ventana secundaria de la ventana devuelta; el encapsulamiento de los controles en una ventana host es una manera sencilla que tiene el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para recibir notificaciones de los controles. Esta técnica ayuda a corregir algunos problemas de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] relacionados con el control de los mensajes en el límite del control hospedado.  
  
4. Invalide <xref:System.Windows.Interop.HwndHost> los <xref:System.Windows.Interop.HwndHost.WndProc%2A>métodos <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> y. Aquí, la intención es procesar una limpieza y quitar las referencias al contenido hospedado, sobre todo si creó referencias a objetos no administrados.  
  
5. En el archivo de código subyacente, cree una instancia del control que hospeda la clase y conviértalo en un elemento secundario del elemento de reserva. Normalmente se usaría un controlador de eventos como <xref:System.Windows.FrameworkElement.Loaded>, o se utilizaría el constructor de clase parcial. pero también podría agregar el contenido de interoperación mediante un comportamiento en tiempo de ejecución.  
  
6. Procese los mensajes de la ventana seleccionada, como las notificaciones de control. Existen dos enfoques. Ambos proporcionan el mismo acceso a la secuencia de mensajes, por lo que su elección es más bien una cuestión de comodidad a la hora de programar.  
  
    - Implemente el procesamiento de mensajes para todos los mensajes (no solo los mensajes de cierre <xref:System.Windows.Interop.HwndHost> ) <xref:System.Windows.Interop.HwndHost.WndProc%2A>en la invalidación del método.  
  
    - Haga que el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento de hospedaje procese los mensajes controlando el <xref:System.Windows.Interop.HwndHost.MessageHook> evento. Este evento se genera para cada mensaje que se envía al procedimiento de ventana principal de la ventana hospedada.  
  
    - No se pueden procesar mensajes de ventanas que no estén en proceso <xref:System.Windows.Interop.HwndHost.WndProc%2A>mediante.  
  
7. Comuníquese con la ventana hospedada usando una invocación de plataforma para llamar a la función `SendMessage` no administrada.  
  
 Si sigue estos pasos, creará una aplicación que funcionará con la entrada del ratón. Puede Agregar compatibilidad con la tabulación para la ventana hospedada implementando la <xref:System.Windows.Interop.IKeyboardInputSink> interfaz.  
  
 Cada uno de estos pasos se muestra en el código del [tema Tutorial: Hospedar un control de Win32](walkthrough-hosting-a-win32-control-in-wpf.md)en WPF.  
  
### <a name="hwnds-inside-wpf"></a>HWND dentro de WPF  
 Puede considerar <xref:System.Windows.Interop.HwndHost> como un control especial. (Técnicamente, <xref:System.Windows.Interop.HwndHost> es una <xref:System.Windows.FrameworkElement> clase derivada, no una <xref:System.Windows.Controls.Control> clase derivada, pero se puede considerar un control a efectos de interoperación). abstrae la naturaleza subyacente [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] del contenido hospedado de forma que el resto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] considere que el contenido hospedado es otro objeto similar a un control, que debe representar y procesar la entrada. <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost>generalmente se comporta como cualquier otro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>, aunque hay algunas diferencias importantes en torno a la salida (dibujo y gráficos) y la entrada (mouse y teclado) en función de las limitaciones de lo que el HWND subyacente puede admitir.  
  
#### <a name="notable-differences-in-output-behavior"></a>Diferencias notables en el comportamiento de salida  
  
- <xref:System.Windows.FrameworkElement>, que es la <xref:System.Windows.Interop.HwndHost> clase base, tiene muy pocas propiedades que implican cambios en la interfaz de usuario. Esto incluye propiedades como <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>, que cambia el diseño de los elementos dentro de ese elemento como un elemento primario. Pero la mayoría de estas propiedades no están asignadas a posibles equivalentes de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], aunque dichos equivalentes existieran. Demasiadas de estas propiedades y de sus significados son tan específicos de la tecnología de representación que las asignaciones no resultan prácticas. Por lo tanto, establecer propiedades <xref:System.Windows.FrameworkElement.FlowDirection%2A> como <xref:System.Windows.Interop.HwndHost> on no tiene ningún efecto.  
  
- <xref:System.Windows.Interop.HwndHost>no se puede girar, escalar, sesgar o afectar de otra manera a una transformación.  
  
- <xref:System.Windows.Interop.HwndHost>no admite la <xref:System.Windows.UIElement.Opacity%2A> propiedad (combinación alfa). Si el contenido dentro <xref:System.Windows.Interop.HwndHost> de <xref:System.Drawing> realiza operaciones que incluyen información alfa, que no es una infracción, pero <xref:System.Windows.Interop.HwndHost> como un todo solo admite la opacidad = 1,0 (100%).  
  
- <xref:System.Windows.Interop.HwndHost>aparecerá encima de otros [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos de la misma ventana de nivel superior. Sin embargo, <xref:System.Windows.Controls.ToolTip> un <xref:System.Windows.Controls.ContextMenu> menú o generado es una ventana de nivel superior independiente y, por tanto, se <xref:System.Windows.Interop.HwndHost>comportará correctamente con.  
  
- <xref:System.Windows.Interop.HwndHost>no respeta la región de recorte de su <xref:System.Windows.UIElement>elemento primario. Esto puede ser un problema si intenta colocar una <xref:System.Windows.Interop.HwndHost> clase dentro de una región de desplazamiento o. <xref:System.Windows.Controls.Canvas>  
  
#### <a name="notable-differences-in-input-behavior"></a>Diferencias notables en el comportamiento de entrada  
  
- En general, mientras que los dispositivos de entrada están en <xref:System.Windows.Interop.HwndHost> el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ámbito de la región hospedada, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]los eventos de entrada van directamente a.  
  
- Mientras el mouse está sobre el <xref:System.Windows.Interop.HwndHost>, la aplicación no recibe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventos del mouse y el valor `false`de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedad <xref:System.Windows.UIElement.IsMouseOver%2A> será.  
  
- Mientras tiene <xref:System.Windows.Interop.HwndHost> el foco [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] deteclado<xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> , la aplicación no recibirá eventos de teclado y el valor de la propiedad será. `false`  
  
- Cuando el <xref:System.Windows.Interop.HwndHost> foco está dentro de y cambia a otro control dentro <xref:System.Windows.Interop.HwndHost>de, la aplicación no recibirá [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] los <xref:System.Windows.UIElement.GotFocus> eventos <xref:System.Windows.UIElement.LostFocus>o.  
  
- Las propiedades y los eventos del lápiz relacionados son análogos y no informan de la <xref:System.Windows.Interop.HwndHost>información mientras el lápiz está por encima.  
  
<a name="tabbing_mnemonics_accelerators"></a>   
## <a name="tabbing-mnemonics-and-accelerators"></a>Tabulación, teclas de acceso y aceleradores  
 Las <xref:System.Windows.Interop.IKeyboardInputSink> interfaces <xref:System.Windows.Interop.IKeyboardInputSite> y permiten crear una experiencia de teclado sin problemas para aplicaciones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mixtas y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] :  
  
- Tabulación entre componentes de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
- Las teclas de acceso y los aceleradores que funcionan tanto si el foco está dentro de un componente de Win32 como si está dentro de un componente de WPF.  
  
 Las <xref:System.Windows.Interop.HwndHost> clases <xref:System.Windows.Interop.HwndSource> y proporcionan implementaciones de <xref:System.Windows.Interop.IKeyboardInputSink>, pero es posible que no controlen todos los mensajes de entrada que desea para escenarios más avanzados. Invalide los métodos adecuados para obtener el comportamiento de teclado que quiera.  
  
 Las interfaces solo proporcionan compatibilidad para lo que ocurre en la transición entre las zonas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Dentro de la zona de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], el comportamiento de la tabulación está totalmente controlado por la lógica implementada de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] de la tabulación, en el caso de que la haya.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.HwndHost>
- <xref:System.Windows.Interop.HwndSource>
- <xref:System.Windows.Interop>
- [Tutorial: Hospedar un control de Win32 en WPF](walkthrough-hosting-a-win32-control-in-wpf.md)
- [Tutorial: Hospedar contenido de WPF en Win32](walkthrough-hosting-wpf-content-in-win32.md)
