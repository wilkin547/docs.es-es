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
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Deshabilitar RealTimeStylus para las aplicaciones de WPF

Windows Presentation Foundation (WPF) tiene compatibilidad integrada para procesar la entrada táctil de Windows 7. La compatibilidad se realiza a través de la entrada del lápiz en tiempo real de la plataforma de tableta como <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>y <xref:System.Windows.UIElement.OnStylusMove%2A> eventos. Windows 7 también proporciona entrada multitáctil como mensajes de ventana de WM_TOUCH Win32. Estas dos API se excluyen mutuamente en el mismo HWND. La habilitación de la entrada táctil a través de la plataforma de tableta (el valor predeterminado para las aplicaciones WPF) deshabilita los mensajes de WM_TOUCH. Como resultado, para usar WM_TOUCH para recibir mensajes táctiles de una ventana de WPF, debe deshabilitar la compatibilidad integrada con el lápiz óptico en WPF. Esto es aplicable en un escenario como una ventana de WPF que hospeda un componente que usa WM_TOUCH.  
  
 Para deshabilitar la escucha de WPF en la entrada del lápiz, quite cualquier compatibilidad de Tablet PC agregada por la ventana de WPF.  
  
## <a name="example"></a>Ejemplo  
 En el código de ejemplo siguiente se muestra cómo quitar la compatibilidad con la plataforma de tableta predeterminada mediante la reflexión.  
  
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
