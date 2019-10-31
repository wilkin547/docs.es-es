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
ms.openlocfilehash: d5323538447e083a0c727e43261dd68337182b9b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141079"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy (Método)
Modifica la Directiva de enlace para el ensamblado especificado y crea una nueva versión de la Directiva.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="parameters"></a>Parámetros  
 `pwzSourceAssemblyIdentity`  
 de La identidad del ensamblado que se va a modificar.  
  
 `pwzTargetAssemblyIdentity`  
 de Nueva identidad del ensamblado modificado.  
  
 `pbApplicationPolicy`  
 de Puntero a un búfer que contiene los datos de la Directiva de enlace del ensamblado que se va a modificar.  
  
 `cbAppPolicySize`  
 de Tamaño de la Directiva de enlace que se va a reemplazar.  
  
 `dwPolicyModifyFlags`  
 de Una combinación lógica o lógica de valores de [ehostbindingpolicymodifyflags (](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) , que indica el control de la redirección.  
  
 `pbNewApplicationPolicy`  
 enuncia Un puntero a un búfer que contiene los nuevos datos de la Directiva de enlace.  
  
 `pcbNewAppPolicySize`  
 [in, out] Puntero al tamaño del nuevo búfer de directiva de enlace.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La Directiva se modificó correctamente.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity` o `pwzTargetAssemblyIdentity` era una referencia nula.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` es demasiado pequeño.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 Se puede llamar al método `ModifyApplicationPolicy` dos veces. La primera llamada debe proporcionar un valor null para el parámetro `pbNewApplicationPolicy`. Esta llamada devolverá con el valor necesario para `pcbNewAppPolicySize`. La segunda llamada debe proporcionar este valor para `pcbNewAppPolicySize`y apuntar a un búfer de ese tamaño para `pbNewApplicationPolicy`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRHostBindingPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
