---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 18564e0de8f88e89f8fb71d28ee3bfeccceea4ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507569"
---
# <a name="getrawinputdevices"></a>GetRawInputDevices
Permite que PresentationHost.exe detecte los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesada la aplicación host.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppEnum`  
  
 [out] Un puntero a un [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) para enumerar los dispositivos de entrada sin formato.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 HRESULT:  
  
 S_OK: [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) solo se usará PresentationHost.exe si se devuelve S_OK.  
  
 E_NOTIMPL  
  
## <a name="remarks"></a>Comentarios  
 Los dispositivos de entrada sin formato constituyen el conjunto de dispositivos de entrada que incluye teclados, mouse y otros dispositivos menos tradicionales, como los de control remoto.  
  
 Una vez que se ha recuperado la lista de dispositivos de entrada sin formato, PresentationHost.exe se registra con los dispositivos para recibir mensajes de notificación WM_INPUT.  
  
## <a name="see-also"></a>Vea también
- [GetRawInputDeviceList](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)
