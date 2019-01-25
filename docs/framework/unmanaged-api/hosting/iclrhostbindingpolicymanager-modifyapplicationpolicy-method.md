---
title: ICLRHostBindingPolicyManager::ModifyApplicationPolicy (Método)
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45e0099ea60a338f0ea1ef414f4d2fa1c33c9d70
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726889"
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
 [in] Una combinación OR lógica de [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) valores, que indica el control de la redirección.  
  
 `pbNewApplicationPolicy`  
 [out] Un puntero a un búfer que contiene los nuevos datos de la directiva de enlace.  
  
 `pcbNewAppPolicySize`  
 [in, out] Un puntero al tamaño del búfer de nueva directiva de enlace.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La directiva se modificó correctamente.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity` o `pwzTargetAssemblyIdentity` era una referencia nula.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` es demasiado pequeño.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El `ModifyApplicationPolicy` método se puede llamar dos veces. La primera llamada debe proporcionar un valor null para el `pbNewApplicationPolicy` parámetro. Esta llamada devolverá el valor necesario para `pcbNewAppPolicySize`. La segunda llamada debe proporcionar este valor para `pcbNewAppPolicySize`y señale a un búfer de ese tamaño para `pbNewApplicationPolicy`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICLRHostBindingPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
