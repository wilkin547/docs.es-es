---
title: "Deshabilitar RealTimeStylus para las aplicaciones de WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# Deshabilitar RealTimeStylus para las aplicaciones de WPF
Windows Presentation Foundation \(WPF\) dispone de compatibilidad integrada para procesar la entrada táctil de Windows 7. La compatibilidad procede de la entrada del lápiz en tiempo real de la plataforma de tableta en forma de eventos <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A> y <xref:System.Windows.UIElement.OnStylusUp%2A>.  Windows 7 también proporciona la entrada de varios toques como mensajes de ventana de Win32 WM\_TOUCH.  Estas dos API son mutuamente excluyentes en el mismo HWND.  Al habilitar la entrada táctil a través de la plataforma de tableta \(el valor predeterminado para las aplicaciones WPF\), se deshabilitan los mensajes de WM\_TOUCH.  En consecuencia, para usar WM\_TOUCH para recibir los mensajes táctiles en una ventana de WPF, debe deshabilitar la compatibilidad del lápiz integrada en WPF.  Esto es aplicable en un escenario como una ventana de WPF que hospeda un componente que usa WM\_TOUCH.  
  
 Para deshabilitar la escucha de WPF a la entrada del lápiz, quite cualquier compatibilidad de la tableta agregada por la ventana de WPF.  
  
## Ejemplo  
 El siguiente código de ejemplo muestra cómo quitar la compatibilidad de plataforma de tableta predeterminada mediante la reflexión.  
  
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
  
## Vea también  
 [Interceptar entradas del lápiz óptico](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)