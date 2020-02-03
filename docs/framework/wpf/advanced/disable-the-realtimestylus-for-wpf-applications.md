---
title: Deshabilitar RealTimeStylus
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: 74145c32af7e9ebbc774a0301e205aa1eb1539b3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737938"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="29871-102">Deshabilitar RealTimeStylus para las aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="29871-102">Disable the RealTimeStylus for WPF Applications</span></span>

<span data-ttu-id="29871-103">Windows Presentation Foundation (WPF) tiene compatibilidad integrada para procesar la entrada táctil de Windows 7.</span><span class="sxs-lookup"><span data-stu-id="29871-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.</span></span> <span data-ttu-id="29871-104">La compatibilidad se realiza a través de la entrada del lápiz en tiempo real de la plataforma de tableta como <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>y <xref:System.Windows.UIElement.OnStylusMove%2A> eventos.</span><span class="sxs-lookup"><span data-stu-id="29871-104">The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="29871-105">Windows 7 también proporciona entrada multitáctil como mensajes de ventana de WM_TOUCH Win32.</span><span class="sxs-lookup"><span data-stu-id="29871-105">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="29871-106">Estas dos API se excluyen mutuamente en el mismo HWND.</span><span class="sxs-lookup"><span data-stu-id="29871-106">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="29871-107">La habilitación de la entrada táctil a través de la plataforma de tableta (el valor predeterminado para las aplicaciones WPF) deshabilita los mensajes de WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="29871-107">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="29871-108">Como resultado, para usar WM_TOUCH para recibir mensajes táctiles de una ventana de WPF, debe deshabilitar la compatibilidad integrada con el lápiz óptico en WPF.</span><span class="sxs-lookup"><span data-stu-id="29871-108">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="29871-109">Esto es aplicable en un escenario como una ventana de WPF que hospeda un componente que usa WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="29871-109">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="29871-110">Para deshabilitar la escucha de WPF en la entrada del lápiz, quite cualquier compatibilidad de Tablet PC agregada por la ventana de WPF.</span><span class="sxs-lookup"><span data-stu-id="29871-110">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29871-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29871-111">Example</span></span>  
 <span data-ttu-id="29871-112">En el código de ejemplo siguiente se muestra cómo quitar la compatibilidad con la plataforma de tableta predeterminada mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="29871-112">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="29871-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29871-113">See also</span></span>

- [<span data-ttu-id="29871-114">Interceptar entradas del lápiz óptico</span><span class="sxs-lookup"><span data-stu-id="29871-114">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)
