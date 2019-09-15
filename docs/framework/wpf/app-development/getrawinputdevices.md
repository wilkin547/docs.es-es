---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 4fc7a5021f9f8d9e6badcd3e13266fb8f4bfe7a4
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991756"
---
# <a name="getrawinputdevices"></a>GetRawInputDevices
Permite que PresentationHost.exe detecte los dispositivos de entrada sin formato (dispositivos de interfaz humana) en los que está interesada la aplicación host.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppEnum`  
  
 enuncia Un puntero a un [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) para enumerar los dispositivos de entrada sin formato.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 HRESULT:  
  
 PresentationHost. exe solo usará S_OK- [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) si se devuelve S_OK.  
  
 E_NOTIMPL  
  
## <a name="remarks"></a>Comentarios  
 Los dispositivos de entrada sin formato constituyen el conjunto de dispositivos de entrada que incluye teclados, mouse y otros dispositivos menos tradicionales, como los de control remoto.  
  
 Una vez que se ha recuperado la lista de dispositivos de entrada sin formato, PresentationHost.exe se registra con los dispositivos para recibir mensajes de notificación WM_INPUT.  
  
## <a name="see-also"></a>Vea también

- [GetRawInputDeviceList](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [FilterInputMessage](filterinputmessage.md)
