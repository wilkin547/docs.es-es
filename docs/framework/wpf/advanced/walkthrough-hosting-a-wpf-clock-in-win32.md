---
title: 'Tutorial: hospedar un reloj de WPF en Win32'
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 1fdc0c9ccf1464d7519a4c5935520de1206ca9bb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794158"
---
# <a name="walkthrough-host-a-wpf-clock-in-win32"></a>Tutorial: hospedar un reloj de WPF en Win32

Para colocar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro de las aplicaciones de Win32, use <xref:System.Windows.Interop.HwndSource>, que proporciona el HWND que incluye el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. En primer lugar, cree el <xref:System.Windows.Interop.HwndSource>, proporcionándole parámetros similares a CreateWindow. A continuación, indique al <xref:System.Windows.Interop.HwndSource> sobre el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que desea incluir en él. Por último, se obtiene el HWND de la <xref:System.Windows.Interop.HwndSource>. En este tutorial se muestra cómo crear una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mixta dentro de la aplicación Win32 que vuelve a implementar el cuadro de diálogo **propiedades de fecha y hora** del sistema operativo.

## <a name="prerequisites"></a>Requisitos previos

Consulte [interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md).

## <a name="how-to-use-this-tutorial"></a>Cómo usar este tutorial

Este tutorial se centra en los pasos importantes para generar una aplicación de interoperabilidad. El tutorial está respaldado por un ejemplo de [ejemplo de interoperación de reloj de Win32](https://go.microsoft.com/fwlink/?LinkID=160051), pero ese ejemplo refleja el producto final. En este tutorial se documentan los pasos como si se empezara con un proyecto de Win32 existente, quizás un proyecto ya existente, y se agregaba un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedado a la aplicación. Puede comparar el producto final con el [ejemplo de interoperación de reloj de Win32](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Tutorial de Windows Presentation Framework dentro de Win32 (HwndSource)

En el siguiente gráfico se muestra el producto final previsto de este tutorial:

![Captura de pantalla que muestra el cuadro de diálogo Propiedades de fecha y hora.](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

Puede volver a crear este cuadro de diálogo creando C++ un proyecto de Win32 en Visual Studio y usando el editor de cuadros de diálogo para crear lo siguiente:

![Cuadro de diálogo Propiedades de fecha y hora de creación de datos](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

(No es necesario usar Visual Studio para usar <xref:System.Windows.Interop.HwndSource>y no es necesario usar C++ para escribir programas de Win32, pero es una manera bastante habitual de hacerlo y se presta bien a una explicación del tutorial de escalonado).

Debe realizar cinco subpasos determinados para colocar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj en el cuadro de diálogo:

1. Habilite el proyecto de Win32 para llamar a código administrado ( **/CLR**) cambiando la configuración del proyecto en Visual Studio.

2. Cree un <xref:System.Windows.Controls.Page> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]en un archivo DLL independiente.

3. Coloque el <xref:System.Windows.Controls.Page> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]dentro de un <xref:System.Windows.Interop.HwndSource>.

4. Obtenga un HWND para ese <xref:System.Windows.Controls.Page> mediante la propiedad <xref:System.Windows.Interop.HwndSource.Handle%2A>.

5. Usar Win32 para decidir dónde colocar el HWND en la aplicación Win32 más grande

## <a name="clr"></a>/clr

El primer paso consiste en convertir este proyecto de Win32 no administrado en uno que pueda llamar a código administrado. Use la opción del compilador/CLR, que se vinculará a los archivos dll necesarios que desee usar, y ajuste el método Main para su uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Para habilitar el uso de código administrado dentro del C++ proyecto: haga clic con el botón derecho en el proyecto win32clock y seleccione **propiedades**. En la página de propiedades **General** (valor predeterminado), cambie la compatibilidad con Common Language Runtime a `/clr`.

A continuación, agregue referencias a los archivos dll necesarios para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore. dll, PresentationFramework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll y UIAutomationTypes. dll. (si sigue las instrucciones, el sistema operativo se instalará en la unidad C:).

1. Haga clic con el botón secundario en el proyecto win32clock y seleccione **referencias...** , y dentro de ese cuadro de diálogo:

2. Haga clic con el botón derecho en proyecto win32clock y seleccione **referencias.** ...

3. Haga clic en **Agregar nueva referencia**, en la pestaña examinar, escriba C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll y haga clic en Aceptar.

4. Repita el proceso para PresentationFramework.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.

5. Repita el proceso para WindowsBase.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.

6. Repita el proceso para UIAutomationTypes.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.

7. Repita el proceso para UIAutomationProvider.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.

8. Haga clic en **Agregar nueva referencia**, seleccione System. dll y haga clic en **Aceptar**.

9. Haga clic en **Aceptar** para salir de las páginas de propiedades de win32clock para agregar referencias.

 Por último, agregue el `STAThreadAttribute` al método `_tWinMain` para su uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

Este atributo indica al Common Language Runtime (CLR) que cuando inicializa el modelo de objetos componentes (COM), debe usar un modelo de apartamento de un solo subproceso (STA), que es necesario para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (y Windows Forms).

## <a name="create-a-windows-presentation-framework-page"></a>Cree una página de Windows Presentation Framework

A continuación, cree un archivo DLL que defina una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>. A menudo es más fácil crear el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> como una aplicación independiente, y escribir y depurar la parte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de esa forma. Una vez hecho, ese proyecto se puede convertir en un archivo DLL; para ello, haga clic con el botón secundario en el proyecto, haga clic en **propiedades**, vaya a la aplicación y cambie tipo de salida a biblioteca de clases de Windows.

El proyecto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll se puede combinar con el proyecto de Win32 (una solución que contiene dos proyectos): haga clic con el botón derecho en la solución, seleccione **proyecto de Add\Existing**.

Para usar ese [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll del proyecto de Win32, debe agregar una referencia:

1. Haga clic con el botón derecho en proyecto win32clock y seleccione **referencias.** ...

2. Haga clic en **Agregar nueva referencia**.

3. Haga clic en la pestaña **proyectos** . Seleccione WPFClock y haga clic en Aceptar.

4. Haga clic en **Aceptar** para salir de las páginas de propiedades de win32clock para agregar referencias.

## <a name="hwndsource"></a>HwndSource

A continuación, use <xref:System.Windows.Interop.HwndSource> para que el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> sea similar a un HWND. Agregue este bloque de código a un archivo de C++:

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

 A continuación, se define una función que crea el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido, coloca un <xref:System.Windows.Interop.HwndSource> alrededor y devuelve el HWND:

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

En primer lugar, cree una <xref:System.Windows.Interop.HwndSource>, cuyos parámetros sean similares a los de CreateWindow:

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

A continuación, cree la clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llamando a su constructor:

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

A continuación, conecte la página al <xref:System.Windows.Interop.HwndSource>:

```cpp
source->RootVisual = page;
```

 Y, en la línea final, devuelva el HWND para el <xref:System.Windows.Interop.HwndSource>:

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a>Colocar el HWND

Ahora que tiene un HWND que contiene el reloj de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], debe colocar ese HWND en el cuadro de diálogo de Win32. Si sabía dónde colocar el HWND, simplemente pasaría ese tamaño y ubicación a la función de `GetHwnd` que definió anteriormente. pero ha usado un archivo de recursos para definir el cuadro de diálogo, por lo que no sabe con certeza dónde están colocados los HWND. Puede usar el editor de cuadros de diálogo de Visual Studio para colocar un control estático de Win32 donde quiera que el reloj ("Inserte el reloj aquí") y usarlo para colocar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj.

Cuando se controla WM_INITDIALOG, se usa `GetDlgItem` para recuperar el HWND para el marcador de posición STATIC:

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

A continuación, calcula el tamaño y la posición del marcador de posición estático, de modo que puede colocar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj en ese lugar:

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

Y crean el HWND de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj en esa ubicación:

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

Para que el tutorial le resulte interesante y para generar un reloj real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], deberá crear un control de reloj de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en este momento. Puede hacerlo principalmente en el marcado, con tan solo unos pocos controladores de eventos en el código subyacente. Dado que este tutorial trata sobre la interoperación y no sobre el diseño del control, el código completo para el reloj de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se proporciona aquí como un bloque de código, sin instrucciones discretas para crearlo o lo que significa cada parte. No dude en experimentar con este código para cambiar el aspecto o la funcionalidad del control.

Aquí está el marcado:

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

Y aquí está el código subyacente adjunto:

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

El resultado final tiene el siguiente aspecto:

![Cuadro de diálogo Propiedades de fecha y hora de resultado final](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

Para comparar el resultado final con el código que generó esta captura de pantalla, vea [ejemplo de interoperación de reloj de Win32](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.HwndSource>
- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
- [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051) (Ejemplo de interoperación de un reloj de Win32)
