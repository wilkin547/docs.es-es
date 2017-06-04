---
title: "Tutorial: Hospedar un reloj de WPF en Win32 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "interoperabilidad [WPF], tutoriales"
  - "interoperabilidad [WPF], Win32"
  - "código Win32, interoperabilidad con WPF"
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Tutorial: Hospedar un reloj de WPF en Win32
Para colocar contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro de aplicaciones [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], utilice <xref:System.Windows.Interop.HwndSource>, que proporciona el identificador de ventana HWND que incluye el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  En primer lugar, se crea <xref:System.Windows.Interop.HwndSource>, proporcionándole parámetros parecidos a los de CreateWindow.  A continuación, se comunica a <xref:System.Windows.Interop.HwndSource> el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que se desea colocar en su interior.  Por último, se saca el HWND del objeto <xref:System.Windows.Interop.HwndSource>.  En este tutorial se muestra cómo crear una aplicación mixta de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro de una aplicación de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] que vuelve a implementar el cuadro de diálogo **Propiedades de fecha y hora** del sistema operativo.  
  
## Requisitos previos  
 Vea [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
## Cómo utilizar este tutorial  
 Este tutorial se concentra en los pasos importantes de la generación de una aplicación de interacción.  El tutorial está respaldado por un ejemplo, [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051), que refleja el producto final.  En este tutorial se documentan los pasos como si usted comenzase con su propio proyecto de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] existente, quizás un proyecto que existiera previamente, y agregase contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedado a su aplicación.  Puede comparar su producto final con [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051).  
  
## Tutorial de Windows Presentation Framework dentro de Win32 \(HwndSource\)  
 En el gráfico siguiente se muestra el producto final previsto en este tutorial:  
  
 ![Cuadro de diálogo Propiedades de fecha y hora](../../../../docs/framework/wpf/advanced/media/interoparch06.png "InteropArch06")  
  
 Puede volver a crear este cuadro de diálogo creando un proyecto C\+\+ de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] y utilizando el editor de cuadros de diálogo para crear lo siguiente:  
  
 ![Cuadro de diálogo Propiedades de fecha y hora](../../../../docs/framework/wpf/advanced/media/interoparch07.png "InteropArch07")  
  
 \(No es necesario utilizar [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] para usar <xref:System.Windows.Interop.HwndSource>, ni se necesita utilizar C\+\+ para escribir programas de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], pero ésta es una manera bastante habitual de hacerlo y se presta bien a una explicación paso a paso, como la de este tutorial\).  
  
 Debe realizar cinco pasos secundarios concretos para colocar un reloj de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en el cuadro de diálogo:  
  
1.  Habilite el proyecto de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para llamar al código administrado \(**\/clr**\) cambiando los valores del proyecto en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].  
  
2.  Cree un objeto <xref:System.Windows.Controls.Page> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en un archivo DLL independiente.  
  
3.  Coloque el objeto <xref:System.Windows.Controls.Page> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro de un <xref:System.Windows.Interop.HwndSource>.  
  
4.  Obtenga un identificador de ventana HWND para ese objeto <xref:System.Windows.Controls.Page> utilizando la propiedad <xref:System.Windows.Interop.HwndSource.Handle%2A>.  
  
5.  Utilice [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para decidir dónde desea colocar el HWND dentro de la aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] mayor.  
  
## \/clr  
 El primer paso consiste en convertir este proyecto de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] no administrado en uno capaz de llamar al código administrado.  Se utiliza la opción del compilador \/clr, que establecerá los vínculos a los archivos DLL necesarios que desee utilizar y ajustará el método Main para su uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Para habilitar el uso de código administrado dentro del proyecto C\+\+: haga clic con el botón secundario del mouse en el proyecto win32clock y seleccione **Propiedades**.  En la página de propiedades **General** \(que es la predeterminada\), cambie compatible con Common Language Runtime a `/clr`.  
  
 A continuación, agregue referencias a los archivos DLL necesarios para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll y UIAutomationTypes.dll.  \(En las instrucciones siguientes se da por hecho que el sistema operativo está instalado en la unidad C:.\)  
  
1.  Haga clic con el botón secundario en el proyecto Win32clock y seleccione **Referencias...**. Dentro de ese cuadro de diálogo:  
  
2.  Haga clic con el botón secundario en el proyecto Win32clock y seleccione **Referencias...**.  
  
3.  Haga clic sucesivamente en **Agregar nueva referencia** y en la ficha Examinar, escriba C:\\Archivos de programa\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\PresentationCore.dll y haga clic en Aceptar.  
  
4.  Repita este paso para PresentationFramework.dll: C:\\Archivos de programa\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\PresentationFramework.dll.  
  
5.  Repita este paso para WindowsBase.dll: C:\\Archivos de programa\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\WindowsBase.dll.  
  
6.  Repita este paso para UIAutomationTypes.dll: C:\\Archivos de programa\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\UIAutomationTypes.dll.  
  
7.  Repita este paso para UIAutomationProvider.dll: C:\\Archivos de programa\\Reference Assemblies\\Microsoft\\Framework\\v3.0\\UIAutomationProvider.dll.  
  
