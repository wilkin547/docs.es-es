---
title: "FilterInputMessage | Microsoft Docs"
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
  - "FilterInputMessage (método)"
  - "entrada sin formato [WPF]"
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# FilterInputMessage
Lo llama PresentationHost.exe cada vez que se recibe un mensaje a menos que se devuelva E\_NOTIMPL.  
  
## Sintaxis  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### Parámetros  
 `pMsg`  
  
 \[in\] Mensaje WM\_INPUT enviado a la ventana que obtiene la entrada sin formato.  
  
## Valor de propiedad y valor devuelto  
 HRESULT:  
  
 S\_OK: el filtro no procesó el mensaje y se puede producir un procesamiento adicional.  
  
 S\_FALSE: el filtro procesó este mensaje y no debe realizarse ningún procesamiento adicional.  
  
 E\_NOTIMPL: si se devuelve este valor, no se vuelve a llamar a [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).  Esto se podría devolver desde una aplicación host que solo esté interesada en proporcionar interfaces de usuario personalizadas de progreso y error a PresentationHost.exe y que no esté interesada en que se reenvíen mensajes de entrada sin formato desde PresentationHost.exe.  
  
## Comentarios  
 PresentationHost.exe es el destino de varios dispositivos de entrada sin formato, incluidos controles remotos, mouse y teclado.  A veces, el comportamiento de la aplicación host depende de entradas que de otra forma serían consumidas por PresentationHost.exe.  Por ejemplo, una aplicación host puede depender de recibir ciertos mensajes de entrada para determinar si se debe o no mostrar determinados elementos de la interfaz de usuario.  
  
 Para que la aplicación host pueda recibir los mensajes de entrada necesarios para proporcionar estos comportamientos, PresentationHost.exe reenvía los mensajes de entrada sin formato adecuados a la aplicación hospedada mediante una llamada a [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).  
  
 Para recibir los mensajes de entrada sin formato, la aplicación hospedada se registra en el conjunto de dispositivos de entrada sin formato \(dispositivos de interfaz humana\) devueltos por [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).  
  
## Vea también  
 [Notificación WM\_INPUT](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)