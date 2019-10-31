---
title: ICLRRuntimeInfo::LoadErrorString (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
ms.openlocfilehash: 20f2041599e85b8df20a7a9cf44680da9f17244e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195928"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a>ICLRRuntimeInfo::LoadErrorString (Método)
Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.  
  
 Este método sustituye a las siguientes funciones:  
  
- [Loadstringrc (](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
- [Loadstringrcex (](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a>Parámetros  
 `iResourceID`  
 de HRESULT que se va a traducir.  
  
 `pwzBuffer`  
 enuncia Cadena de mensaje asociada al HRESULT especificado.  
  
 `pcchBuffer`  
 [in, out] Tamaño de `pwzbuffer` para evitar las saturaciones del búfer. Si `pwzbuffer` es null, `pcchBuffer` proporciona el tamaño esperado de `pwzbuffer` para permitir la asignación previa.  
  
 `iLocaleID`  
 de Identificador de referencia cultural. Para utilizar la referencia cultural predeterminada, debe especificar-1.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`pcchBuffer` es null.|  
|E_INVALIDARG|`pwzBuffer` es null.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRRuntimeInfo (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
