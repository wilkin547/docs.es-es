---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: e3edd7f7080562d03453898dba7a9326561803b5
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124200"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
Las aplicaciones que hospedan [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenido mediante PresentationHost. exe implementan esta interfaz para proporcionar un punto de integración entre el host y PresentationHost. exe.  
  
## <a name="remarks"></a>Observaciones  
 Las aplicaciones Win32, como los exploradores Web, pueden hospedar contenido de WPF, incluidas las aplicaciones de explorador XAML (XBAP) y XAML dinámico. Para hospedar contenido de WPF, las aplicaciones Win32 crean una instancia del [control WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)). Para hospedarse, WPF crea una instancia de PresentationHost. exe, que proporciona el contenido de WPF hospedado al host para su presentación en el [control WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).  
  
 La integración habilitada por `IWpfHostSupport` permite a PresentationHost. exe:  
  
- Detecte y registre con los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesado la aplicación host.  
  
- Recibir mensajes de entrada de los dispositivos de entrada sin procesar registrados y reenviar los mensajes adecuados a la aplicación host.  
  
- Consulte la aplicación host para obtener interfaces de usuario de progreso y error personalizadas.  
  
> [!NOTE]
> Esta API solo está destinada y es compatible con el equipo cliente local  
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|Permite que PresentationHost.exe detecte los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesada la aplicación host.|  
|[FilterInputMessage](filterinputmessage.md)|Lo llama PresentationHost.exe cada vez que se recibe un mensaje a menos que se devuelva E_NOTIMPL.|  
|[GetCustomUI](getcustomui.md)|De forma predeterminada, PresentationHost. exe proporciona sus propias interfaces de usuario de error de implementación y progreso de implementación que se muestran cuando se implementa el contenido de WPF.|
