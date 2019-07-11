---
title: ICLRRuntimeInfo::GetDefaultStartupFlags (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aeb4c9935d5e9e4063497dd56276edfe6e62752a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765587"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>ICLRRuntimeInfo::GetDefaultStartupFlags (Método)
Obtiene las marcas de inicio y el archivo de configuración de host que se usará para iniciar el tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pdwStartupFlags`  
 [out] Un puntero a las marcas de inicio del host que están establecidas actualmente.  
  
 `pwzHostConfigFile`  
 [out] Un puntero a la ruta del directorio del archivo de configuración de host actual.  
  
 `pcchHostConfigFile`  
 [in, out] En la entrada, el tamaño de `pwzHostConfigFile`, para evitar saturaciones de búfer. Si `pwzHostConfigFile` es null, el método devuelve el tamaño necesario de `pwzHostConfigFile` para la asignación previa.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos, así como los errores HRESULT que indican un error del método.  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
  
## <a name="remarks"></a>Comentarios  
 Este método devuelve los valores de marca predeterminada (`STARTUP_CONCURRENT_GC` y `NULL`), o los valores proporcionados por una llamada anterior a la [SetDefaultStartupFlags (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), o los valores establecidos por cualquiera de los `CorBind*` métodos si están enlazados a este entorno de ejecución.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRRuntimeInfo (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
