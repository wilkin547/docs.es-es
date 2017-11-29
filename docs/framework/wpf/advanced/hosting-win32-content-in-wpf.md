---
title: Hospedar contenido de Win32 en WPF
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
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e82d18cd765fc3ac4f4982a71d187a3741f4f03a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="2630f-102">Hospedar contenido de Win32 en WPF</span><span class="sxs-lookup"><span data-stu-id="2630f-102">Hosting Win32 Content in WPF</span></span>
## <a name="prerequisites"></a><span data-ttu-id="2630f-103">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2630f-103">Prerequisites</span></span>  
 <span data-ttu-id="2630f-104">Vea [WPF y Win32 interoperación](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="2630f-104">See [WPF and Win32 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span></span>  
  
## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="2630f-105">Un tutorial de Win32 dentro de Windows Presentation Framework (HwndHost)</span><span class="sxs-lookup"><span data-stu-id="2630f-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>  
 <span data-ttu-id="2630f-106">Volver a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] contenido dentro de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones, utilizan <xref:System.Windows.Interop.HwndHost>, que es un control que hace que el aspecto HWND [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido.</span><span class="sxs-lookup"><span data-stu-id="2630f-106">To reuse [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>  <span data-ttu-id="2630f-107">Como <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> es fácil de usar: derivan de <xref:System.Windows.Interop.HwndHost> e implementar `BuildWindowCore` y `DestroyWindowCore` , a continuación, crear instancias de métodos, su <xref:System.Windows.Interop.HwndHost> clase derivada y colóquelo dentro de su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación.</span><span class="sxs-lookup"><span data-stu-id="2630f-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  
  
 <span data-ttu-id="2630f-108">Si su [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] lógica ya se empaqueta como un control, la `BuildWindowCore` implementación es algo más que una llamada a `CreateWindow`.</span><span class="sxs-lookup"><span data-stu-id="2630f-108">If your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span>  <span data-ttu-id="2630f-109">Por ejemplo, para crear un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX (control) en [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="2630f-109">For example, to create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX control in [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span></span>  
  
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
  
 <span data-ttu-id="2630f-110">¿Sin embargo, supongamos la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] código no es tan independiente?</span><span class="sxs-lookup"><span data-stu-id="2630f-110">But suppose the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] code is not quite so self-contained?</span></span> <span data-ttu-id="2630f-111">Si es así, puede crear un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] diálogo cuadro y lo inserte su contenido en una mayor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación.</span><span class="sxs-lookup"><span data-stu-id="2630f-111">If so, you can create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  <span data-ttu-id="2630f-112">El ejemplo muestra cómo hacerlo en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] y [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], aunque también es posible hacerlo en un idioma diferente o en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="2630f-112">The sample shows this in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], although it is also possible to do this in a different language or at the command line.</span></span>  
  
 <span data-ttu-id="2630f-113">Iniciar un cuadro de diálogo simple, que se compila en un [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="2630f-113">Start with a simple dialog, which is compiled into a [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] project.</span></span>  
  
 <span data-ttu-id="2630f-114">A continuación, insertar el cuadro de diálogo en el mayor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación:</span><span class="sxs-lookup"><span data-stu-id="2630f-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>  
  
-   <span data-ttu-id="2630f-115">Compile el [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] como administrado (`/clr`)</span><span class="sxs-lookup"><span data-stu-id="2630f-115">Compile the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] as managed (`/clr`)</span></span>  
  
-   <span data-ttu-id="2630f-116">Convertir el cuadro de diálogo en un control</span><span class="sxs-lookup"><span data-stu-id="2630f-116">Turn the dialog into a control</span></span>  
  
-   <span data-ttu-id="2630f-117">Defina la clase derivada de <xref:System.Windows.Interop.HwndHost> con `BuildWindowCore` y `DestroyWindowCore` métodos</span><span class="sxs-lookup"><span data-stu-id="2630f-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>  
  
-   <span data-ttu-id="2630f-118">Invalidar `TranslateAccelerator` método para administrar las claves del cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="2630f-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>  
  
-   <span data-ttu-id="2630f-119">Invalidar `TabInto` método para admitir la tabulación</span><span class="sxs-lookup"><span data-stu-id="2630f-119">Override `TabInto` method to support tabbing</span></span>  
  
