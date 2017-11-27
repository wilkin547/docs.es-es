---
title: Deshabilitar RealTimeStylus para las aplicaciones de WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 01a4d8f6d98eb341021442d9b7964816dd673374
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="1b73e-102">Deshabilitar RealTimeStylus para las aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="1b73e-102">Disable the RealTimeStylus for WPF Applications</span></span>
<span data-ttu-id="1b73e-103">Windows Presentation Foundation (WPF) incorpora compatibilidad para procesar la entrada táctil de Windows 7. La compatibilidad procede a través de la entrada de lápiz en tiempo real de la plataforma de tableta como <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, y <xref:System.Windows.UIElement.OnStylusMove%2A> eventos.</span><span class="sxs-lookup"><span data-stu-id="1b73e-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="1b73e-104">Windows 7 también proporciona la entrada de multitoque como mensajes de ventana de Win32 WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="1b73e-104">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="1b73e-105">Estas dos API son mutuamente excluyentes en el mismo HWND.</span><span class="sxs-lookup"><span data-stu-id="1b73e-105">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="1b73e-106">Habilitar táctil a través de la plataforma de tableta (el valor predeterminado para las aplicaciones WPF) deshabilita WM_TOUCH los mensajes de entrada.</span><span class="sxs-lookup"><span data-stu-id="1b73e-106">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="1b73e-107">Como resultado, para usar WM_TOUCH para recibir mensajes de entrada táctil de una ventana de WPF, debe deshabilitar la compatibilidad con el lápiz integradas en WPF.</span><span class="sxs-lookup"><span data-stu-id="1b73e-107">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="1b73e-108">Esto es aplicable en un escenario como una ventana de WPF que hospeda un componente que usa WM_TOUCH.</span><span class="sxs-lookup"><span data-stu-id="1b73e-108">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="1b73e-109">Para deshabilitar la escucha de WPF a la entrada de lápiz, quite cualquier compatibilidad de tableta agregada por la ventana de WPF.</span><span class="sxs-lookup"><span data-stu-id="1b73e-109">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b73e-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b73e-110">Example</span></span>  
 <span data-ttu-id="1b73e-111">El código de ejemplo siguiente muestra cómo quitar la compatibilidad de plataforma de tableta predeterminada mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="1b73e-111">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1b73e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b73e-112">See Also</span></span>  
 [<span data-ttu-id="1b73e-113">Interceptar entradas del lápiz óptico</span><span class="sxs-lookup"><span data-stu-id="1b73e-113">Intercepting Input from the Stylus</span></span>](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)
