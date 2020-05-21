---
title: ICLRRuntimeInfo::GetRuntimeDirectory (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
ms.openlocfilehash: d744abf5c502e9b9510cf9fd6479149b6c2177cc
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762219"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a>ICLRRuntimeInfo::GetRuntimeDirectory (Método)
Obtiene el directorio de instalación del Common Language Runtime (CLR) asociado a esta interfaz.  
  
 Este método reemplaza la función [GetCORSystemDirectory (](getcorsystemdirectory-function.md) proporcionada en las versiones 2,0, 3,0 y 3,5 de .NET Framework.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzBuffer`  
 enuncia Devuelve el directorio de instalación de CLR. La ruta de instalación es completa; por ejemplo, "c:\Windows\Microsoft.NET\Framework\v1.0.3705 \\ ".  
  
 `pchBuffer`  
 [in, out] Especifica el tamaño de `pwzBuffer` para evitar las saturaciones del búfer. Si `pwzBuffer` es null, `pchBuffer` devuelve el tamaño requerido de `pwzBuffer` .  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`pwzBuffer` o `pchBuffer` es null.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICLRRuntimeInfo (Interfaz)](iclrruntimeinfo-interface.md)
- [Hospedar aplicaciones de WPF](index.md)
