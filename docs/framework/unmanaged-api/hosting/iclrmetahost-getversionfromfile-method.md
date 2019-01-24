---
title: ICLRMetaHost::GetVersionFromFile (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83bd2f3b0c1d58528624ac730756fb3bcdf4ba47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744848"
---
# <a name="iclrmetahostgetversionfromfile-method"></a>ICLRMetaHost::GetVersionFromFile (Método)
Obtiene .NET Framework versión de compilación original un ensamblado (almacenada en los metadatos), dada su ruta de acceso de archivo. Este método reemplaza el [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pwzFilePath`  
 [in] La ruta de acceso completa del ensamblado.  
  
 `pwzbuffer`  
 [out] La versión de compilación de .NET Framework almacenada en los metadatos, en el formato "v*A*. *B*[. *X*] ". *Un*, *B*, y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación. La longitud de esta cadena está limitada a MAX_PATH.  
  
> [!NOTE]
>  Esta salida coincide con el nombre del directorio para la versión de .NET Framework, tal y como aparece bajo C:\Windows\Microsoft.NET\Framework.  
  
 Los valores de ejemplo son "v1.0.3705", "v1.1.4322", "v2.0.50727" y "v4.0. *X*", donde *X* depende del número de compilación instalado. Tenga en cuenta que el prefijo "v" es necesario.  
  
 `pcchBuffer`  
 [in, out] El tamaño de `pwzbuffer` para evitar saturaciones de búfer.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`pwzbuffer` o `pcchBuffer` es null.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|El búfer es demasiado pequeño.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICLRMetaHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
