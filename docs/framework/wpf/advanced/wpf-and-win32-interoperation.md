---
title: Interoperabilidad de WPF y Win32
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: 7b7c3ed8f9833094ce1e836c11f84132ae84def2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735218"
---
# <a name="wpf-and-win32-interoperation"></a>Interoperabilidad de WPF y Win32

En este tema se proporciona información general sobre cómo interoperar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y código Win32. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, si tiene una inversión sustancial en código Win32, podría ser más eficaz reutilizar parte de ese código.

<a name="basics"></a>

## <a name="wpf-and-win32-interoperation-basics"></a>Conceptos básicos de interoperación de WPF y Win32

Hay dos técnicas básicas para la interoperación entre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y el código Win32.

- Hospede [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido en una ventana de Win32. Con esta técnica, puede usar las funciones de gráficos avanzadas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro del marco de una aplicación y una ventana estándar de Win32.

- Hospede una ventana de Win32 en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido. Con esta técnica, puede usar un control Win32 personalizado existente en el contexto de otro contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y pasar datos a través de los límites.

Todas estas técnicas se presentan conceptualmente en este tema. Para obtener más información orientada a código sobre cómo hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en Win32, vea [Tutorial: hospedar contenido de WPF en Win32](walkthrough-hosting-wpf-content-in-win32.md). Para obtener más información orientada a código sobre el hospedaje de Win32 en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Tutorial: hospedar un control de Win32 en WPF](walkthrough-hosting-a-win32-control-in-wpf.md).

<a name="projects"></a>

## <a name="wpf-interoperation-projects"></a>Proyectos de interoperación de WPF

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API son código administrado, pero la mayoría de los programas de Win32 existentes se escriben en no administrados C++.  No se puede llamar a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API desde un auténtico programa no administrado. Sin embargo, si usa la opción `/clr` con el compilador de Microsoft Visual C++ , puede crear un programa mixto administrado-no administrado en el que pueda combinar sin problemas llamadas API administradas y no administradas.

Una complicación de nivel de proyecto es que no se pueden compilar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivos en un C++ proyecto.  Existen varias técnicas de división de proyectos para compensarlo.

- Cree un C# archivo DLL que contenga todas las páginas de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como un ensamblado compilado y C++ , después, haga que el archivo ejecutable incluya ese archivo dll como referencia.

- Cree un C# archivo ejecutable para el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y haga referencia a un C++ archivo DLL que contenga el contenido de Win32.

- Utilice <xref:System.Windows.Markup.XamlReader.Load%2A> para cargar cualquier [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en tiempo de ejecución, en lugar de compilar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

- No utilice [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en absoluto y escriba todo el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en el código, compilando el árbol de elementos a partir de <xref:System.Windows.Application>.

Use el método que se adapte mejor a sus necesidades.

> [!NOTE]
> Si no ha usado C++/CLI antes, es posible que observe algunas palabras clave "nuevas", como `gcnew` y `nullptr` en los ejemplos de código de interoperación. Estas palabras clave reemplazan la sintaxis de doble subrayado anterior (`__gc`) y proporcionan una sintaxis más natural para el C++código administrado en.  Para obtener más información sobre C++las características administradas de/CLI, vea [extensiones de componentes para plataformas en tiempo de ejecución](/cpp/windows/component-extensions-for-runtime-platforms).

<a name="hwnds"></a>

## <a name="how-wpf-uses-hwnds"></a>Cómo WPF usa los HWND

Para aprovechar al máximo la "interoperación de HWND" de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], debe comprender cómo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa los HWND. Para cualquier HWND, no se puede mezclar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] representación con representación de DirectX o representación de GDI/GDI+. Esto tiene varias implicaciones. En primer lugar, para poder mezclar estos modelos de representación, debe crear una solución de interoperación y usar segmentos de interoperación designados para cada modelo de representación que quiera usar. Además, el comportamiento de representación crea una restricción de "espacio aéreo" de lo que puede llevar a cabo su solución de interoperación. El concepto "espacio aéreo" se describe más detalladamente en el tema [Información general sobre áreas de la tecnología](technology-regions-overview.md).