8.  Haga clic en **Agregar nueva referencia**, seleccione System.dll y haga clic en **Aceptar**.  
  
9. Haga clic en **Aceptar** a fin de salir de las páginas de propiedades de win32clock para agregar referencias.  
  
 Por último, agregue `STAThreadAttribute` al método `_tWinMain` para su uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 Este atributo indica a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] que debe utilizar un modelo de apartamentos de un único subproceso \(STA\) al inicializar [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)]; este modelo es necesario para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \(y para [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\).  
  
## Crear una página de Windows Presentation Framework  
 Luego, se crea un archivo DLL que define un objeto <xref:System.Windows.Controls.Page> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Con frecuencia resulta más sencillo crear el objeto <xref:System.Windows.Controls.Page> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] como una aplicación independiente y escribir y depurar la parte de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de ese modo.  Cuando haya finalizado, el proyecto podrá convertirse en un archivo DLL. Para ello, haga clic con el botón secundario en el proyecto, haga clic en **Propiedades**, vaya a la aplicación y cambie el tipo de salida a Biblioteca de clases de Windows.  
  
 El proyecto de DLL de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se puede combinar seguidamente con el proyecto [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] \(una solución que contiene dos proyectos\). Haga clic con el botón secundario en la solución y seleccione **Agregar Proyecto existente**.  
  
 Para utilizar ese archivo DLL de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del proyecto de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], debe agregar una referencia:  
  
1.  Haga clic con el botón secundario en el proyecto Win32clock y seleccione **Referencias...**.  
  
2.  Haga clic en **Agregar nueva referencia**.  
  
3.  Haga clic en la ficha **Proyectos**.  Seleccione WPFClock y haga clic en Aceptar.  
  
4.  Haga clic en **Aceptar** a fin de salir de las páginas de propiedades de win32clock para agregar referencias.  
  
## HwndSource  
 A continuación, se utiliza <xref:System.Windows.Interop.HwndSource> para que el objeto <xref:System.Windows.Controls.Page> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se parezca a un HWND.  Se agrega este bloque de código a un archivo C\+\+:  
  
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
  
 Es un fragmento de código extenso, que merece algunas explicaciones.  La primera parte consiste en varias cláusulas para que no tenga que certificar totalmente todas las llamadas:  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 A continuación, se define una función que crea el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], lo incluye en un <xref:System.Windows.Interop.HwndSource> y devuelve el HWND:  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 En primer lugar, se crea un <xref:System.Windows.Interop.HwndSource>, cuyos parámetros son similares a los de CreateWindow:  
  
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
  
 A continuación, se crea la clase de contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llamando a su constructor:  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 Luego se conecta la página a <xref:System.Windows.Interop.HwndSource>:  
  
```  
source->RootVisual = page;  
```  
  
 Por último, en la línea final, se devuelve el HWND para <xref:System.Windows.Interop.HwndSource>:  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## Colocar el HWND  
 Ahora que ya tiene un HWND que contiene el reloj de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], hay que colocarlo dentro del cuadro de diálogo de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Si supiera dónde colocarlo exactamente, bastaría con pasar el tamaño y la ubicación a la función `GetHwnd` que se definió anteriormente.  Sin embargo, se ha utilizado un archivo de recursos para definir el cuadro de diálogo, por lo que no se puede estar seguro con exactitud de la posición de ningún HWND.  Puede utilizar el editor de cuadros de diálogo de [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] para colocar un control STATIC de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] donde desee situar el reloj \("Insert clock here"\), y utilizarlo para colocar el reloj de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Cuando se administra WM\_INITDIALOG, se utiliza `GetDlgItem` para recuperar el HWND del marcador de posición STATIC:  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 A continuación, se calcula el tamaño y la posición del marcador de posición STATIC, para poder colocar el reloj de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en ese lugar:  
  
 RECT rectangle;  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 A continuación, se oculta el marcador de posición STATIC:  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 Y se crea el HWND del reloj de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en esa ubicación:  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 Para que el tutorial resulte interesante y generar un reloj de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] real, deberá crear un control de reloj de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en este punto.  Puede hacerlo principalmente en marcado, con tan sólo algunos controladores de eventos en código subyacente.  Puesto que este tutorial trata sobre interoperabilidad y no sobre el diseño de controles, el código completo del reloj de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se proporciona en un bloque de código, sin instrucciones discretas para crearlo ni explicaciones sobre lo que significa cada parte del mismo.  No dude en experimentar con este código para cambiar la apariencia y el funcionamiento o la funcionalidad del control.  
  
 Éste es el marcado:  
  
 [!code-xml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 Y aquí está el código subyacente que lo acompaña:  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 El resultado final tiene este aspecto:  
  
 ![Cuadro de diálogo Propiedades de fecha y hora](../../../../docs/framework/wpf/advanced/media/interoparch08.png "InteropArch08")  
  
 Para comparar su resultado final con el código que generó esta captura de pantalla, vea [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051).  
  
## Vea también  
 <xref:System.Windows.Interop.HwndSource>   
 [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)   
 [Ejemplo Win32 Clock Interoperation](http://go.microsoft.com/fwlink/?LinkID=160051)