---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
ms.openlocfilehash: f4c200ad23ff7a71298e84fda857912da53978a5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126692"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a>ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream (Método)
Obtiene un puntero a un objeto [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) que contiene los datos de identidad del ensamblado para los ensamblados a los que hace referencia el ensamblado en la secuencia especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pStream`  
 de Puntero de interfaz a un `IStream` que contiene el ensamblado que se va a evaluar.  
  
 `dwFlags`  
 de Se proporciona para la extensibilidad futura. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor que admite la versión actual del Common Language Runtime (CLR).  
  
 `pExcludeAssembliesList`  
 de Un puntero a un objeto [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) que contiene datos de identidad del ensamblado para los ensamblados que se van a excluir de `ppReferenceEnum`.  
  
 `ppReferenceEnum`  
 enuncia Puntero a la dirección de un objeto `ICLRReferenceAssemblyEnum` que contiene los datos de identidad del ensamblado para los ensamblados a los que hace referencia el ensamblado en `pStream`, excluyendo los ensamblados en `pExcludeAssembliesList`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El autor de la llamada puede optar por excluir un conjunto de referencias de ensamblado conocidas de la lista devuelta. Este conjunto se define mediante `pExcludeAssembliesList`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyIdentityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [ICLRReferenceAssemblyEnum (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