Todos los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de la pantalla están respaldados en última instancia por un HWND. Cuando se crea un <xref:System.Windows.Window>de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea un HWND de nivel superior y utiliza un <xref:System.Windows.Interop.HwndSource> para colocar el <xref:System.Windows.Window> y su contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro del HWND.  El resto del contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de la aplicación comparte ese HWND en concreto. Una excepción son los menús, los menús desplegables de cuadro combinado y otros elementos emergentes. Estos elementos crean su propia ventana de nivel superior, razón por la cual un menú de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede exceder el borde del HWND de ventana que lo contiene. Cuando se usa <xref:System.Windows.Interop.HwndHost> para colocar un HWND dentro de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] informa a Win32 de cómo colocar el nuevo HWND secundario en relación con la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND.

Un concepto relacionado con HWND es la transparencia dentro de cada HWND y entre cada uno de ellos. Esto también se describe en el tema [Información general sobre áreas de la tecnología](technology-regions-overview.md).

<a name="hosting_a_wpf_page"></a>

## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>Hospedar contenido de WPF en una ventana de Microsoft Win32

La clave para hospedar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de Win32 es la clase <xref:System.Windows.Interop.HwndSource>. Esta clase ajusta el contenido de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una ventana de Win32, de modo que el contenido de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pueda incorporarse al [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] como una ventana secundaria. El siguiente enfoque combina el Win32 y el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una sola aplicación.

1. Implemente su contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (el elemento raíz del contenido) como una clase administrada. Normalmente, la clase hereda de una de las clases que pueden contener varios elementos secundarios o usarse como un elemento raíz, como <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.Page>. En los siguientes pasos se hace referencia a esta clase como "clase de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]", mientras que las instancias de la clase se denominan "objetos de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]".

2. Implementar una aplicación de Windows C++con/CLI. Si está empezando con una C++ aplicación no administrada existente, normalmente puede habilitarla para llamar a código administrado cambiando la configuración del proyecto para incluir la marca de compilador `/clr` (el ámbito completo de lo que podría ser necesario para admitir la compilación de `/clr` no se describe en este tema).

3. Establezca el modelo de subprocesos en Contenedor uniproceso (STA). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa este modelo de subprocesamiento.

4. Controle la notificación WM_CREATE en el procedimiento de ventana.

5. En el controlador (o en una función a la que llama el controlador), haga lo siguiente:

    1. Cree un nuevo objeto de <xref:System.Windows.Interop.HwndSource> con el HWND de la ventana primaria como su parámetro `parent`.

    2. Cree una instancia de su clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

    3. Asigne una referencia al objeto de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la propiedad <xref:System.Windows.Interop.HwndSource.RootVisual%2A> del objeto <xref:System.Windows.Interop.HwndSource>.

    4. El objeto <xref:System.Windows.Interop.HwndSource> <xref:System.Windows.Interop.HwndSource.Handle%2A> propiedad contiene el identificador de ventana (HWND). Para obtener un HWND que se pueda usar en la parte de la aplicación no administrada, convierta `Handle.ToPointer()` en un HWND.

6. Implemente una clase administrada que contenga un campo estático para contener una referencia al objeto de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Esta clase permite obtener una referencia al objeto de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] desde el código de Win32, pero lo más importante es evitar que el <xref:System.Windows.Interop.HwndSource> se recopile involuntariamente.

7. Adjunte un identificador a uno o varios de los eventos del objeto de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para recibir notificaciones del objeto de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

8. Comuníquese con el objeto de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante la referencia que almacenó en el campo estático para establecer propiedades, llamar a métodos, etc.

> [!NOTE]
> Puede hacer una parte o toda la definición de clase de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para el primer paso en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usando la clase parcial predeterminada de la clase de contenido. Para ello, debe crear un ensamblado independiente y hacer referencia a este. Aunque normalmente se incluye un objeto <xref:System.Windows.Application> como parte de la compilación de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en un ensamblado, no se termina usando ese <xref:System.Windows.Application> como parte de la interoperación, solo se usan una o varias de las clases raíz para los archivos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] a los que hace referencia la aplicación y se hace referencia a sus clases parciales. El resto del procedimiento es muy similar al descrito anteriormente.
>
> Todos estos pasos se describen mediante código en el tema [Tutorial: Hospedar contenido de WPF en Win32](walkthrough-hosting-wpf-content-in-win32.md).

<a name="hosting_an_hwnd"></a>

## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>Hospedar una ventana de Microsoft Win32 en WPF

La clave para hospedar una ventana de Win32 dentro de otro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido es la clase <xref:System.Windows.Interop.HwndHost>. Esta clase encapsula la ventana en un elemento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que se puede agregar a un árbol de elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Interop.HwndHost> también admite las API que le permiten realizar tareas como procesar mensajes para la ventana hospedada. El procedimiento básico es el siguiente:

