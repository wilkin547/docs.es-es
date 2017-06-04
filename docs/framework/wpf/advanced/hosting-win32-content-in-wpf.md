---
title: "Hospedar contenido de Win32 en WPF | Microsoft Docs"
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
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Hospedar contenido de Win32 en WPF
## Requisitos previos  
 Vea [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
## Un tutorial de Win32 dentro de Windows Presentation Framework \(HwndHost\)  
 Para reutilizar el contenido de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dentro de las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], utilice <xref:System.Windows.Interop.HwndHost>, que es un control que hace que los indicadores de ventana \(HWND\) parezcan contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Al igual que <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> es fácil de usar: derive de <xref:System.Windows.Interop.HwndHost> e implemente los métodos `BuildWindowCore` y `DestroyWindowCore`; a continuación, cree una instancia de la clase derivada de <xref:System.Windows.Interop.HwndHost> y colóquela dentro de la aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Si la lógica de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ya está empaquetada como un control, entonces la implementación de `BuildWindowCore` será poco más que una llamada a `CreateWindow`.  Por ejemplo, para crear un control LISTBOX de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] en [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:  
  
```  
virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {  
    HWND handle = CreateWindowEx(0, L"LISTBOX",   
    L"this is a Win32 listbox",  
    WS_CHILD | WS_VISIBLE | LBS_NOTIFY  
    | WS_VSCROLL | WS_BORDER,  
    0, 0, // x, y  
    30, 70, // height, width  
    (HWND) hwndParent.Handle.ToPointer(), // parent hwnd  
    0, // hmenu  
    0, // hinstance  
    0); // lparam  
  
    return HandleRef(this, IntPtr(handle));  
}  
  
virtual void DestroyWindowCore(HandleRef hwnd) override {  
    // HwndHost will dispose the hwnd for us  
}  
```  
  
 Ahora, supongamos que el código de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] no sea tan autónomo.  En ese caso, puede crear un cuadro de diálogo de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] e incrustar su contenido en una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mayor.  En el ejemplo se muestra este proceso en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] y [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], aunque también es posible hacerlo en otro lenguaje diferente o desde la línea de comandos.  
  
 Comience por un diálogo simple, que se compila en un proyecto de [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] en [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)].  
  
 A continuación, inserte el cuadro de diálogo en la aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mayor:  
  
-   Compile [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] como administrado \(`/clr`\)  
  
-   Convierta el cuadro de diálogo en un control  
  
-   Defina la clase derivada de <xref:System.Windows.Interop.HwndHost> con los métodos `BuildWindowCore` y `DestroyWindowCore`  
  
-   Invalide el método `TranslateAccelerator` para administrar las claves del cuadro de diálogo  
  
-   Invalide el método `TabInto` para admitir la tabulación  
  
-   Invalide el método `OnMnemonic` para admitir las teclas de acceso  
  
-   Cree una instancia de la subclase <xref:System.Windows.Interop.HwndHost> y colóquela bajo el elemento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] correcto  
  
### Convertir el cuadro de diálogo en un control  
 Puede convertir un cuadro de diálogo en un elemento HWND secundario utilizando los estilos WS\_CHILD y DS\_CONTROL.  Vaya al archivo de recursos \(.rc\) donde se define el cuadro de diálogo y busque el principio de la definición del mismo:  
  
```  
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121  
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU  
```  
  
 Cambie la segunda línea a:  
  
```  
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL  
```  
  
 Esta acción no empaqueta totalmente el cuadro de diálogo en un control autónomo; todavía deberá llamar a `IsDialogMessage()` para que [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] pueda procesar determinados mensajes, pero este cambio de control proporciona una manera sencilla de colocar esos controles dentro de otro HWND.  
  
## Subclase HwndHost  
 Importe los espacios de nombres siguientes:  
  
```  
namespace ManagedCpp  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Input;  
    using namespace System::Windows::Media;  
    using namespace System::Runtime::InteropServices;  
```  
  
 A continuación, cree una clase derivada de <xref:System.Windows.Interop.HwndHost> e invalide los métodos `BuildWindowCore` y `DestroyWindowCore`:  
  
