---
title: Deshabilitar RealTimeStylus para las aplicaciones de WPF
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: e44b71ac5af64ab3a6cb008db71e5a8881592e91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962495"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Deshabilitar RealTimeStylus para las aplicaciones de WPF
Windows Presentation Foundation (WPF) incorpora compatibilidad para procesar la entrada táctil de Windows 7. Incluye el soporte técnico a través de la entrada de lápiz en tiempo real de la plataforma de Tablet PC como <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, y <xref:System.Windows.UIElement.OnStylusMove%2A> eventos. Windows 7 también proporciona la entrada de multitoque como mensajes de ventana de Win32 WM_TOUCH. Estas dos API son mutuamente excluyentes en el mismo HWND. Entrada táctil habilitación a través de la plataforma de Tablet PC (el valor predeterminado para las aplicaciones de WPF) en los mensajes WM_TOUCH deshabilita. Como resultado, para usar WM_TOUCH para recibir mensajes táctiles de una ventana de WPF, debe deshabilitar la compatibilidad con el lápiz integradas en WPF. Esto es aplicable en un escenario como una ventana de WPF hospeda un componente que usa WM_TOUCH.  
  
 Para deshabilitar la escucha de WPF a la entrada de lápiz, quite cualquier compatibilidad de la tableta agregada por la ventana de WPF.  
  
## <a name="example"></a>Ejemplo  
 El código de ejemplo siguiente muestra cómo quitar la compatibilidad de plataforma de Tablet PC de forma predeterminada mediante la reflexión.  
  
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
  
## <a name="see-also"></a>Vea también

- [Interceptar entradas del lápiz óptico](intercepting-input-from-the-stylus.md)
