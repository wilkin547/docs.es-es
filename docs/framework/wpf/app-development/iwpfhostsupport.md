---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 074167111b78edc517dda019465260d0acd54737
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376018"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
Las aplicaciones que hospedan [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenido a través de PresentationHost.exe implementan esta interfaz para proporcionar un punto de integración entre el host y PresentationHost.exe.  
  
## <a name="remarks"></a>Comentarios  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] pueden hospedar las aplicaciones como los exploradores Web [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] de contenido, incluidos [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] y dinamizarlos en XAML. Al host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] contenido, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] las aplicaciones crean una instancia de la [control WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911). Al hospedarse, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] crea una instancia de PresentationHost.exe, que proporciona hospedado [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] contenido en el host para su presentación en el [control WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).  
  
 La integración habilitada de forma `IWpfHostSupport` permite que PresentationHost.exe:  
  
-   Detectar y registrar con los dispositivos de entrada sin formato (dispositivos de interfaz humana) que está interesada la aplicación host.  
  
-   Recibir mensajes de entrada de los dispositivos registrados de entrada sin procesar y reenviar los mensajes adecuados a la aplicación host.  
  
-   Consultar la aplicación host para interfaces de usuario personalizadas de progreso y error.  
  
> [!NOTE]
>  Esta API solo está destinada y es compatible con el equipo cliente local  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|Permite que PresentationHost.exe detecte los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesada la aplicación host.|  
|[FilterInputMessage](filterinputmessage.md)|Lo llama PresentationHost.exe cada vez que se recibe un mensaje a menos que se devuelva E_NOTIMPL.|  
|[GetCustomUI](getcustomui.md)|De forma predeterminada, PresentationHost.exe proporciona su propio progreso de la implementación y el error de implementación de interfaces de usuario que se muestran cuando se implementa contenido de WPF.|