```  
public ref class MyHwndHost : public HwndHost, IKeyboardInputSink {  
    private:  
        HWND dialog;  
  
    protected:   
        virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {  
            InitializeGlobals();   
            dialog = CreateDialog(hInstance,   
                MAKEINTRESOURCE(IDD_DIALOG1),   
                (HWND) hwndParent.Handle.ToPointer(),  
                (DLGPROC) About);   
            return HandleRef(this, IntPtr(dialog));  
        }  
  
        virtual void DestroyWindowCore(HandleRef hwnd) override {  
            // hwnd will be disposed for us  
        }  
```  
  
 Aquí, se utiliza `CreateDialog` para crear el cuadro de diálogo que sí es un control en realidad.  Puesto que se trata de uno de los primeros métodos a los que se llama dentro de [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], también debe realizar algún tipo de inicialización estándar de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] llamando a una función que se definirá más adelante, denominada `InitializeGlobals()`:  
  
```  
bool initialized = false;  
    void InitializeGlobals() {  
        if (initialized) return;  
        initialized = true;  
  
        // TODO: Place code here.  
        MSG msg;  
        HACCEL hAccelTable;  
  
        // Initialize global strings  
        LoadString(hInstance, IDS_APP_TITLE, szTitle, MAX_LOADSTRING);  
        LoadString(hInstance, IDC_TYPICALWIN32DIALOG, szWindowClass, MAX_LOADSTRING);  
        MyRegisterClass(hInstance);  
  
```  
  
### Invalidar el método TranslateAccelerator para administrar las claves del cuadro de diálogo  
 Si ejecutara ahora este ejemplo, obtendría un control de cuadro de diálogo que se mostraría pero omitiría todos los procesos de teclado que convierten un cuadro de diálogo en un elemento funcional.  Ahora, debe invalidar la implementación de `TranslateAccelerator` \(que procede de `IKeyboardInputSink`, una interfaz implementada por <xref:System.Windows.Interop.HwndHost>\).  Se llama a este método cuando la aplicación recibe WM\_KEYDOWN y WM\_SYSKEYDOWN.  
  
```  
  
#undef TranslateAccelerator  
        virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
            ModifierKeys modifiers) override   
        {  
            ::MSG m = ConvertMessage(msg);  
  
            // Win32's IsDialogMessage() will handle most of our tabbing, but doesn't know   
            // what to do when it reaches the last tab stop  
            if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {  
                HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
                HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
                TraversalRequest^ request = nullptr;  
  
                if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {  
                    // this code should work, but there’s a bug with interop shift-tab in current builds                      
                    request = gcnew TraversalRequest(FocusNavigationDirection::Last);  
                }  
                else if (!GetKeyState(VK_SHIFT) && GetFocus() == lastTabStop) {  
                    request = gcnew TraversalRequest(FocusNavigationDirection::Next);  
                }  
  
                if (request != nullptr)  
                    return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);  
  
            }  
  
            // Only call IsDialogMessage for keys it will do something with.  
            if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {  
                switch (m.wParam) {  
                    case VK_TAB:  
                    case VK_LEFT:  
                    case VK_UP:  
                    case VK_RIGHT:  
                    case VK_DOWN:  
                    case VK_EXECUTE:  
                    case VK_RETURN:  
                    case VK_ESCAPE:  
                    case VK_CANCEL:  
                        IsDialogMessage(dialog, &m);  
                        // IsDialogMessage should be called ProcessDialogMessage --  
                        // it processes messages without ever really telling you  
                        // if it handled a specific message or not  
                        return true;  
                }  
            }  
  
            return false; // not a key we handled  
        }  
```  
  
 Es un fragmento de código extenso, que merece algunas explicaciones más detalladas.  En primer lugar, dado que se utilizan macros [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] y [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] en el código, es preciso que sea consciente de que ya existe una macro denominada `TranslateAccelerator`, que se define en winuser.h:  
  
