---
title: Deshabilitar el RealTimeStylus
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: c2500b494f76c85e4b23823a44a180d85d5092ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186086"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Deshabilitar RealTimeStylus para las aplicaciones de WPF

Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) tiene compatibilidad integrada para procesar la entrada táctil de Windows 7. El soporte viene a través de la <xref:System.Windows.UIElement.OnStylusDown%2A>entrada <xref:System.Windows.UIElement.OnStylusUp%2A>de <xref:System.Windows.UIElement.OnStylusMove%2A> lápiz en tiempo real de la plataforma de la tableta como , , y eventos. Windows 7 también proporciona entrada multitáctil como mensajes de ventana de WM_TOUCH Win32. Estas dos API se excluyen mutuamente en el mismo HWND. Habilitar la entrada táctil a través de la plataforma de tableta (el valor predeterminado para las aplicaciones WPF) deshabilita los mensajes WM_TOUCH. Como resultado, para usar WM_TOUCH para recibir mensajes táctiles desde una ventana WPFWPF, debe deshabilitar la compatibilidad integrada con el lápiz en WPFWPF. Esto es aplicable en un escenario como una ventana WPFWPF que hospeda un componente que usa WM_TOUCH.  
  
 Para deshabilitar WPFWPF escuchar la entrada de lápiz, quite cualquier compatibilidad con tabletas agregada por la ventana WPFWPF.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código de ejemplo muestra cómo quitar la compatibilidad predeterminada de la plataforma de tableta mediante la reflexión.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Interceptar entradas del lápiz óptico](intercepting-input-from-the-stylus.md)
