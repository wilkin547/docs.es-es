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
ms.openlocfilehash: d8df78e3d5cebe5378dfba11dc0ea93cc8e346eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178102"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy (Método)
Modifica la directiva de enlace para el ensamblado especificado y crea una nueva versión de la directiva.  
  
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
 [en] La identidad del ensamblado que se va a modificar.  
  
 `pwzTargetAssemblyIdentity`  
 [en] La nueva identidad del ensamblado modificado.  
  
 `pbApplicationPolicy`  
 [en] Puntero a un búfer que contiene los datos de directiva de enlace para que el ensamblado los modifique.  
  
 `cbAppPolicySize`  
 [en] El tamaño de la directiva de enlace que se va a reemplazar.  
  
 `dwPolicyModifyFlags`  
 [en] Una combinación OR lógica de [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) valores, que indica el control de redirección.  
  
 `pbNewApplicationPolicy`  
 [fuera] Puntero a un búfer que contiene los nuevos datos de directiva de enlace.  
  
 `pcbNewAppPolicySize`  
 [adentro, fuera] Un puntero al tamaño del nuevo búfer de directiva de enlace.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La directiva se modificó correctamente.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity`o `pwzTargetAssemblyIdentity` era una referencia nula.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy` es demasiado pequeño.|  
|HOST_E_CLRNOTAVAILABLE|Common Language Runtime (CLR) no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se adelantó la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no es el propietario de la cerradura.|  
|HOST_E_ABANDONED|Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.|  
|E_FAIL|Se ha producido un fallo catastrófico desconocido. Después de que un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  
 El `ModifyApplicationPolicy` método se puede llamar dos veces. La primera llamada debe proporcionar `pbNewApplicationPolicy` un valor nulo para el parámetro. Esta llamada se devolverá `pcbNewAppPolicySize`con el valor necesario para . La segunda llamada debe `pcbNewAppPolicySize`proporcionar este valor para , `pbNewApplicationPolicy`y apuntar a un búfer de ese tamaño para .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MScorEE.h  
  
 **Biblioteca:** Incluido como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRHostBindingPolicyManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
