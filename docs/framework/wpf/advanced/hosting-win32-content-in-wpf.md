---
title: Hospedar contenido de Win32 en WPF
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: 3c00539eb5f2a96fec974accda2fea1c0200aeec
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2019
ms.locfileid: "63807770"
---
# <a name="hosting-win32-content-in-wpf"></a>Hospedar contenido de Win32 en WPF

## <a name="prerequisites"></a>Requisitos previos

Consulte [WPF e interoperabilidad con Win32](wpf-and-win32-interoperation.md).

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>Un tutorial de Win32 dentro de Windows Presentation Framework (HwndHost)

Volver a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] contenido dentro de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de las aplicaciones, usar <xref:System.Windows.Interop.HwndHost>, que es un control que hace que los HWND aspecto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido. Al igual que <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> es fácil de usar: derivar de <xref:System.Windows.Interop.HwndHost> e implementar `BuildWindowCore` y `DestroyWindowCore` métodos, a continuación, cree una instancia su <xref:System.Windows.Interop.HwndHost> clase derivada y colóquelo dentro de su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación.

Si su [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] lógica ya se empaqueta como un control, la `BuildWindowCore` es poco más que una llamada a la implementación `CreateWindow`. Por ejemplo, para crear un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control LISTBOX en [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:

```cpp
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

¿Pero supongamos que la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] código no es tan independiente? Si es así, puede crear un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] diálogo cuadro e insertar su contenido en una mayor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación. El ejemplo muestra esto en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] y [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], aunque también es posible hacerlo en un idioma diferente o en la línea de comandos.

Comience con un sencillo cuadro de diálogo, que se compila en un [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] proyecto.

A continuación, introducir el cuadro de diálogo en el mayor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación:

- Compile el [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] como administrado (`/clr`)

- Activar el cuadro de diálogo en un control

- Defina la clase derivada de <xref:System.Windows.Interop.HwndHost> con `BuildWindowCore` y `DestroyWindowCore` métodos

- Invalidar `TranslateAccelerator` método para controlar las claves del cuadro de diálogo

- Invalidar `TabInto` método para admitir la tabulación

- Invalidar `OnMnemonic` método para admitir las teclas de acceso

- Crear una instancia de la <xref:System.Windows.Interop.HwndHost> subclase y colóquelo debajo de la derecha [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento

### <a name="turn-the-dialog-into-a-control"></a>Activar el cuadro de diálogo en un Control

Un cuadro de diálogo se puede convertir en un elemento secundario con los estilos WS_CHILD y DS_CONTROL de HWND. ENTRAR en el archivo de recursos (.rc) donde se define el cuadro de diálogo y buscar el principio de la definición del cuadro de diálogo:

```
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

Cambiar la segunda línea:

```
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

Esta acción no totalmente empaquetarlo en un control independiente; aun así deberá llamar a `IsDialogMessage()` para [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] puede procesar determinados mensajes, pero el cambio de control proporcionan una manera sencilla de colocar los controles dentro de otro HWND.

## <a name="subclass-hwndhost"></a>Subclase HwndHost

Importe los siguientes espacios de nombres:

```cpp
namespace ManagedCpp
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Input;
    using namespace System::Windows::Media;
    using namespace System::Runtime::InteropServices;
```

A continuación, cree una clase derivada de <xref:System.Windows.Interop.HwndHost> e invalidar la `BuildWindowCore` y `DestroyWindowCore` métodos:

```cpp
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

Aquí se usa el `CreateDialog` para crear el cuadro de diálogo que es en realidad un control. Puesto que este es uno de los primeros métodos llamados dentro de la [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], también debe hacer algunos estándar [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] inicialización mediante una llamada a una función que se definirá más adelante, llamado `InitializeGlobals()`:

```cpp
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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a>Invalidar el método TranslateAccelerator para administrar las claves del cuadro de diálogo

Ahora, si se ha ejecutado en este ejemplo se obtendría un control de cuadro de diálogo que muestra, pero podría omitir todo del teclado de procesamiento que facilita un cuadro de diálogo un cuadro de diálogo funcional. Ahora, debe invalidar el `TranslateAccelerator` implementación (que proviene de `IKeyboardInputSink`, una interfaz que <xref:System.Windows.Interop.HwndHost> implementa). Este método se llama cuando la aplicación recibe WM_KEYDOWN y WM_SYSKEYDOWN.

```cpp
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

Se trata de mucho código en una sola pieza, de manera que pueda usar algunas explicaciones más detalladas. En primer lugar, el código usando [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] y [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] macros; deberá tener en cuenta que ya hay una macro denominada `TranslateAccelerator`, que se define en winuser.h:

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

Así que asegúrese de definir una `TranslateAccelerator` método y no un `TranslateAcceleratorW` método.

De forma similar, es el winuser.h MSG no administrado y el administrado `Microsoft::Win32::MSG` struct. Puede eliminar la ambigüedad entre los dos mediante la [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` operador.

```cpp
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
    ModifierKeys modifiers) override
{
    ::MSG m = ConvertMessage(msg);
}

Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:

```cpp
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

Volver a `TranslateAccelerator`. El principio básico es llamar a la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] función `IsDialogMessage` realice tanto trabajo como sea posible, pero `IsDialogMessage` no tiene acceso a cualquier elemento fuera del cuadro de diálogo. Cuando se ejecuta una pestaña de usuario en el cuadro de diálogo, al desplazarse más allá del último control en el cuadro de diálogo, deberá establecer el foco en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] parte mediante una llamada a `IKeyboardInputSite::OnNoMoreStops`.

```cpp
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

Por último, llame a `IsDialogMessage`. Pero una de las responsabilidades de un `TranslateAccelerator` indica método [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] si se controla la pulsación de tecla o no. Si no se administró, puede tunelizar el evento de entrada y propagan a través del resto de la aplicación. En este caso, va a exponer una peculiaridad de administración de mensajes del teclado y la naturaleza de la arquitectura de entrada en [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Por desgracia, `IsDialogMessage` no devuelve de ninguna manera si controla una pulsación de tecla determinada. Aún peor, llamará `DispatchMessage()` no debe controlar las pulsaciones de teclas.  Por lo que tendrá que realizar ingeniería inversa `IsDialogMessage`y se invoca solo para las teclas que sepa va a controlar:

```cpp
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

### <a name="override-tabinto-method-to-support-tabbing"></a>Invalidar el método TabInto para permitir las tabulaciones

Ahora que ha implementado `TranslateAccelerator`, un usuario puede tabulación para desplazarse por el cuadro de diálogo cuadro y saltar a la mayor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación. Pero un usuario no puede ficha en el cuadro de diálogo. Para resolverlo, invalida `TabInto`:

```cpp
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

El `TraversalRequest` parámetro indica si la acción de ficha es un tab o MAYÚS+TAB.

### <a name="override-onmnemonic-method-to-support-mnemonics"></a>Invalidar el método OnMnemonic para admitir las teclas de acceso

Administración del teclado está casi completo, pero hay una falta algo: las teclas de acceso no funcionan. Si un usuario presiona alt-F, el foco no salta a la "nombre:" cuadro de edición. Por lo tanto, invalida el `OnMnemonic` método:

```cpp
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

¿Por qué no llamar a `IsDialogMessage` aquí?  Tienen el mismo problema como antes, deberá ser capaz de informar a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] código si el código controla la pulsación de tecla o no, y `IsDialogMessage` no puede hacer eso. También hay un problema de segundo, el porque `IsDialogMessage` se niega a procesar la tecla de acceso si el HWND enfocado no está dentro del cuadro de diálogo.

### <a name="instantiate-the-hwndhost-derived-class"></a>Crear una instancia de clase derivada de HwndHost

Por último, ahora que toda la compatibilidad de pestaña y la clave está en su lugar, puede colocar su <xref:System.Windows.Interop.HwndHost> en el mayor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación. Si la aplicación principal está escrita [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], colocarlo en el lugar correcto de la forma más sencilla es dejar vacío <xref:System.Windows.Controls.Border> elemento donde desea colocar el <xref:System.Windows.Interop.HwndHost>. Aquí se crea un <xref:System.Windows.Controls.Border> denominado `insertHwndHostHere`:

```xaml
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

A continuación, todo lo que queda es buscar un buen punto de secuencia de código para crear instancias de la <xref:System.Windows.Interop.HwndHost> y conectarlo a la <xref:System.Windows.Controls.Border>. En este ejemplo, se coloca dentro del constructor para la <xref:System.Windows.Window> clase derivada:

```csharp
public partial class Window1 : Window {
    public Window1() {
    }

    void Window1_Loaded(object sender, RoutedEventArgs e) {
        HwndHost host = new ManagedCpp.MyHwndHost();
        insertHwndHostHere.Child = host;
    }
}
```

Que proporciona:

![Captura de pantalla de la aplicación WPF que se ejecuta.](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a>Vea también

- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