-   <span data-ttu-id="2630f-120">Invalidar `OnMnemonic` método para admitir las teclas de acceso</span><span class="sxs-lookup"><span data-stu-id="2630f-120">Override `OnMnemonic` method to support mnemonics</span></span>  
  
-   <span data-ttu-id="2630f-121">Crear una instancia de la <xref:System.Windows.Interop.HwndHost> subclase y colóquelo debajo de la derecha [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento</span><span class="sxs-lookup"><span data-stu-id="2630f-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>  
  
### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="2630f-122">Convertir el cuadro de diálogo en un Control</span><span class="sxs-lookup"><span data-stu-id="2630f-122">Turn the Dialog into a Control</span></span>  
 <span data-ttu-id="2630f-123">Puede convertir un cuadro de diálogo en un elemento HWND secundario utilizando los estilos WS_CHILD y DS_CONTROL.</span><span class="sxs-lookup"><span data-stu-id="2630f-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span>  <span data-ttu-id="2630f-124">ENTRAR en el archivo de recursos (.rc) donde se define el cuadro de diálogo y buscar el principio de la definición del cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="2630f-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>  
  
```  
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121  
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU  
```  
  
 <span data-ttu-id="2630f-125">Cambiar la segunda línea para:</span><span class="sxs-lookup"><span data-stu-id="2630f-125">Change the second line to:</span></span>  
  
```  
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL  
```  
  
 <span data-ttu-id="2630f-126">Esta acción no totalmente empaquetarla en un control independiente; debe llamar a `IsDialogMessage()` para [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] puede procesar determinados mensajes, pero el cambio de control proporcionan una manera sencilla de colocar esos controles dentro de otro HWND.</span><span class="sxs-lookup"><span data-stu-id="2630f-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>  
  
## <a name="subclass-hwndhost"></a><span data-ttu-id="2630f-127">Subclase HwndHost</span><span class="sxs-lookup"><span data-stu-id="2630f-127">Subclass HwndHost</span></span>  
 <span data-ttu-id="2630f-128">Importe los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="2630f-128">Import the following namespaces:</span></span>  
  
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
  
 <span data-ttu-id="2630f-129">A continuación, cree una clase derivada de <xref:System.Windows.Interop.HwndHost> e invalide el `BuildWindowCore` y `DestroyWindowCore` métodos:</span><span class="sxs-lookup"><span data-stu-id="2630f-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>  
  
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
  
 <span data-ttu-id="2630f-130">Aquí se usa el `CreateDialog` para crear el cuadro de diálogo que es realmente un control.</span><span class="sxs-lookup"><span data-stu-id="2630f-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span>  <span data-ttu-id="2630f-131">Puesto que este es uno de los primeros métodos llamados dentro de la [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], también debe hacer algunos estándar [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] inicialización mediante una llamada a una función que se definirá más adelante, denominado `InitializeGlobals()`:</span><span class="sxs-lookup"><span data-stu-id="2630f-131">Since this is one of the first methods called inside the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], you should also do some standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>  
  
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
  
### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="2630f-132">Invalidar el método TranslateAccelerator para administrar las claves del cuadro de diálogo</span><span class="sxs-lookup"><span data-stu-id="2630f-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>  
 <span data-ttu-id="2630f-133">Ahora, si se ejecutó en este ejemplo se obtendría un control de cuadro de diálogo que muestra, pero podría omitir todo del teclado procesamiento que facilita un cuadro de diálogo un cuadro de diálogo funcional.</span><span class="sxs-lookup"><span data-stu-id="2630f-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span>  <span data-ttu-id="2630f-134">Ahora, debe invalidar el `TranslateAccelerator` implementación (que proviene de `IKeyboardInputSink`, una interfaz que <xref:System.Windows.Interop.HwndHost> implementa).</span><span class="sxs-lookup"><span data-stu-id="2630f-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span>  <span data-ttu-id="2630f-135">Este método se invoca cuando la aplicación recibe WM_KEYDOWN y WM_SYSKEYDOWN.</span><span class="sxs-lookup"><span data-stu-id="2630f-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>  
  
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
  
 <span data-ttu-id="2630f-136">Se trata de una gran cantidad de código en una sola pieza, por lo que podría utilizar algunas explicaciones más detalladas.</span><span class="sxs-lookup"><span data-stu-id="2630f-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span>  <span data-ttu-id="2630f-137">En primer lugar, el código que usa [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] y [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] macros, se deben tener en cuenta que ya hay una macro denominada `TranslateAccelerator`, que se define en winuser.h:</span><span class="sxs-lookup"><span data-stu-id="2630f-137">First, the code using [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>  
  
```  
#define TranslateAccelerator  TranslateAcceleratorW  
```  
  
 <span data-ttu-id="2630f-138">Por lo que debe asegurarse de definir un `TranslateAccelerator` método y no un `TranslateAcceleratorW` método.</span><span class="sxs-lookup"><span data-stu-id="2630f-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>  
  
 <span data-ttu-id="2630f-139">De forma similar, hay el winuser.h MSG no administrado y los recursos administrados `Microsoft::Win32::MSG` struct.</span><span class="sxs-lookup"><span data-stu-id="2630f-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span>  <span data-ttu-id="2630f-140">Puede eliminar la ambigüedad entre los dos mediante la [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` operador.</span><span class="sxs-lookup"><span data-stu-id="2630f-140">You can disambiguate between the two using the [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` operator.</span></span>  
  
```  
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
    ModifierKeys modifiers) override   
{  
    ::MSG m = ConvertMessage(msg);  
```  
  
 <span data-ttu-id="2630f-141">Los mensajes tienen los mismos datos, pero a veces resulta más fácil trabajar con la definición no administrada, por lo que en este ejemplo puede definir la rutina de conversión evidente:</span><span class="sxs-lookup"><span data-stu-id="2630f-141">Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:</span></span>  
  
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
  
 <span data-ttu-id="2630f-142">Volver a `TranslateAccelerator`.</span><span class="sxs-lookup"><span data-stu-id="2630f-142">Back to `TranslateAccelerator`.</span></span>  <span data-ttu-id="2630f-143">El principio básico consiste en llamar a la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] función `IsDialogMessage` para hacer el trabajo como sea posible, pero `IsDialogMessage` no tiene acceso a ningún sitio fuera del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2630f-143">The basic principle is to call the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="2630f-144">Cuando se ejecuta una pestaña de usuario en el cuadro de diálogo, al desplazarse más allá del último control en el cuadro de diálogo, debe establecer el foco en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] parte mediante una llamada a `IKeyboardInputSite::OnNoMoreStops`.</span><span class="sxs-lookup"><span data-stu-id="2630f-144">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>  
  
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
  
 <span data-ttu-id="2630f-145">Por último, llame a `IsDialogMessage`.</span><span class="sxs-lookup"><span data-stu-id="2630f-145">Finally, call `IsDialogMessage`.</span></span>  <span data-ttu-id="2630f-146">Pero una de las responsabilidades de un `TranslateAccelerator` indica el método [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para administrar la pulsación de tecla o no.</span><span class="sxs-lookup"><span data-stu-id="2630f-146">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="2630f-147">Si no se administró, el evento de entrada puede tunelizar y propagarse a través del resto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2630f-147">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="2630f-148">En este caso, va a exponer una anomalía de administración de mensajes del teclado y la naturaleza de la arquitectura de entrada en [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2630f-148">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span></span> <span data-ttu-id="2630f-149">Por desgracia, `IsDialogMessage` no devuelve de ninguna manera si administra una pulsación de tecla determinada.</span><span class="sxs-lookup"><span data-stu-id="2630f-149">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span>  <span data-ttu-id="2630f-150">Peor aún, llamará `DispatchMessage()` las pulsaciones de teclas no debería administrar!</span><span class="sxs-lookup"><span data-stu-id="2630f-150">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="2630f-151">Por lo que tendrá que realizar ingeniería inversa `IsDialogMessage`y se invoca solo para las claves que se sabe que va a controlar:</span><span class="sxs-lookup"><span data-stu-id="2630f-151">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>  
  
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
  
### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="2630f-152">Invalidar el método TabInto para permitir las tabulaciones</span><span class="sxs-lookup"><span data-stu-id="2630f-152">Override TabInto Method to Support Tabbing</span></span>  
 <span data-ttu-id="2630f-153">Ahora que ha implementado `TranslateAccelerator`, un usuario puede tabulación para desplazarse por el cuadro de diálogo cuadro y saltar a la mayor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación.</span><span class="sxs-lookup"><span data-stu-id="2630f-153">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  <span data-ttu-id="2630f-154">Pero no se pestaña un usuario nuevo en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2630f-154">But a user cannot tab back into the dialog box.</span></span>  <span data-ttu-id="2630f-155">Para resolverlo, invalidar `TabInto`:</span><span class="sxs-lookup"><span data-stu-id="2630f-155">To solve that, you override `TabInto`:</span></span>  
  
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
  
 <span data-ttu-id="2630f-156">El `TraversalRequest` parámetro indica si la acción de la pestaña es un tab o MAYÚS+TAB.</span><span class="sxs-lookup"><span data-stu-id="2630f-156">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>  
  
### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="2630f-157">Invalidar el método OnMnemonic para admitir las teclas de acceso</span><span class="sxs-lookup"><span data-stu-id="2630f-157">Override OnMnemonic Method to Support Mnemonics</span></span>  
 <span data-ttu-id="2630f-158">Administración del teclado está casi ha finalizado, pero hay una falta algo: teclas de acceso no funcionan.</span><span class="sxs-lookup"><span data-stu-id="2630f-158">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span>  <span data-ttu-id="2630f-159">Si un usuario presiona alt-F, foco no salta a la "nombre:" cuadro de edición.</span><span class="sxs-lookup"><span data-stu-id="2630f-159">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="2630f-160">Por lo tanto, invalide el `OnMnemonic` método:</span><span class="sxs-lookup"><span data-stu-id="2630f-160">So, you override the `OnMnemonic` method:</span></span>  
  
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
  
 <span data-ttu-id="2630f-161">¿Por qué no llamar a `IsDialogMessage` aquí?</span><span class="sxs-lookup"><span data-stu-id="2630f-161">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="2630f-162">Tienen el mismo problema como antes, debe ser capaz de informar a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] código si el código controla la pulsación de tecla o no, y `IsDialogMessage` no es posible hacerlo.</span><span class="sxs-lookup"><span data-stu-id="2630f-162">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span>  <span data-ttu-id="2630f-163">También hay un problema de la segundo, el porque `IsDialogMessage` rechaza procesar la tecla de acceso si el HWND tiene el foco no está dentro del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="2630f-163">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>  
  
### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="2630f-164">Crear una instancia de clase derivada de la HwndHost</span><span class="sxs-lookup"><span data-stu-id="2630f-164">Instantiate the HwndHost Derived Class</span></span>  
 <span data-ttu-id="2630f-165">Por último, ahora que toda la compatibilidad de pestaña y la clave está en su lugar, puede colocar su <xref:System.Windows.Interop.HwndHost> en el mayor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación.</span><span class="sxs-lookup"><span data-stu-id="2630f-165">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  <span data-ttu-id="2630f-166">Si la aplicación principal está escrita en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], la manera más fácil de colocarla en el lugar correcto es dejar vacío <xref:System.Windows.Controls.Border> elemento donde desea colocar el <xref:System.Windows.Interop.HwndHost>.</span><span class="sxs-lookup"><span data-stu-id="2630f-166">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span>  <span data-ttu-id="2630f-167">Aquí se crea un <xref:System.Windows.Controls.Border> denominado `insertHwndHostHere`:</span><span class="sxs-lookup"><span data-stu-id="2630f-167">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>  
  
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
  
 <span data-ttu-id="2630f-168">A continuación, lo único que queda es buscar un buen punto de secuencia de código para crear instancias de la <xref:System.Windows.Interop.HwndHost> y conectarlo a la <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="2630f-168">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span>  <span data-ttu-id="2630f-169">En este ejemplo, se coloca dentro del constructor para la <xref:System.Windows.Window> clase derivada:</span><span class="sxs-lookup"><span data-stu-id="2630f-169">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>  
  
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
  
 <span data-ttu-id="2630f-170">Que proporciona:</span><span class="sxs-lookup"><span data-stu-id="2630f-170">Which gives you:</span></span>  
  
 <span data-ttu-id="2630f-171">![Captura de pantalla de aplicación de WPF](../../../../docs/framework/wpf/advanced/media/interoparch09.PNG "InteropArch09")</span><span class="sxs-lookup"><span data-stu-id="2630f-171">![WPF application screen shot](../../../../docs/framework/wpf/advanced/media/interoparch09.PNG "InteropArch09")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2630f-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="2630f-172">See Also</span></span>  
 [<span data-ttu-id="2630f-173">Interoperabilidad de WPF y Win32</span><span class="sxs-lookup"><span data-stu-id="2630f-173">WPF and Win32 Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