1. Cree un árbol de elementos para una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (se puede efectuar mediante código o mediante marcado). Busque un punto adecuado y permisible en el árbol de elementos donde la implementación de <xref:System.Windows.Interop.HwndHost> se puede agregar como elemento secundario. En el resto de estos pasos, este elemento se conoce como el "elemento de reserva".

2. Derive de <xref:System.Windows.Interop.HwndHost> para crear un objeto que contenga el contenido de Win32.

3. En esa clase de host, invalide el método <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>. Devuelva el HWND de la ventana hospedada. Tal vez quiera encapsular los controles reales como una ventana secundaria de la ventana devuelta; el encapsulamiento de los controles en una ventana host es una manera sencilla que tiene el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para recibir notificaciones de los controles. Esta técnica ayuda a corregir algunos problemas de Win32 relacionados con el control de mensajes en el límite de control hospedado.

4. Invalide los métodos de <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> y <xref:System.Windows.Interop.HwndHost.WndProc%2A>. Aquí, la intención es procesar una limpieza y quitar las referencias al contenido hospedado, sobre todo si creó referencias a objetos no administrados.

5. En el archivo de código subyacente, cree una instancia del control que hospeda la clase y conviértalo en un elemento secundario del elemento de reserva. Normalmente se usaría un controlador de eventos como <xref:System.Windows.FrameworkElement.Loaded>, o bien se utilizaría el constructor de clase parcial. pero también podría agregar el contenido de interoperación mediante un comportamiento en tiempo de ejecución.

6. Procese los mensajes de la ventana seleccionada, como las notificaciones de control. Existen dos enfoques. Ambos proporcionan el mismo acceso a la secuencia de mensajes, por lo que su elección es más bien una cuestión de comodidad a la hora de programar.

    - Implemente el procesamiento de mensajes para todos los mensajes (no solo los mensajes de cierre) en la invalidación del método de <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost.WndProc%2A>.

    - Haga que el elemento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de hospedaje procese los mensajes controlando el evento de <xref:System.Windows.Interop.HwndHost.MessageHook>. Este evento se genera para cada mensaje que se envía al procedimiento de ventana principal de la ventana hospedada.

    - No se pueden procesar mensajes de ventanas que no estén en proceso mediante <xref:System.Windows.Interop.HwndHost.WndProc%2A>.

7. Comuníquese con la ventana hospedada usando una invocación de plataforma para llamar a la función `SendMessage` no administrada.

Si sigue estos pasos, creará una aplicación que funcionará con la entrada del ratón. Puede Agregar compatibilidad con la tabulación para la ventana hospedada implementando la interfaz de <xref:System.Windows.Interop.IKeyboardInputSink>.

Todos estos pasos se describen mediante código en el tema [Tutorial: Hospedar un control de Win32 en WPF](walkthrough-hosting-a-win32-control-in-wpf.md).

### <a name="hwnds-inside-wpf"></a>HWND dentro de WPF

Puede pensar en <xref:System.Windows.Interop.HwndHost> como un control especial. (Técnicamente, <xref:System.Windows.Interop.HwndHost> es una clase derivada <xref:System.Windows.FrameworkElement>, no una clase derivada <xref:System.Windows.Controls.Control>, pero se puede considerar un control para la interoperación). <xref:System.Windows.Interop.HwndHost> abstrae la naturaleza Win32 subyacente del contenido hospedado de forma que el resto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] considera que el contenido hospedado es otro objeto similar a un control, que debe representar y procesar la entrada. <xref:System.Windows.Interop.HwndHost> generalmente se comporta como cualquier otro <xref:System.Windows.FrameworkElement>de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], aunque hay algunas diferencias importantes en torno a la salida (dibujo y gráficos) y a la entrada (mouse y teclado) en función de las limitaciones de lo que el HWND subyacente puede admitir.

#### <a name="notable-differences-in-output-behavior"></a>Diferencias notables en el comportamiento de salida

