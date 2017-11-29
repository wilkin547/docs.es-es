---
title: "ICLRHostBindingPolicyManager::ModifyApplicationPolicy (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 51775f52e34f35d8ef9f3a8533363be73e9bd7c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy (Método)
Modifica la directiva de enlace para el ensamblado especificado y crea una nueva versión de la directiva.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,   
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,   
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pwzSourceAssemblyIdentity`  
 [in] La identidad del ensamblado que se va a modificar.  
  
 `pwzTargetAssemblyIdentity`  
 [in] La nueva identidad del ensamblado modificado.  
  
 `pbApplicationPolicy`  
 [in] Un puntero a un búfer que contiene los datos de la directiva de enlace del ensamblado que se va a modificar.  
  
 `cbAppPolicySize`  
 [in] El tamaño de la directiva de enlace que se debe reemplazar.  
  
 `dwPolicyModifyFlags`  
 [in] Combinación OR lógica de [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) valores, que indican el control de la redirección.  
  
 `pbNewApplicationPolicy`  
 [out] Un puntero a un búfer que contiene los nuevos datos de directiva de enlace.  
  
 `pcbNewAppPolicySize`  
 [entrada, salida] Un puntero al tamaño del búfer de directiva de enlace nueva.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|Se modificó correctamente la directiva.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity`o `pwzTargetAssemblyIdentity` era una referencia nula.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy`es demasiado pequeño.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada agotó el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El `ModifyApplicationPolicy` método puede llamarse dos veces. La primera llamada debe proporcionar un valor null para la `pbNewApplicationPolicy` parámetro. Esta llamada devolverá el valor necesario para `pcbNewAppPolicySize`. La segunda llamada debe proporcionar este valor para `pcbNewAppPolicySize`y señalar un búfer de ese tamaño para `pbNewApplicationPolicy`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRHostBindingPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
