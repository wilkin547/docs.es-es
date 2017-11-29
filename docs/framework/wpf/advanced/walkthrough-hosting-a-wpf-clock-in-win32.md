---
title: 'Tutorial: Hospedar un reloj de WPF en Win32'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55e5aa633e3d788ac8acaa09684c92b8608e7cfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a>Tutorial: Hospedar un reloj de WPF en Win32
Para colocar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] aplicaciones, utilizan <xref:System.Windows.Interop.HwndSource>, que proporciona el HWND que contiene su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido. Primero debe crear el <xref:System.Windows.Interop.HwndSource>, proporcionándole parámetros parecidos a los de CreateWindow.  Indicar el <xref:System.Windows.Interop.HwndSource> sobre el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido que desea en su interior.  Por último, obtendrá el HWND de la <xref:System.Windows.Interop.HwndSource>. Este tutorial muestra cómo crear un mixto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] aplicación que reimplements el sistema operativo **propiedades de fecha y hora** cuadro de diálogo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Vea [WPF y Win32 interoperación](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
## <a name="how-to-use-this-tutorial"></a>Cómo usar este tutorial  
 Este tutorial se centra en los pasos importantes para generar una aplicación de interoperabilidad. El tutorial está respaldado por un ejemplo, [ejemplo de interoperación de reloj de Win32](http://go.microsoft.com/fwlink/?LinkID=160051), pero este ejemplo es reflexivo del producto final. Este tutorial documenta los pasos como si usted comenzase con existente [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] su propio proyecto, quizás un proyecto existente y se agregase hospedados [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la aplicación. Puede comparar su producto final con [ejemplo de interoperación de reloj de Win32](http://go.microsoft.com/fwlink/?LinkID=160051).  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Tutorial de Windows Presentation Framework dentro de Win32 (HwndSource)  
 En el siguiente gráfico se muestra el producto final previsto de este tutorial:  
  
 ![Cuadro de diálogo Propiedades de fecha y hora](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")  
  
 Puede volver a este cuadro de diálogo Crear C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proyecto en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]y usa el editor de cuadro de diálogo para crear lo siguiente:  
  
 ![Cuadro de diálogo Propiedades de fecha y hora](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")  
  
 (No es necesario usar [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] usar <xref:System.Windows.Interop.HwndSource>, y no es necesario usar C++ para escribir [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programas, pero esto es una manera bastante habitual de hacerlo y se presta bien a una explicación del tutorial paso a paso).  
  
 Debe realizar cinco pasos secundarios concretos para colocar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj en el cuadro de diálogo:  
  
1.  Habilitar la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proyecto para llamar a código administrado (**/CLR**) cambiando la configuración del proyecto en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].  
  
2.  Crear un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> en un archivo DLL independiente.  
  
3.  Colocación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> dentro de un <xref:System.Windows.Interop.HwndSource>.  
  
4.  Obtener un HWND para que <xref:System.Windows.Controls.Page> mediante el <xref:System.Windows.Interop.HwndSource.Handle%2A> propiedad.  
  
5.  Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] decidir dónde colocar el HWND dentro de la mayor [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] aplicación  
  
## <a name="clr"></a>/clr  
 El primer paso consiste en desactivar esta administrados [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proyecto en el que se puede llamar a código administrado.  Utilice la opción del compilador/CLR, que se vinculará a las DLL necesarias que desea usar y ajustar el método Main para su uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Para habilitar el uso de código administrado dentro del proyecto de C++: haga doble clic en el proyecto win32clock y seleccione **propiedades**.  En el **General** cambiar de página de propiedades (valor predeterminado), compatibilidad con Common Language Runtime para `/clr`.  
  
 A continuación, agregue referencias a archivos DLL necesarios para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll y UIAutomationTypes.dll. (si sigue las instrucciones, el sistema operativo se instalará en la unidad C:).  
  
1.  Haga clic en proyecto win32clock y seleccione **referencias...** y dentro de ese cuadro de diálogo:  
  
2.  Haga clic en proyecto win32clock y seleccione **referencias...** .  
  
3.  Haga clic en **agregar nueva referencia**, haga clic en la ficha Examinar, escriba C:\Program programa\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll y haga clic en Aceptar.  
  
4.  Repita el proceso para PresentationFramework.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.  
  
5.  Repita el proceso para WindowsBase.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.  
  
6.  Repita el proceso para UIAutomationTypes.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.  
  
7.  Repita el proceso para UIAutomationProvider.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.  
  
8.  Haga clic en **agregar nueva referencia**, seleccione System.dll y haga clic en **Aceptar**.  
  
9. Haga clic en **Aceptar** para salir de las páginas de propiedades de win32clock para agregar referencias.  
  
 Por último, agregue el `STAThreadAttribute` a la `_tWinMain` método para su uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 Este atributo indica la [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] que cuando inicializa [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], debería utilizar un modelo de contenedor uniproceso (STA), que es necesario para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).  
  
## <a name="create-a-windows-presentation-framework-page"></a>Cree una página de Windows Presentation Framework  
 A continuación, cree un archivo DLL que define una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>. A menudo resulta más fácil crear el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> como una aplicación independiente y escribir y depurar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] parte de este modo.  Una vez hecho, ese proyecto se puede convertir en un archivo DLL haciendo clic en el proyecto, haga clic en **propiedades**, vaya a la aplicación y cambiar el tipo de salida a la biblioteca de clases de Windows.  
  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proyecto dll, a continuación, se puede combinar con la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proyecto (una solución que contiene dos proyectos), haga doble clic en la solución, seleccione **seguidamente**.  
  
 Usar este [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll desde el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proyecto, debe agregar una referencia:  
  
1.  Haga clic en proyecto win32clock y seleccione **referencias...** .  
  
2.  Haga clic en **agregar nueva referencia**.  
  
3.  Haga clic en la pestaña **Proyectos**.  Seleccione WPFClock y haga clic en Aceptar.  
  
4.  Haga clic en **Aceptar** para salir de las páginas de propiedades de win32clock para agregar referencias.  
  
## <a name="hwndsource"></a>HwndSource  
 A continuación, use <xref:System.Windows.Interop.HwndSource> para realizar la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> el aspecto de un HWND.  Agregue este bloque de código a un archivo de C++:  
  
```  
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
  
 Se trata de un fragmento de código extenso que podría incluir alguna explicación.  La primera parte consta de varias cláusulas para que no tenga que completar todas las llamadas:  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 A continuación, definir una función que crea el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de contenido, coloca una <xref:System.Windows.Interop.HwndSource> alrededor de la base de datos y devuelve el HWND:  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 Primero debe crear un <xref:System.Windows.Interop.HwndSource>, cuyos parámetros son similares a los de CreateWindow:  
  
```  
HwndSource^ source = gcnew HwndSource(  
    0, // class style  
    WS_VISIBLE | WS_CHILD, // style  
    0, // exstyle  
    x, y, width, height,  
    "hi", // NAME  
    IntPtr(parent) // parent window   
    );  
```  
  
 A continuación, se crea el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de contenido mediante una llamada a su constructor de clase:  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 A continuación, conectar la página a la <xref:System.Windows.Interop.HwndSource>:  
  
```  
source->RootVisual = page;  
```  
  
 Y en la línea final, se devuelve el HWND para el <xref:System.Windows.Interop.HwndSource>:  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a>Colocar el HWND  
 Ahora que tiene un HWND que contiene el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj, es necesario colocar ese HWND dentro de la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] cuadro de diálogo.  Si supiera dónde colocar el HWND, bastaría con pasar dicho tamaño y la ubicación a la `GetHwnd` función que se definió anteriormente.  pero ha usado un archivo de recursos para definir el cuadro de diálogo, por lo que no sabe con certeza dónde están colocados los HWND.  Puede usar el [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] editor de cuadro de diálogo para colocar un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] estático controlar donde desea que el reloj para ir ("Insertar reloj aquí") y que utilice para colocar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj.  
  
 Cuando se administra WM_INITDIALOG, use `GetDlgItem` para recuperar el HWND del marcador de posición estático:  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 Calcule el tamaño y la posición del marcador de posición STATIC, por lo que puede colocar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj en ese lugar:  
  
 RECT rectángulo;  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 Luego, oculte el marcador de posición STATIC:  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 Y crear el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj HWND en esa ubicación:  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 Para realizar el tutorial resulte interesante y para generar un número real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj, necesitará crear un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en este punto de control de reloj. Puede hacerlo principalmente en el marcado, con tan solo unos pocos controladores de eventos en el código subyacente. Dado que este tutorial es acerca de la interoperación y no sobre el diseño de control, complete el código para el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj se proporciona aquí como un bloque de código, sin instrucciones discretas para crearlo ni lo que significa cada parte. No dude en experimentar con este código para cambiar el aspecto o la funcionalidad del control.  
  
 Aquí está el marcado:  
  
 [!code-xaml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 Y aquí está el código subyacente adjunto:  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 El resultado final tiene el siguiente aspecto:  
  
 ![Cuadro de diálogo Propiedades de fecha y hora](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")  
  
 Para comparar su resultado final con el código que produjo esta captura de pantalla, vea [ejemplo de interoperación de reloj de Win32](http://go.microsoft.com/fwlink/?LinkID=160051).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Interop.HwndSource>  
 [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051) (Ejemplo de interoperación de un reloj de Win32)
