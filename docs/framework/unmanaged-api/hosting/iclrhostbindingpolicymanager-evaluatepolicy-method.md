---
title: ICLRHostBindingPolicyManager::EvaluatePolicy (Método)
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
ms.openlocfilehash: 9600573a0a730cee10247d5644d587e75856cdd9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141181"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a>ICLRHostBindingPolicyManager::EvaluatePolicy (Método)
Evalúa la Directiva de enlace en nombre del host.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzReferenceIdentity`  
 de Referencia al ensamblado antes de la evaluación de la Directiva.  
  
 `pbApplicationPolicy`  
 de Un puntero a un búfer que contiene los datos de la Directiva.  
  
 `cbAppPolicySize`  
 de Tamaño del búfer de `pbApplicationPolicy`.  
  
 `pwzPostPolicyReferenceIdentity`  
 enuncia Referencia al ensamblado después de la evaluación de los nuevos datos de la Directiva.  
  
 `pcchPostPolicyReferenceIdentity`  
 [in, out] Puntero al tamaño del búfer de referencia de identidad del ensamblado después de la evaluación de los datos de la nueva Directiva.  
  
 `pdwPoliciesApplied`  
 enuncia Puntero a una combinación lógica o de valores de [ebindpolicylevels (](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) , que indica qué directivas se han aplicado.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La evaluación se completó correctamente.|  
|E_INVALIDARG|`pwzReferenceIdentity` o `pbApplicationPolicy` es una referencia nula.|  
|ERROR_INSUFFICIENT_BUFFER|`cbAppPolicySize` es demasiado pequeño.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El método `EvaluatePolicy` permite que el host influya en la Directiva de enlace para mantener los requisitos de control de versiones de ensamblado específicos del host. El propio motor de directivas permanece dentro de CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRHostBindingPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
