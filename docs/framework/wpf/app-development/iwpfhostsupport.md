---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 994e5146e9cf49a9b31396d0b51e7be83bbb3cfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964781"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
Las aplicaciones que [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] hospedan contenido a través de PresentationHost. exe implementan esta interfaz para proporcionar un punto de integración entre el host y PresentationHost. exe.  
  
## <a name="remarks"></a>Comentarios  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]las aplicaciones como los exploradores Web pueden [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] hospedar contenido [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] , incluido y código XAML dinámico. Para hospedar [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] contenido [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] , las aplicaciones crean una instancia del [control WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911). Para hospedar, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] crea una instancia de PresentationHost. exe, que proporciona el contenido [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] hospedado al host para su presentación en el [control WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).  
  
 La integración habilitada `IWpfHostSupport` por permite a PresentationHost. exe:  
  
- Detecte y registre con los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesado la aplicación host.  
  
- Recibir mensajes de entrada de los dispositivos de entrada sin procesar registrados y reenviar los mensajes adecuados a la aplicación host.  
  
- Consulte la aplicación host para obtener interfaces de usuario de progreso y error personalizadas.  
  
> [!NOTE]
> Esta API solo está destinada y es compatible con el equipo cliente local  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|Permite que PresentationHost.exe detecte los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesada la aplicación host.|  
|[FilterInputMessage](filterinputmessage.md)|Lo llama PresentationHost.exe cada vez que se recibe un mensaje a menos que se devuelva E_NOTIMPL.|  
|[GetCustomUI](getcustomui.md)|De forma predeterminada, PresentationHost. exe proporciona sus propias interfaces de usuario de error de implementación y progreso de implementación que se muestran cuando se implementa el contenido de WPF.|
