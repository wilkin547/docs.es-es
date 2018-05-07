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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e37d56a321e6529812045e37c4f1929818b38a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a>ICLRHostBindingPolicyManager::EvaluatePolicy (Método)
Evalúa la directiva de enlace en nombre del host.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pwzReferenceIdentity`  
 [in] Una referencia al ensamblado antes de la evaluación de directivas.  
  
 `pbApplicationPolicy`  
 [in] Un puntero a un búfer que contiene los datos de la directiva.  
  
 `cbAppPolicySize`  
 [in] El tamaño de la `pbApplicationPolicy` búfer.  
  
 `pwzPostPolicyReferenceIdentity`  
 [out] Una referencia al ensamblado después de la evaluación de los nuevos datos de directiva.  
  
 `pcchPostPolicyReferenceIdentity`  
 [entrada, salida] Un puntero al tamaño del búfer de referencia de identidad de ensamblado después de la evaluación de los nuevos datos de directiva.  
  
 `pdwPoliciesApplied`  
 [out] Un puntero a una combinación OR lógica de [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) valores, que indica qué directivas se han aplicado.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La evaluación que se completó correctamente.|  
|E_INVALIDARG|Ya sea `pwzReferenceIdentity` o `pbApplicationPolicy` es una referencia nula.|  
|ERROR_INSUFFICIENT_BUFFER|`cbAppPolicySize` es demasiado pequeño.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada agotó el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El `EvaluatePolicy` método permite al host influir en la directiva de enlace para mantener el ensamblado específico del host requisitos de control de versiones. El propio motor de directiva permanece dentro del CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRHostBindingPolicyManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
