---
title: Hospedar contenido de Win32
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: b3113d9f3146e1590363dc9db6f751a429dda74b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747013"
---
# <a name="hosting-win32-content-in-wpf"></a>Hospedar contenido de Win32 en WPF

## <a name="prerequisites"></a>Requisitos previos

Consulte [interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md).

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>Un tutorial de Win32 en Windows Presentation Framework (HwndHost)

Para reutilizar el contenido de Win32 dentro de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones, use <xref:System.Windows.Interop.HwndHost>, que es un control que hace que HWND tenga el aspecto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido. Como <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> es sencillo de usar: derivar de <xref:System.Windows.Interop.HwndHost> e implementar métodos `BuildWindowCore` y `DestroyWindowCore` y, a continuación, crear una instancia de la clase derivada <xref:System.Windows.Interop.HwndHost> y colocarla dentro de la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Si la lógica de Win32 ya está empaquetada como un control, la implementación de `BuildWindowCore` es poco más que una llamada a `CreateWindow`. Por ejemplo, para crear un control LISTBOX de Win32 C++en:

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

Pero supongamos que el código de Win32 no es bastante independiente? En ese caso, puede crear un cuadro de diálogo de Win32 e incrustar su contenido en una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mayor. En el ejemplo se muestra esto en Visual C++Studio y, aunque también es posible hacerlo en otro lenguaje o en la línea de comandos.

Comience con un cuadro de diálogo simple, que se compila C++ en un proyecto dll.

A continuación, introduzca el cuadro de diálogo en la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mayor:

- Compilar el archivo DLL como administrado (`/clr`)

- Convertir el cuadro de diálogo en un control

- Definir la clase derivada de <xref:System.Windows.Interop.HwndHost> con los métodos `BuildWindowCore` y `DestroyWindowCore`

- Invalidar `TranslateAccelerator` método para controlar las teclas de cuadro de diálogo

- Invalidar `TabInto` método para admitir la tabulación

- Invalide `OnMnemonic` método para admitir mnemónicos

- Crear una instancia de la subclase <xref:System.Windows.Interop.HwndHost> y colocarla en el elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] derecho

### <a name="turn-the-dialog-into-a-control"></a>Convertir el cuadro de diálogo en un control

Puede convertir un cuadro de diálogo en un HWND secundario mediante los estilos WS_CHILD y DS_CONTROL. Vaya al archivo de recursos (. RC) donde se define el cuadro de diálogo y busque el principio de la definición del cuadro de diálogo:

```text
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

Cambie la segunda línea a:

```text
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

Esta acción no lo empaqueta completamente en un control independiente; todavía necesita llamar a `IsDialogMessage()` para que Win32 pueda procesar ciertos mensajes, pero el cambio de control proporciona una manera sencilla de colocar esos controles dentro de otro HWND.

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

A continuación, cree una clase derivada de <xref:System.Windows.Interop.HwndHost> e invalide los métodos `BuildWindowCore` y `DestroyWindowCore`:

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

Aquí se usa el `CreateDialog` para crear el cuadro de diálogo que es realmente un control. Dado que se trata de uno de los primeros métodos a los que se llama dentro del archivo DLL, también debe realizar alguna inicialización de Win32 estándar llamando a una función que se va a definir más adelante, denominada `InitializeGlobals()`:

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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a>Invalidar el método TranslateAccelerator para controlar las teclas de cuadro de diálogo

Si ha ejecutado este ejemplo ahora, obtendrá un control de cuadro de diálogo que muestra, pero omitiría todo el procesamiento del teclado que hace que un cuadro de diálogo sea un cuadro de diálogo funcional. Ahora debería invalidar la implementación `TranslateAccelerator` (que proviene de `IKeyboardInputSink`, una interfaz que <xref:System.Windows.Interop.HwndHost> implementa). Se llama a este método cuando la aplicación recibe WM_KEYDOWN y WM_SYSKEYDOWN.

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

