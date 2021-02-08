---
description: 'Más información acerca de: ICLRRuntimeHost:: ExecuteInAppDomain ((método)'
title: ICLRRuntimeHost::ExecuteInAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
ms.openlocfilehash: 6640713b55e05817f39af819d5e41ee1f2a10b68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799751"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a>ICLRRuntimeHost::ExecuteInAppDomain (Método)

Especifica el <xref:System.AppDomain> en el que se va a ejecutar el código administrado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `AppDomainId`  
 de IDENTIFICADOR numérico del en el <xref:System.AppDomain> que se va a ejecutar el método especificado.  
  
 `pCallback`  
 de Puntero a la función que se va a ejecutar dentro del especificado <xref:System.AppDomain> .  
  
 `cookie`  
 de Puntero a la memoria opaca asignada por el llamador. El Common Language Runtime (CLR) pasa este parámetro a la devolución de llamada del dominio. No es memoria del montón administrado en tiempo de ejecución; el autor de la llamada controla tanto la asignación como la duración de esta memoria.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`ExecuteInAppDomain` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  

 `ExecuteInAppDomain` permite que el host ejerza el control sobre <xref:System.AppDomain> el que se debe ejecutar el método administrado especificado. Puede obtener el valor del identificador de un dominio de aplicación, que se corresponde con el valor de la <xref:System.AppDomain.Id%2A> propiedad, llamando al [método GetCurrentAppDomainId (](iclrruntimehost-getcurrentappdomainid-method.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRRuntimeHost (Interfaz)](iclrruntimehost-interface.md)
