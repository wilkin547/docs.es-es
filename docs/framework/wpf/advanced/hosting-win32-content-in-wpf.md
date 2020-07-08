---
title: Hospedar contenido de Win32
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: c0c62f1999feaf591c512314515f01e83fa12591
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052096"
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="30e80-102">Hospedar contenido de Win32 en WPF</span><span class="sxs-lookup"><span data-stu-id="30e80-102">Hosting Win32 Content in WPF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="30e80-103">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="30e80-103">Prerequisites</span></span>

<span data-ttu-id="30e80-104">Consulte [interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="30e80-104">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="30e80-105">Un tutorial de Win32 en Windows Presentation Framework (HwndHost)</span><span class="sxs-lookup"><span data-stu-id="30e80-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>

<span data-ttu-id="30e80-106">Para reutilizar el contenido de Win32 dentro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de las aplicaciones, use <xref:System.Windows.Interop.HwndHost> , que es un control que hace que HWND parezca [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido.</span><span class="sxs-lookup"><span data-stu-id="30e80-106">To reuse Win32 content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="30e80-107">Al <xref:System.Windows.Interop.HwndSource> igual <xref:System.Windows.Interop.HwndHost> que, es sencillo de usar: derive de <xref:System.Windows.Interop.HwndHost> e implemente `BuildWindowCore` `DestroyWindowCore` los métodos y, a continuación, cree una instancia de la <xref:System.Windows.Interop.HwndHost> clase derivada y colóquela dentro de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación.</span><span class="sxs-lookup"><span data-stu-id="30e80-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

<span data-ttu-id="30e80-108">Si la lógica de Win32 ya está empaquetada como un control, la `BuildWindowCore` implementación es poco más que una llamada a `CreateWindow` .</span><span class="sxs-lookup"><span data-stu-id="30e80-108">If your Win32 logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span> <span data-ttu-id="30e80-109">Por ejemplo, para crear un control LISTBOX de Win32 en C++:</span><span class="sxs-lookup"><span data-stu-id="30e80-109">For example, to create a Win32 LISTBOX control in C++:</span></span>

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

<span data-ttu-id="30e80-110">Pero supongamos que el código de Win32 no es bastante independiente?</span><span class="sxs-lookup"><span data-stu-id="30e80-110">But suppose the Win32 code is not quite so self-contained?</span></span> <span data-ttu-id="30e80-111">En ese caso, puede crear un cuadro de diálogo de Win32 e incrustar su contenido en una aplicación más grande [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30e80-111">If so, you can create a Win32 dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="30e80-112">En el ejemplo se muestra esto en Visual Studio y C++, aunque también es posible hacerlo en otro lenguaje o en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="30e80-112">The sample shows this in Visual Studio and C++, although it is also possible to do this in a different language or at the command line.</span></span>

<span data-ttu-id="30e80-113">Comience con un cuadro de diálogo simple, que se compila en un proyecto de archivo DLL de C++.</span><span class="sxs-lookup"><span data-stu-id="30e80-113">Start with a simple dialog, which is compiled into a C++ DLL project.</span></span>

<span data-ttu-id="30e80-114">A continuación, introduzca el cuadro de diálogo en la aplicación más grande [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="30e80-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>

- <span data-ttu-id="30e80-115">Compilar el archivo DLL como administrado ( `/clr` )</span><span class="sxs-lookup"><span data-stu-id="30e80-115">Compile the DLL as managed (`/clr`)</span></span>

- <span data-ttu-id="30e80-116">Convertir el cuadro de diálogo en un control</span><span class="sxs-lookup"><span data-stu-id="30e80-116">Turn the dialog into a control</span></span>

- <span data-ttu-id="30e80-117">Definir la clase derivada de <xref:System.Windows.Interop.HwndHost> con `BuildWindowCore` `DestroyWindowCore` los métodos y</span><span class="sxs-lookup"><span data-stu-id="30e80-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>

- <span data-ttu-id="30e80-118">Reemplazar el `TranslateAccelerator` método para controlar las teclas de cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="30e80-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>

- <span data-ttu-id="30e80-119">Reemplazar el `TabInto` método para admitir la tabulación</span><span class="sxs-lookup"><span data-stu-id="30e80-119">Override `TabInto` method to support tabbing</span></span>

- <span data-ttu-id="30e80-120">Invalide el `OnMnemonic` método para admitir mnemónicos</span><span class="sxs-lookup"><span data-stu-id="30e80-120">Override `OnMnemonic` method to support mnemonics</span></span>

- <span data-ttu-id="30e80-121">Crear una instancia de la <xref:System.Windows.Interop.HwndHost> subclase y colocarla en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento Right</span><span class="sxs-lookup"><span data-stu-id="30e80-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>

### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="30e80-122">Convertir el cuadro de diálogo en un control</span><span class="sxs-lookup"><span data-stu-id="30e80-122">Turn the Dialog into a Control</span></span>

<span data-ttu-id="30e80-123">Puede convertir un cuadro de diálogo en un HWND secundario mediante los estilos WS_CHILD y DS_CONTROL.</span><span class="sxs-lookup"><span data-stu-id="30e80-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span> <span data-ttu-id="30e80-124">Vaya al archivo de recursos (. RC) donde se define el cuadro de diálogo y busque el principio de la definición del cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="30e80-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>

```text
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

<span data-ttu-id="30e80-125">Cambie la segunda línea a:</span><span class="sxs-lookup"><span data-stu-id="30e80-125">Change the second line to:</span></span>

```text
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

<span data-ttu-id="30e80-126">Esta acción no lo empaqueta completamente en un control independiente; todavía necesita llamar a `IsDialogMessage()` para que Win32 pueda procesar ciertos mensajes, pero el cambio de control proporciona una manera sencilla de colocar esos controles dentro de otro HWND.</span><span class="sxs-lookup"><span data-stu-id="30e80-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so Win32 can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>

## <a name="subclass-hwndhost"></a><span data-ttu-id="30e80-127">Subclase HwndHost</span><span class="sxs-lookup"><span data-stu-id="30e80-127">Subclass HwndHost</span></span>

<span data-ttu-id="30e80-128">Importe los siguientes espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="30e80-128">Import the following namespaces:</span></span>

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

<span data-ttu-id="30e80-129">A continuación, cree una clase derivada de <xref:System.Windows.Interop.HwndHost> e invalide los `BuildWindowCore` `DestroyWindowCore` métodos y:</span><span class="sxs-lookup"><span data-stu-id="30e80-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>

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

<span data-ttu-id="30e80-130">Aquí se usa `CreateDialog` para crear el cuadro de diálogo que es realmente un control.</span><span class="sxs-lookup"><span data-stu-id="30e80-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span> <span data-ttu-id="30e80-131">Dado que se trata de uno de los primeros métodos a los que se llama dentro del archivo DLL, también debe realizar alguna inicialización de Win32 estándar llamando a una función que se definirá más adelante, denominada `InitializeGlobals()` :</span><span class="sxs-lookup"><span data-stu-id="30e80-131">Since this is one of the first methods called inside the DLL, you should also do some standard Win32 initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>

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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="30e80-132">Invalidar el método TranslateAccelerator para controlar las teclas de cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="30e80-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>

<span data-ttu-id="30e80-133">Si ha ejecutado este ejemplo ahora, obtendrá un control de cuadro de diálogo que muestra, pero omitiría todo el procesamiento del teclado que hace que un cuadro de diálogo sea un cuadro de diálogo funcional.</span><span class="sxs-lookup"><span data-stu-id="30e80-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span> <span data-ttu-id="30e80-134">Ahora debería invalidar la `TranslateAccelerator` implementación (que proviene de `IKeyboardInputSink` , una interfaz que <xref:System.Windows.Interop.HwndHost> implementa).</span><span class="sxs-lookup"><span data-stu-id="30e80-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span> <span data-ttu-id="30e80-135">Se llama a este método cuando la aplicación recibe WM_KEYDOWN y WM_SYSKEYDOWN.</span><span class="sxs-lookup"><span data-stu-id="30e80-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>

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

<span data-ttu-id="30e80-136">Se trata de una gran cantidad de código en una pieza, por lo que podría usar algunas explicaciones más detalladas.</span><span class="sxs-lookup"><span data-stu-id="30e80-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span> <span data-ttu-id="30e80-137">En primer lugar, el código que usa macros de C++ y C++; debe tener en cuenta que ya existe una macro denominada `TranslateAccelerator` , que se define en Winuser. h:</span><span class="sxs-lookup"><span data-stu-id="30e80-137">First, the code using C++ and C++ macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

<span data-ttu-id="30e80-138">Asegúrese de definir un `TranslateAccelerator` método y no un `TranslateAcceleratorW` método.</span><span class="sxs-lookup"><span data-stu-id="30e80-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>

<span data-ttu-id="30e80-139">Del mismo modo, hay el mensaje Winuser. h no administrado y el struct administrado `Microsoft::Win32::MSG` .</span><span class="sxs-lookup"><span data-stu-id="30e80-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span> <span data-ttu-id="30e80-140">Puede eliminar la ambigüedad entre los dos mediante el `::` operador de C++.</span><span class="sxs-lookup"><span data-stu-id="30e80-140">You can disambiguate between the two using the C++ `::` operator.</span></span>

```cpp
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
    ModifierKeys modifiers) override
{
    ::MSG m = ConvertMessage(msg);
}
```

<span data-ttu-id="30e80-141">Ambos mensajes tienen los mismos datos, pero a veces es más fácil trabajar con la definición no administrada, por lo que en este ejemplo puede definir la rutina de conversión obvia:</span><span class="sxs-lookup"><span data-stu-id="30e80-141">Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:</span></span>

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

<span data-ttu-id="30e80-142">Vuelva a `TranslateAccelerator` .</span><span class="sxs-lookup"><span data-stu-id="30e80-142">Back to `TranslateAccelerator`.</span></span> <span data-ttu-id="30e80-143">El principio básico es llamar a la función de Win32 `IsDialogMessage` para hacer tanto trabajo como sea posible, pero `IsDialogMessage` no tiene acceso a nada fuera del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="30e80-143">The basic principle is to call the Win32 function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="30e80-144">Como ficha de usuario en torno al cuadro de diálogo, cuando se ejecuta el tabulador más allá del último control de nuestro cuadro de diálogo, debe establecer el foco en la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] parte mediante una llamada a `IKeyboardInputSite::OnNoMoreStops` .</span><span class="sxs-lookup"><span data-stu-id="30e80-144">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>

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

<span data-ttu-id="30e80-145">Por último, llame a `IsDialogMessage`.</span><span class="sxs-lookup"><span data-stu-id="30e80-145">Finally, call `IsDialogMessage`.</span></span> <span data-ttu-id="30e80-146">Pero una de las responsabilidades de un `TranslateAccelerator` método consiste en indicar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] si se ha controlado o no la pulsación de tecla.</span><span class="sxs-lookup"><span data-stu-id="30e80-146">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="30e80-147">Si no lo ha identificado, el evento de entrada puede Tunelizar y propagar por el resto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="30e80-147">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="30e80-148">En este caso, expondrá una peculiaridad del control de messange de teclado y la naturaleza de la arquitectura de entrada en Win32.</span><span class="sxs-lookup"><span data-stu-id="30e80-148">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in Win32.</span></span> <span data-ttu-id="30e80-149">Desafortunadamente, `IsDialogMessage` no devuelve de ninguna manera si controla una pulsación de tecla determinada.</span><span class="sxs-lookup"><span data-stu-id="30e80-149">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span> <span data-ttu-id="30e80-150">Incluso peor, llamará a las `DispatchMessage()` pulsaciones de tecla que no debe controlar.</span><span class="sxs-lookup"><span data-stu-id="30e80-150">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="30e80-151">Por lo tanto, tendrá que realizar ingeniería inversa `IsDialogMessage` y llamarlo solo para las claves que sepa que va a administrar:</span><span class="sxs-lookup"><span data-stu-id="30e80-151">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>

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

### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="30e80-152">Invalide el método TabInto para admitir la tabulación</span><span class="sxs-lookup"><span data-stu-id="30e80-152">Override TabInto Method to Support Tabbing</span></span>

<span data-ttu-id="30e80-153">Ahora que ha implementado `TranslateAccelerator` , un usuario puede hacer una tabulación en el cuadro de diálogo y salir de él en la aplicación más grande [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30e80-153">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="30e80-154">Pero un usuario no puede volver a la pestaña en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="30e80-154">But a user cannot tab back into the dialog box.</span></span> <span data-ttu-id="30e80-155">Para solucionarlo, invalide `TabInto` :</span><span class="sxs-lookup"><span data-stu-id="30e80-155">To solve that, you override `TabInto`:</span></span>

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

<span data-ttu-id="30e80-156">El `TraversalRequest` parámetro indica si la acción de tabulación es una tabulación o una tecla Mayús.</span><span class="sxs-lookup"><span data-stu-id="30e80-156">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>

### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="30e80-157">Invalide el método de mnemotécnico para admitir las teclas de método</span><span class="sxs-lookup"><span data-stu-id="30e80-157">Override OnMnemonic Method to Support Mnemonics</span></span>

<span data-ttu-id="30e80-158">La administración del teclado está casi completa, pero falta algo: los mnemónicos no funcionan.</span><span class="sxs-lookup"><span data-stu-id="30e80-158">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span> <span data-ttu-id="30e80-159">Si un usuario presiona ALT-F, el foco no salta al cuadro de edición "nombre:".</span><span class="sxs-lookup"><span data-stu-id="30e80-159">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="30e80-160">Por lo tanto, invalide el `OnMnemonic` método:</span><span class="sxs-lookup"><span data-stu-id="30e80-160">So, you override the `OnMnemonic` method:</span></span>

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

<span data-ttu-id="30e80-161">¿Por qué no llamar `IsDialogMessage` aquí?</span><span class="sxs-lookup"><span data-stu-id="30e80-161">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="30e80-162">Tiene el mismo problema que antes: debe ser capaz de notificar al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] código si el código controló la pulsación de tecla o no, y `IsDialogMessage` no puede hacerlo.</span><span class="sxs-lookup"><span data-stu-id="30e80-162">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span> <span data-ttu-id="30e80-163">También hay un segundo problema, porque `IsDialogMessage` rechaza procesar el mnemotécnico si el HWND con foco no está dentro del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="30e80-163">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>

### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="30e80-164">Crear una instancia de la clase derivada HwndHost</span><span class="sxs-lookup"><span data-stu-id="30e80-164">Instantiate the HwndHost Derived Class</span></span>

<span data-ttu-id="30e80-165">Por último, ahora que la compatibilidad con la clave y la pestaña está en su lugar, puede colocar su <xref:System.Windows.Interop.HwndHost> en la aplicación más grande [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30e80-165">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="30e80-166">Si la aplicación principal está escrita en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , la manera más fácil de colocarla en el lugar correcto es dejar un <xref:System.Windows.Controls.Border> elemento vacío donde desea colocar el <xref:System.Windows.Interop.HwndHost> .</span><span class="sxs-lookup"><span data-stu-id="30e80-166">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span> <span data-ttu-id="30e80-167">Aquí creará un <xref:System.Windows.Controls.Border> denominado `insertHwndHostHere` :</span><span class="sxs-lookup"><span data-stu-id="30e80-167">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>

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

<span data-ttu-id="30e80-168">Después, todo lo que queda es encontrar un buen lugar en la secuencia de código para crear una instancia del <xref:System.Windows.Interop.HwndHost> y conectarlo al <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="30e80-168">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="30e80-169">En este ejemplo, lo colocará dentro del constructor para la <xref:System.Windows.Window> clase derivada:</span><span class="sxs-lookup"><span data-stu-id="30e80-169">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>

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

<span data-ttu-id="30e80-170">Lo que le proporciona:</span><span class="sxs-lookup"><span data-stu-id="30e80-170">Which gives you:</span></span>

![Captura de pantalla de la aplicación WPF en ejecución.](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a><span data-ttu-id="30e80-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="30e80-172">See also</span></span>

- [<span data-ttu-id="30e80-173">Interoperabilidad de WPF y Win32</span><span class="sxs-lookup"><span data-stu-id="30e80-173">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
