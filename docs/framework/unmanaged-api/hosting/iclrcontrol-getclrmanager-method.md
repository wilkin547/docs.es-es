---
title: ICLRControl::GetCLRManager (Método)
ms.date: 03/30/2017
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
ms.openlocfilehash: 04cb45cd021532b6cb3d74a195cbd62e1ab8d31d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615858"
---
# <a name="iclrcontrolgetclrmanager-method"></a>ICLRControl::GetCLRManager (Método)
Obtiene un puntero de interfaz a una instancia de cualquiera de los tipos de administrador que el host puede usar para configurar el Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `riid`  
 de `IID`Del tipo de administrador que se va a devolver. `IID`Se admiten los valores siguientes.  
  
- IID_ICLRDebugManager: especifica que será `ppObject` de tipo [ICLRDebugManager](iclrdebugmanager-interface.md).  
  
- IID_ICLRErrorReportingManager: especifica que será `ppObject` de tipo [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md).  
  
- IID_ICLRGCManager: especifica que será `ppObject` de tipo [ICLRGCManager](iclrgcmanager-interface.md).  
  
- IID_ICLRHostProtectionManager: especifica que será `ppObject` de tipo [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md).  
  
- IID_ICLROnEventManager: especifica que será `ppObject` de tipo [ICLROnEventManager](iclroneventmanager-interface.md).  
  
- IID_ICLRPolicyManager: especifica que `ppObject` será de tipo [ICLRPolicyManager](iclrpolicymanager-interface.md).  
  
- IID_ICLRTaskManager: especifica que será `ppObject` de tipo [ICLRTaskManager](iclrtaskmanager-interface.md).  
  
 `ppObject`  
 enuncia Puntero de interfaz al administrador solicitado, o null si se solicitó un tipo de administrador no válido.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_NOINTERFACE|No se admite el tipo de interfaz.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
- [IHostControl (Interfaz)](ihostcontrol-interface.md)
