---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferenceAssembliesFromFile method [.NET Framework hosting]
- GetReferenceAssembliesFromFile method [.NET Framework hosting]
ms.assetid: eed63d31-d977-4c7d-9443-f9d37a2a7d81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eac70f35e3c4c0beab0842f24702213a98fbaae3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478497"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a>ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile (Método)
Obtiene un [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instancia que contiene una lista de ensamblados al que hace referencia el ensamblado en la ruta de acceso de archivo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzFilePath`  
 [in] La ruta de acceso al ensamblado que se va a evaluar.  
  
 `dwFlags`  
 [in] Se proporciona para extensibilidad futura. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor compatible con la versión actual de common language runtime (CLR).  
  
 `pExcludeAssembliesList`  
 [in] Un puntero a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) objeto que representa los ensamblados que se deben excluir de `ppReferenceEnum`.  
  
 `ppReferenceEnum`  
 [out] Un puntero a la dirección de un `ICLRReferenceAssemblyEnum` objeto que contiene datos de identidad de ensamblado para los ensamblados que se hace referencia el ensamblado en `pwzFilePath`, excluyendo los ensamblados representados por `pExcludeAssembliesList`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El llamador puede excluir un conjunto de referencias de ensamblados conocidos de la lista devuelta. Este conjunto se define mediante el `pExcludeAssembliesList` parámetro.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICLRAssemblyIdentityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [ICLRReferenceAssemblyEnum (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
