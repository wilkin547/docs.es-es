---
description: 'Más información acerca de: ICLRRuntimeInfo:: LoadErrorString ((método)'
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
ms.openlocfilehash: 0523b5b89072db50c83c52065c22e9df7167a027
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785073"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a>ICLRRuntimeInfo::LoadErrorString (Método)

Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.  
  
 Este método sustituye a las siguientes funciones:  
  
- [Loadstringrc (](loadstringrc-function.md)  
  
- [Loadstringrcex (](loadstringrcex-function.md)  
  
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

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRRuntimeInfo (Interfaz)](iclrruntimeinfo-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
