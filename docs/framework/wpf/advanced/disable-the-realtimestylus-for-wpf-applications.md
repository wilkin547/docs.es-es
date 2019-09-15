---
title: Deshabilitar RealTimeStylus para las aplicaciones de WPF
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: acae177e1c49a6a1161bcf48f8e2e8ac1bfe13b8
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991838"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="71b04-102">Deshabilitar RealTimeStylus para las aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="71b04-102">Disable the RealTimeStylus for WPF Applications</span></span>
<span data-ttu-id="71b04-103">Windows Presentation Foundation (WPF) tiene compatibilidad integrada para procesar la entrada táctil de Windows 7.</span><span class="sxs-lookup"><span data-stu-id="71b04-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.</span></span> <span data-ttu-id="71b04-104">La compatibilidad se realiza a través de la entrada del lápiz en tiempo real <xref:System.Windows.UIElement.OnStylusDown%2A>de <xref:System.Windows.UIElement.OnStylusUp%2A>la plataforma <xref:System.Windows.UIElement.OnStylusMove%2A> de tableta como eventos, y.</span><span class="sxs-lookup"><span data-stu-id="71b04-104">The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="71b04-105">Windows 7 también proporciona una entrada multitáctil como mensajes de ventana WM_TOUCH de Win32.</span><span class="sxs-lookup"><span data-stu-id="71b04-105">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="71b04-106">Estas dos API se excluyen mutuamente en el mismo HWND.</span><span class="sxs-lookup"><span data-stu-id="71b04-106">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="71b04-107">La habilitación de la entrada táctil a través de la plataforma de tableta (el valor predeterminado para las aplicaciones WPF) deshabilita los mensajes WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="71b04-107">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="71b04-108">Como resultado, para usar WM_TOUCH para recibir mensajes táctiles de una ventana de WPF, debe deshabilitar la compatibilidad integrada con el lápiz óptico en WPF.</span><span class="sxs-lookup"><span data-stu-id="71b04-108">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="71b04-109">Esto es aplicable en un escenario como una ventana de WPF que hospeda un componente que usa WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="71b04-109">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="71b04-110">Para deshabilitar la escucha de WPF en la entrada del lápiz, quite cualquier compatibilidad de Tablet PC agregada por la ventana de WPF.</span><span class="sxs-lookup"><span data-stu-id="71b04-110">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71b04-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="71b04-111">Example</span></span>  
 <span data-ttu-id="71b04-112">En el código de ejemplo siguiente se muestra cómo quitar la compatibilidad con la plataforma de tableta predeterminada mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="71b04-112">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
```csharp  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.    
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {     
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }                  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="71b04-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="71b04-113">See also</span></span>

- [<span data-ttu-id="71b04-114">Interceptar entradas del lápiz óptico</span><span class="sxs-lookup"><span data-stu-id="71b04-114">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)
