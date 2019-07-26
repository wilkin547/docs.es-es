---
title: 'Tutorial: Hospedar un reloj de WPF en Win32'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 27e1a2e88beeacf8c2cd98f61b11542ee2341e8f
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433977"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a>Tutorial: Hospedar un reloj de WPF en Win32

Para colocar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] de las aplicaciones <xref:System.Windows.Interop.HwndSource>, use, que proporciona el HWND que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye el contenido. En primer lugar, <xref:System.Windows.Interop.HwndSource>cree el, y asígnele parámetros similares a CreateWindow. A continuación, se <xref:System.Windows.Interop.HwndSource> indica a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sobre el contenido que se desea incluir en él. Por último, se obtiene el HWND de la <xref:System.Windows.Interop.HwndSource>. En este tutorial se muestra cómo crear una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] de una mezcla que vuelva a implementar el cuadro de diálogo **propiedades de fecha y hora** del sistema operativo.

## <a name="prerequisites"></a>Requisitos previos

Consulte [interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md).

## <a name="how-to-use-this-tutorial"></a>Cómo usar este tutorial

Este tutorial se centra en los pasos importantes para generar una aplicación de interoperabilidad. El tutorial está respaldado por un ejemplo de [ejemplo](https://go.microsoft.com/fwlink/?LinkID=160051)de interoperación de reloj de Win32, pero ese ejemplo refleja el producto final. En este tutorial se documentan los pasos como si se empezara [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] con un proyecto existente, quizás un proyecto ya existente, y se agregaba un hospedado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la aplicación. Puede comparar el producto final con el [ejemplo](https://go.microsoft.com/fwlink/?LinkID=160051)de interoperación de reloj de Win32.

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Tutorial de Windows Presentation Framework dentro de Win32 (HwndSource)

En el siguiente gráfico se muestra el producto final previsto de este tutorial:

![Captura de pantalla que muestra el cuadro de diálogo Propiedades de fecha y hora.](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

Puede volver a crear este cuadro de diálogo creando C++ un proyecto de Win32 en Visual Studio y usando el editor de cuadros de diálogo para crear lo siguiente:

![Cuadro de diálogo Propiedades de fecha y hora de creación de datos](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

(No [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] es necesario usar para usar <xref:System.Windows.Interop.HwndSource>y no es necesario usar C++ para escribir [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programas, pero esta es una manera bastante habitual de hacerlo y se presta bien a una explicación del tutorial de escalonado).

Debe realizar cinco subpasos determinados para colocar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj en el cuadro de diálogo:

1. Habilite el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proyecto para que llame a código administrado ( **/CLR**) cambiando la configuración [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]del proyecto en.

2. Cree un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> en un archivo dll independiente.

3. Colóquelo dentro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> de.<xref:System.Windows.Interop.HwndSource>

4. Obtenga un HWND para que <xref:System.Windows.Controls.Page> use la <xref:System.Windows.Interop.HwndSource.Handle%2A> propiedad.

5. Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para decidir dónde colocar el HWND dentro de la aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] más grande

## <a name="clr"></a>/clr

El primer paso consiste en convertir este [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proyecto no administrado en uno que pueda llamar a código administrado. Utilice la opción del compilador/CLR, que se vinculará a los archivos dll necesarios que desee usar, y ajuste el método Main [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]para su uso con.

Para habilitar el uso de código administrado dentro del C++ proyecto: Haga clic con el botón derecho en el proyecto win32clock y seleccione **propiedades**. En la página de propiedades **General** (valor predeterminado), cambie compatibilidad con Common Language `/clr`Runtime a.

A continuación, agregue referencias a los archivos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]dll necesarios para: PresentationCore. dll, PresentationFramework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll y UIAutomationTypes. dll. (si sigue las instrucciones, el sistema operativo se instalará en la unidad C:).

1. Haga clic con el botón secundario en el proyecto win32clock y seleccione **referencias...** , y dentro de ese cuadro de diálogo:

2. Haga clic con el botón derecho en proyecto win32clock y seleccione **referencias.** ...

3. Haga clic en **Agregar nueva referencia**, en la pestaña examinar, escriba C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll y haga clic en Aceptar.

4. Repita el procedimiento para PresentationFramework. dll: C:\Archivos de Programa\reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.

5. Repita el procedimiento para WindowsBase. dll: C:\Archivos de Programa\reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.

6. Repita el procedimiento para UIAutomationTypes. dll: C:\Archivos de Programa\reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.

7. Repita el procedimiento para UIAutomationProvider. dll: C:\Archivos de Programa\reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.

8. Haga clic en **Agregar nueva referencia**, seleccione System. dll y haga clic en **Aceptar**.

9. Haga clic en **Aceptar** para salir de las páginas de propiedades de win32clock para agregar referencias.

 Por último, agregue `STAThreadAttribute` el `_tWinMain` al método para su uso [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]con:

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

Este atributo indica al Common Language Runtime (CLR) que cuando inicializa el modelo de objetos componentes (com), debe usar un modelo de apartamento de un solo subproceso (STA), que es [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] necesario para [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)](y).

## <a name="create-a-windows-presentation-framework-page"></a>Cree una página de Windows Presentation Framework

A continuación, se crea un archivo DLL que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]define un. <xref:System.Windows.Controls.Page> A menudo es más fácil crear el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> como una aplicación independiente y escribir y depurar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la parte de ese modo. Una vez hecho, ese proyecto se puede convertir en un archivo DLL; para ello, haga clic con el botón secundario en el proyecto, haga clic en **propiedades**, vaya a la aplicación y cambie tipo de salida a biblioteca de clases de Windows.

Después [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , el proyecto dll se puede combinar con [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] el proyecto (una solución que contiene dos proyectos): haga clic con el botón derecho en la solución, seleccione **proyecto de Add\Existing**.

Para usar ese [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] archivo dll desde [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] el proyecto, debe agregar una referencia:

1. Haga clic con el botón derecho en proyecto win32clock y seleccione **referencias.** ...

2. Haga clic en **Agregar nueva referencia**.

3. Haga clic en la pestaña **Proyectos**. Seleccione WPFClock y haga clic en Aceptar.

4. Haga clic en **Aceptar** para salir de las páginas de propiedades de win32clock para agregar referencias.

## <a name="hwndsource"></a>HwndSource

A continuación, use <xref:System.Windows.Interop.HwndSource> para que el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> aspecto sea un HWND. Agregue este bloque de código a un archivo de C++:

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;

    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
        HwndSource^ source = gcnew HwndSource(
            0, // class style
            WS_VISIBLE | WS_CHILD, // style
            0, // exstyle
            x, y, width, height,
            "hi", // NAME
            IntPtr(parent)        // parent window
            );

        UIElement^ page = gcnew WPFClock::Clock();
        source->RootVisual = page;
        return (HWND) source->Handle.ToPointer();
    }
}
}
```

 Se trata de un fragmento de código extenso que podría incluir alguna explicación. La primera parte consta de varias cláusulas para que no tenga que completar todas las llamadas:

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 A continuación, se define una función que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea el contenido, <xref:System.Windows.Interop.HwndSource> coloca una alrededor y devuelve el HWND:

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

Primero se crea un <xref:System.Windows.Interop.HwndSource>, cuyos parámetros son similares a los de CreateWindow:

```cpp
HwndSource^ source = gcnew HwndSource(
    0, // class style
    WS_VISIBLE | WS_CHILD, // style
    0, // exstyle
    x, y, width, height,
    "hi", // NAME
    IntPtr(parent) // parent window
);
```

A continuación, cree [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la clase de contenido llamando a su constructor:

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

A continuación, conecte la página a <xref:System.Windows.Interop.HwndSource>:

```cpp
source->RootVisual = page;
```

 Y en la línea final, devuelva el HWND para <xref:System.Windows.Interop.HwndSource>:

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a>Colocar el HWND

Ahora que tiene un HWND que contiene el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj, debe colocar ese HWND en el cuadro de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] diálogo. Si sabía dónde colocar el HWND, simplemente pasaría ese tamaño y ubicación a la `GetHwnd` función que definió anteriormente. pero ha usado un archivo de recursos para definir el cuadro de diálogo, por lo que no sabe con certeza dónde están colocados los HWND. Puede usar el [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] editor de cuadros de diálogo para [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] colocar un control estático en el que desea que el reloj ("Inserte el reloj aquí") y usarlo para colocar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el reloj.

Donde se controla WM_INITDIALOG, se usa `GetDlgItem` para recuperar el HWND para el marcador de posición Static:

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

A continuación, calcula el tamaño y la posición del marcador de posición estático, de modo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que puede colocar el reloj en ese lugar:

RECT rectángulo;

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

Luego, oculte el marcador de posición STATIC:

```cpp
ShowWindow(placeholder, SW_HIDE);
```

Y crean el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND del reloj en esa ubicación:

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

Para que el tutorial le resulte interesante y para generar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un reloj real, deberá crear un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control de reloj en este momento. Puede hacerlo principalmente en el marcado, con tan solo unos pocos controladores de eventos en el código subyacente. Dado que este tutorial trata sobre la interoperación y no sobre el diseño del control, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el código completo del reloj se proporciona aquí como un bloque de código, sin instrucciones discretas para crearlo o lo que significa cada parte. No dude en experimentar con este código para cambiar el aspecto o la funcionalidad del control.

Aquí está el marcado:

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

Y aquí está el código subyacente adjunto:

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

El resultado final tiene el siguiente aspecto:

![Cuadro de diálogo Propiedades de fecha y hora de resultado final](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

Para comparar el resultado final con el código que generó esta captura de pantalla, vea ejemplo de interoperación de [reloj de Win32](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.HwndSource>
- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
- [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051) (Ejemplo de interoperación de un reloj de Win32)
