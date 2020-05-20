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
ms.openlocfilehash: 5b537d59014afa783d3f8c5046cc02dad7ea7740
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616000"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a>ICLRAssemblyIdentityManager::GetBindingIdentityFromFile (Método)
Obtiene los datos de enlace de identidad del ensamblado en la ruta de acceso de archivo especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzFilePath`  
 de Ruta de acceso al archivo que se va a evaluar.  
  
 `dwFlags`  
 de Un valor de la enumeración [eclrassemblyidentityflags (](eclrassemblyidentityflags-enumeration.md) que indica el tipo de identidad de un ensamblado. Se proporciona para la extensibilidad futura. CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor que admite la versión 2,0 de Common Language Runtime (CLR).  
  
 `pwzBuffer`  
 enuncia Búfer que contiene los datos de identidad del ensamblado opaco.  
  
 `pcchBufferSize`  
 [in, out] Puntero al tamaño de `pwzBuffer` .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se devolvió correctamente.|  
|E_INVALIDARG|El valor de proporcionado `pwzFilePath` es NULL.|  
|ERROR_INSUFFICIENT_BUFFER|El tamaño de `pwzBuffer` es demasiado pequeño.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  
 `GetBindingIdentityFromFile`normalmente se llama dos veces. La primera llamada proporciona un valor null para `pwzBuffer` y el método devuelve el tamaño adecuado en `pcchBufferSize` . La segunda llamada proporciona un búfer asignado adecuadamente y el método devuelve con los datos de búfer reales al finalizar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICLRAssemblyIdentityManager (Interfaz)](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList (Interfaz)](iclrassemblyreferencelist-interface.md)
- [ICLRHostBindingPolicyManager (Interfaz)](iclrhostbindingpolicymanager-interface.md)
