---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28e97289eda5949e6d124426eb58105e2e3ad33e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a>ICLRAssemblyIdentityManager::GetBindingIdentityFromFile (Método)
Obtiene la identidad del ensamblado enlace de datos para el ensamblado en la ruta de acceso de archivo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pwzFilePath`  
 [in] La ruta de acceso al archivo que se debe evaluar.  
  
 `dwFlags`  
 [in] Un valor de la [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeración que indica el tipo de identidad de un ensamblado. Se proporciona para extensibilidad futura. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor admitido por common language runtime (CLR) versión 2.0.  
  
 `pwzBuffer`  
 [out] Un búfer que contiene los datos de identidad de ensamblado opaco.  
  
 `pcchBufferSize`  
 [entrada, salida] Un puntero al tamaño de `pwzBuffer`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se devolvió correctamente.|  
|E_INVALIDARG|Suministrado `pwzFilePath` es null.|  
|ERROR_INSUFFICIENT_BUFFER|El tamaño de `pwzBuffer` es demasiado pequeño.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada agotó el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 `GetBindingIdentityFromFile` Normalmente se llama dos veces. La primera llamada proporciona un valor null para `pwzBuffer`, y el método devuelve el tamaño adecuado en `pcchBufferSize`. La segunda llamada proporciona un búfer correctamente asignado y el método devuelve con los datos del búfer reales cuando se complete.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRAssemblyIdentityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [ICLRHostBindingPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
