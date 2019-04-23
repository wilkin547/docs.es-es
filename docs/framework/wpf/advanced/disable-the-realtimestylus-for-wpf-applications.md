---
title: Deshabilitar RealTimeStylus para las aplicaciones de WPF
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: e44b71ac5af64ab3a6cb008db71e5a8881592e91
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124688"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="cebc7-102">Deshabilitar RealTimeStylus para las aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="cebc7-102">Disable the RealTimeStylus for WPF Applications</span></span>
<span data-ttu-id="cebc7-103">Windows Presentation Foundation (WPF) incorpora compatibilidad para procesar la entrada táctil de Windows 7. Incluye el soporte técnico a través de la entrada de lápiz en tiempo real de la plataforma de Tablet PC como <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, y <xref:System.Windows.UIElement.OnStylusMove%2A> eventos.</span><span class="sxs-lookup"><span data-stu-id="cebc7-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="cebc7-104">Windows 7 también proporciona la entrada de multitoque como mensajes de ventana de Win32 WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="cebc7-104">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="cebc7-105">Estas dos API son mutuamente excluyentes en el mismo HWND.</span><span class="sxs-lookup"><span data-stu-id="cebc7-105">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="cebc7-106">Entrada táctil habilitación a través de la plataforma de Tablet PC (el valor predeterminado para las aplicaciones de WPF) en los mensajes WM_TOUCH deshabilita.</span><span class="sxs-lookup"><span data-stu-id="cebc7-106">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="cebc7-107">Como resultado, para usar WM_TOUCH para recibir mensajes táctiles de una ventana de WPF, debe deshabilitar la compatibilidad con el lápiz integradas en WPF.</span><span class="sxs-lookup"><span data-stu-id="cebc7-107">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="cebc7-108">Esto es aplicable en un escenario como una ventana de WPF hospeda un componente que usa WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="cebc7-108">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="cebc7-109">Para deshabilitar la escucha de WPF a la entrada de lápiz, quite cualquier compatibilidad de la tableta agregada por la ventana de WPF.</span><span class="sxs-lookup"><span data-stu-id="cebc7-109">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cebc7-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cebc7-110">Example</span></span>  
 <span data-ttu-id="cebc7-111">El código de ejemplo siguiente muestra cómo quitar la compatibilidad de plataforma de Tablet PC de forma predeterminada mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="cebc7-111">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="cebc7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cebc7-112">See also</span></span>

- [<span data-ttu-id="cebc7-113">Interceptar entradas del lápiz óptico</span><span class="sxs-lookup"><span data-stu-id="cebc7-113">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)