- <xref:System.Windows.FrameworkElement>, que es la clase base <xref:System.Windows.Interop.HwndHost>, tiene algunas propiedades que implican cambios en la interfaz de usuario. Esto incluye propiedades como <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>, que cambia el diseño de los elementos dentro de ese elemento como un elemento primario. Sin embargo, la mayoría de estas propiedades no se asignan a los equivalentes de Win32 posibles, aunque puedan existir tales equivalentes. Demasiadas de estas propiedades y de sus significados son tan específicos de la tecnología de representación que las asignaciones no resultan prácticas. Por lo tanto, establecer propiedades como <xref:System.Windows.FrameworkElement.FlowDirection%2A> en <xref:System.Windows.Interop.HwndHost> no tiene ningún efecto.

- <xref:System.Windows.Interop.HwndHost> no se pueden girar, escalar, sesgar ni afectar de alguna manera a una transformación.

- <xref:System.Windows.Interop.HwndHost> no admite la propiedad <xref:System.Windows.UIElement.Opacity%2A> (combinación alfa). Si el contenido de la <xref:System.Windows.Interop.HwndHost> realiza <xref:System.Drawing> operaciones que incluyen información alfa, no es una infracción, pero el <xref:System.Windows.Interop.HwndHost> como un todo solo admite la opacidad = 1,0 (100%).

- <xref:System.Windows.Interop.HwndHost> aparecerán encima de otros elementos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en la misma ventana de nivel superior. Sin embargo, un <xref:System.Windows.Controls.ToolTip> o <xref:System.Windows.Controls.ContextMenu> menú generado es una ventana de nivel superior independiente y, por tanto, se comportará correctamente con <xref:System.Windows.Interop.HwndHost>.

- <xref:System.Windows.Interop.HwndHost> no respeta la región de recorte de su <xref:System.Windows.UIElement>principal. Esto puede ser un problema si intenta colocar una clase <xref:System.Windows.Interop.HwndHost> dentro de una región de desplazamiento o <xref:System.Windows.Controls.Canvas>.

#### <a name="notable-differences-in-input-behavior"></a>Diferencias notables en el comportamiento de entrada

- En general, mientras que los dispositivos de entrada se encuentran dentro del ámbito de la <xref:System.Windows.Interop.HwndHost> región de Win32 hospedada, los eventos de entrada van directamente a Win32.

- Mientras el mouse está sobre el <xref:System.Windows.Interop.HwndHost>, la aplicación no recibe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventos del mouse y se `false`el valor de la propiedad [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.IsMouseOver%2A>.

- Mientras el <xref:System.Windows.Interop.HwndHost> tiene el foco de teclado, la aplicación no recibirá [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventos de teclado y el valor de la propiedad [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> se `false`.

- Cuando el foco está en el <xref:System.Windows.Interop.HwndHost> y cambia a otro control dentro de la <xref:System.Windows.Interop.HwndHost>, la aplicación no recibirá los eventos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.GotFocus> o <xref:System.Windows.UIElement.LostFocus>.

- Las propiedades y los eventos del lápiz relacionados son análogos y no informan de la información mientras el lápiz se encuentra sobre <xref:System.Windows.Interop.HwndHost>.

<a name="tabbing_mnemonics_accelerators"></a>

## <a name="tabbing-mnemonics-and-accelerators"></a>Tabulación, teclas de acceso y aceleradores

Las interfaces <xref:System.Windows.Interop.IKeyboardInputSink> y <xref:System.Windows.Interop.IKeyboardInputSite> permiten crear una experiencia de teclado sin problemas para las aplicaciones mixtas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y Win32:

- Tabulación entre componentes de Win32 y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]

- Las teclas de acceso y los aceleradores que funcionan tanto si el foco está dentro de un componente de Win32 como si está dentro de un componente de WPF.

Las clases <xref:System.Windows.Interop.HwndHost> y <xref:System.Windows.Interop.HwndSource> proporcionan implementaciones de <xref:System.Windows.Interop.IKeyboardInputSink>, pero puede que no controlen todos los mensajes de entrada que desee para escenarios más avanzados. Invalide los métodos adecuados para obtener el comportamiento de teclado que quiera.

Las interfaces solo proporcionan compatibilidad con lo que ocurre en la transición entre las regiones [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y Win32. Dentro de la región de Win32, el comportamiento de tabulación se controla por completo mediante la lógica implementada por Win32 para la tabulación, si existe.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Interop.HwndHost>
- <xref:System.Windows.Interop.HwndSource>
- <xref:System.Windows.Interop>
- [Tutorial: Hospedar un control de Win32 en WPF](walkthrough-hosting-a-win32-control-in-wpf.md)
- [Tutorial: Hospedar contenido de WPF en Win32](walkthrough-hosting-wpf-content-in-win32.md)
