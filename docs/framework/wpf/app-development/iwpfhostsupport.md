---
title: "IWpfHostSupport | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IWpfHostSupport (interfaz)"
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# IWpfHostSupport
Las aplicaciones que hospedan contenido de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] mediante PresentationHost.exe implementan esta interfaz para proporcionar un punto de integración entre el host y PresentationHost.exe.  
  
## Comentarios  
 Las aplicaciones de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] como los exploradores web pueden hospedar contenido de [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)], incluidas las [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] y XAML dinámico.  Para hospedar contenido de [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)], las aplicaciones de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] crean una instancia del [control WebBrowser](http://go.microsoft.com/fwlink/?LinkId=97911).  Para hospedarse, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] crea una instancia de PresentationHost.exe, que proporciona el contenido de [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] hospedado al host para mostrarlo en el [control WebBrowser](http://go.microsoft.com/fwlink/?LinkId=97911).  
  
 La integración habilitada por `IWpfHostSupport` permite a PresentationHost.exe:  
  
-   Detectar y registrar los dispositivos de entrada sin formato \(dispositivos de interfaz de usuario\) en los que la aplicación host está interesada.  
  
-   Recibir los mensajes de entrada de los dispositivos de entrada sin formato registrados y reenvíe los mensajes adecuados a la aplicación host.  
  
-   Consultar la aplicación host para obtener las interfaces de usuario personalizadas de progreso y errores.  
  
> [!NOTE]
>  Esta API solo es compatible y está diseñada para su uso en el equipo cliente local  
  
## Members  
  
|Miembro|Descripción|  
|-------------|-----------------|  
|[GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|Permite que PresentationHost.exe detecte los dispositivos de entrada sin formato \(dispositivos de interfaz de usuario\) en los que la aplicación host está interesada.|  
|[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|Lo llama PresentationHost.exe cada vez que se recibe un mensaje, a menos que se devuelva E\_NOTIMPL.|  
|[GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)|De manera predeterminada, PresentationHost.exe proporciona sus propias interfaces de progreso de la implementación y de errores de implementación que se muestran cuando se implementa el contenido de WPF.|