Se trata de una gran cantidad de código en una pieza, por lo que podría usar algunas explicaciones más detalladas. En primer lugar, el C++ código C++ mediante macros y. debe tener en cuenta que ya existe una macro denominada `TranslateAccelerator`, que se define en Winuser. h:

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

Asegúrese de definir un método `TranslateAccelerator` y no un método `TranslateAcceleratorW`.

Del mismo modo, hay el mensaje Winuser. h no administrado y el de `Microsoft::Win32::MSG` administrado. Puede eliminar la ambigüedad entre los dos mediante C++ el operador `::`.

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

Vuelva a `TranslateAccelerator`. El principio básico es llamar a la función de Win32 `IsDialogMessage` para hacer tanto trabajo como sea posible, pero `IsDialogMessage` no tiene acceso a nada fuera del cuadro de diálogo. Como ficha de usuario en torno al cuadro de diálogo, cuando se ejecuta el tabulador más allá del último control de nuestro cuadro de diálogo, debe establecer el foco en la parte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llamando a `IKeyboardInputSite::OnNoMoreStops`.

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

Por último, llame a `IsDialogMessage`. Pero una de las responsabilidades de un método `TranslateAccelerator` está indicando a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] si se ha controlado o no la pulsación de tecla. Si no lo ha identificado, el evento de entrada puede Tunelizar y propagar por el resto de la aplicación. En este caso, expondrá una peculiaridad del control de messange de teclado y la naturaleza de la arquitectura de entrada en Win32. Desafortunadamente, `IsDialogMessage` no devuelve de ninguna manera si controla una pulsación de tecla determinada. Incluso peor, llamará `DispatchMessage()` en las pulsaciones de teclas que no debería controlar.  Por lo tanto, tendrá que aplicar ingeniería inversa `IsDialogMessage`y solo llamarla para las claves que sepa que controlará:

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

### <a name="override-tabinto-method-to-support-tabbing"></a>Invalide el método TabInto para admitir la tabulación

Ahora que ha implementado `TranslateAccelerator`, un usuario puede hacer una tabulación en el cuadro de diálogo y salir de él en la aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mayor. Pero un usuario no puede volver a la pestaña en el cuadro de diálogo. Para solucionarlo, invalide `TabInto`:

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

El parámetro `TraversalRequest` indica si la acción de tabulación es una tabulación o una tabulación de Mayús.

### <a name="override-onmnemonic-method-to-support-mnemonics"></a>Invalide el método de mnemotécnico para admitir las teclas de método

La administración del teclado está casi completa, pero falta algo: los mnemónicos no funcionan. Si un usuario presiona ALT-F, el foco no salta al cuadro de edición "nombre:". Por lo tanto, invalide el método `OnMnemonic`:

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

¿Por qué no llamar `IsDialogMessage` aquí?  Tiene el mismo problema que antes: debe ser capaz de informar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] código si el código controló la pulsación de tecla o no y `IsDialogMessage` no puede hacerlo. También hay un segundo problema, porque `IsDialogMessage` rechaza procesar el mnemotécnico si el HWND centrado no está dentro del cuadro de diálogo.

### <a name="instantiate-the-hwndhost-derived-class"></a>Crear una instancia de la clase derivada HwndHost

Por último, ahora que la compatibilidad con la clave y la pestaña está en su lugar, puede colocar el <xref:System.Windows.Interop.HwndHost> en la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] más grande. Si la aplicación principal se escribe en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], la manera más sencilla de colocarla en el lugar correcto es dejar un elemento <xref:System.Windows.Controls.Border> vacío donde desea colocar el <xref:System.Windows.Interop.HwndHost>. Aquí creará una <xref:System.Windows.Controls.Border> denominada `insertHwndHostHere`:

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

Después, todo lo que queda es encontrar un buen lugar en la secuencia de código para crear una instancia del <xref:System.Windows.Interop.HwndHost> y conectarlo a la <xref:System.Windows.Controls.Border>. En este ejemplo, lo colocará dentro del constructor para la clase derivada <xref:System.Windows.Window>:

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

Lo que le proporciona:

![Captura de pantalla de la aplicación WPF en ejecución.](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a>Vea también

- [Interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md)