```  
#define TranslateAccelerator  TranslateAcceleratorW  
```  
  
 Por tanto, debe asegurarse de definir un método `TranslateAccelerator` y no un método `TranslateAcceleratorW`.  
  
 Igualmente, tenemos winuser.h MSG no administrado y el struct `Microsoft::Win32::MSG` administrado.  Puede eliminar la ambigüedad entre ambas utilizando el operador [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::`.  
  
```  
  
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
    ModifierKeys modifiers) override   
{  
    ::MSG m = ConvertMessage(msg);  
```  
  
 Las dos estructuras MSG tienen los mismos datos, pero a veces es más fácil trabajar con la definición no administrada, por lo que en este ejemplo puede definir la rutina de conversión obvia:  
  
```  
::MSG ConvertMessage(System::Windows::Interop::MSG% msg) {  
    ::MSG m;  
    m.hwnd = (HWND) msg.hwnd.ToPointer();  
    m.lParam = (LPARAM) msg.lParam.ToPointer();  
    m.message = msg.message;  
    m.wParam = (WPARAM) msg.wParam.ToPointer();  
  
    m.time = msg.time;  
  
    POINT pt;  
    pt.x = msg.pt_x;  
    pt.y = msg.pt_y;  
    m.pt = pt;  
  
    return m;  
}  
```  
  
 Volvamos a `TranslateAccelerator`.  El principio básico consiste en llamar a la función `IsDialogMessage` de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para que realice el máximo trabajo posible, pero `IsDialogMessage` no tiene acceso a nada que esté fuera del cuadro de diálogo. Cuando un usuario utiliza la tecla de tabulación para desplazarse por el cuadro de diálogo, si la tabulación sale del último control del mismo, es preciso establecer el foco en la parte correspondiente a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llamando a `IKeyboardInputSite::OnNoMoreStops`.  
  
```  
// Win32's IsDialogMessage() will handle most of the tabbing, but doesn't know   
// what to do when it reaches the last tab stop  
if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {  
    HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
    HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
    TraversalRequest^ request = nullptr;  
  
    if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {  
        request = gcnew TraversalRequest(FocusNavigationDirection::Last);  
    }  
    else if (!GetKeyState(VK_SHIFT) && GetFocus() ==  lastTabStop) { {  
        request = gcnew TraversalRequest(FocusNavigationDirection::Next);  
    }  
  
    if (request != nullptr)  
        return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);  
}  
```  
  
 Por último, llame a `IsDialogMessage`.  Sin embargo, una de las responsabilidades de un método `TranslateAccelerator` es indicar a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] si se administró la presión de tecla o no.  Si no se administró, el evento de entrada puede tunelizar y propagarse a través del resto de la aplicación.  En este punto, se expone una peculiaridad de la administración de mensajes del teclado y la naturaleza de la arquitectura de entrada de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  Por desgracia, `IsDialogMessage` no devuelve nada sobre si ha administrado una pulsación de tecla determinada.  Lo que es peor, llamará a `DispatchMessage()` para presiones de teclas que no debe administrar.  Así que tendrá que efectuar la ingeniería inversa de `IsDialogMessage` y llamarlo únicamente para las teclas que sepa que va a administrar:  
  
```  
// Only call IsDialogMessage for keys it will do something with.  
if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {  
    switch (m.wParam) {  
        case VK_TAB:  
        case VK_LEFT:  
        case VK_UP:  
        case VK_RIGHT:  
        case VK_DOWN:  
        case VK_EXECUTE:  
        case VK_RETURN:  
        case VK_ESCAPE:  
        case VK_CANCEL:  
            IsDialogMessage(dialog, &m);  
            // IsDialogMessage should be called ProcessDialogMessage --  
            // it processes messages without ever really telling you  
            // if it handled a specific message or not  
            return true;  
    }  
```  
  
### Invalidar el método TabInto para permitir las tabulaciones  
 Ahora que ha implementado `TranslateAccelerator`, un usuario puede presionar la tecla de tabulación para desplazarse por el cuadro de diálogo y salir de él a la aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mayor.  Sin embargo, el usuario no puede presionar la tecla de tabulación para volver al cuadro de diálogo.  Para resolverlo, se invalida `TabInto`:  
  
```  
  
public:   
    virtual bool TabInto(TraversalRequest^ request) override {  
        if (request->FocusNavigationDirection == FocusNavigationDirection::Last) {  
            HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
            SetFocus(lastTabStop);  
        }  
        else {  
            HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
            SetFocus(firstTabStop);  
        }  
        return true;  
    }  
  
```  
  
 El parámetro `TraversalRequest` le indica si la acción de tabulación consiste en presionar TAB o MAYÚS\+TAB.  
  
### Invalidar el método OnMnemonic para admitir las teclas de acceso  
 La administración del teclado está casi completa, pero falta algo: las teclas de acceso no funcionan.  Si un usuario presiona ALT\+F, el foco no salta al cuadro de edición "First name:".  De modo que debe invalidar el método `OnMnemonic`:  
  
```  
virtual bool OnMnemonic(System::Windows::Interop::MSG% msg, ModifierKeys modifiers) override {  
    ::MSG m = ConvertMessage(msg);  
  
    // If it's one of our mnemonics, set focus to the appropriate hwnd  
    if (msg.message == WM_SYSCHAR && GetKeyState(VK_MENU /*alt*/)) {  
        int dialogitem = 9999;  
        switch (m.wParam) {  
            case 's': dialogitem = IDOK; break;  
            case 'c': dialogitem = IDCANCEL; break;  
            case 'f': dialogitem = IDC_EDIT1; break;  
            case 'l': dialogitem = IDC_EDIT2; break;  
            case 'p': dialogitem = IDC_EDIT3; break;  
            case 'a': dialogitem = IDC_EDIT4; break;  
            case 'i': dialogitem = IDC_EDIT5; break;  
            case 't': dialogitem = IDC_EDIT6; break;  
            case 'z': dialogitem = IDC_EDIT7; break;  
        }  
        if (dialogitem != 9999) {  
            HWND hwnd = GetDlgItem(dialog, dialogitem);  
            SetFocus(hwnd);  
            return true;  
        }  
    }  
    return false; // key unhandled  
};  
```  
  
 ¿Por qué no se llama a `IsDialogMessage` en este caso?  El problema es el mismo que antes: necesita comunicar al código de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] si el código ha administrado o no la pulsación de tecla e `IsDialogMessage` no lo puede hacer.  Además, hay otro problema, porque `IsDialogMessage` no procesa la tecla de acceso si el HWND que tiene el foco no se encuentra dentro del cuadro de diálogo.  
  
### Crear una instancia de la clase derivada de HwndHost  
 Por último, ahora que ya está implementada la compatibilidad con la presión de teclas y el uso de la tecla de tabulación, puede insertar <xref:System.Windows.Interop.HwndHost> en la aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mayor.  Si la aplicación principal está escrita en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], la manera más fácil de colocarla en el lugar correcto es dejar un elemento <xref:System.Windows.Controls.Border> vacío donde desee colocar <xref:System.Windows.Interop.HwndHost>.  Aquí, se crea un objeto <xref:System.Windows.Controls.Border> denominado `insertHwndHostHere`:  
  
```  
<Window x:Class="WPFApplication1.Window1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    Title="Windows Presentation Framework Application"  
    Loaded="Window1_Loaded"  
    >  
    <StackPanel>  
        <Button Content="WPF button"/>  
        <Border Name="insertHwndHostHere" Height="200" Width="500"/>  
        <Button Content="WPF button"/>  
    </StackPanel>  
</Window>  
```  
  
 A continuación, lo único que falta es encontrar un lugar apropiado en la secuencia del código para crear una instancia de <xref:System.Windows.Interop.HwndHost> y conectarla a <xref:System.Windows.Controls.Border>.  En este ejemplo, se coloca dentro del constructor para la clase derivada de <xref:System.Windows.Window>:  
  
```  
public partial class Window1 : Window {  
    public Window1() {  
    }  
  
    void Window1_Loaded(object sender, RoutedEventArgs e) {  
        HwndHost host = new ManagedCpp.MyHwndHost();  
        insertHwndHostHere.Child = host;  
    }  
}  
```  
  
 Lo que da como resultado:  
  
 ![Captura de pantalla de aplicación WPF](../../../../docs/framework/wpf/advanced/media/interoparch09.png "InteropArch09")  
  
## Vea también  
 [Interoperabilidad de WPF y Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)