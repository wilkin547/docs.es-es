---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 91a29233d12a842a64b7d3dd497312f6dc6742ca
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423652"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
Las aplicaciones que hospedan [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenido mediante PresentationHost. exe implementan esta interfaz para proporcionar un punto de integración entre el host y PresentationHost. exe.  
  
## <a name="remarks"></a>Comentarios  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] aplicaciones como los exploradores Web pueden hospedar contenido de WPF, incluidas las aplicaciones de explorador XAML (XBAP) y XAML dinámico. Para hospedar contenido de WPF, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] aplicaciones crean una instancia del [control WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911). Para hospedarse, WPF crea una instancia de PresentationHost. exe, que proporciona el contenido de WPF hospedado al host para su presentación en el [control WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).  
  
 La integración habilitada por `IWpfHostSupport` permite a PresentationHost. exe:  
  
- Detecte y registre con los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesado la aplicación host.  
  
- Recibir mensajes de entrada de los dispositivos de entrada sin procesar registrados y reenviar los mensajes adecuados a la aplicación host.  
  
- Consulte la aplicación host para obtener interfaces de usuario de progreso y error personalizadas.  
  
> [!NOTE]
> Esta API solo está destinada y es compatible con el equipo cliente local  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|Permite que PresentationHost.exe detecte los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesada la aplicación host.|  
|[FilterInputMessage](filterinputmessage.md)|Lo llama PresentationHost.exe cada vez que se recibe un mensaje a menos que se devuelva E_NOTIMPL.|  
|[GetCustomUI](getcustomui.md)|De forma predeterminada, PresentationHost. exe proporciona sus propias interfaces de usuario de error de implementación y progreso de implementación que se muestran cuando se implementa el contenido de WPF.|
