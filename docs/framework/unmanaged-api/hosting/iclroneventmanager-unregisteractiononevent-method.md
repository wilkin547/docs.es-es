---
description: 'Más información sobre: ICLROnEventManager:: Unregisteractiononevent ((método)'
title: ICLROnEventManager::UnregisterActionOnEvent (Método)
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.UnregisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::UnregisterActionOnEvent
helpviewer_keywords:
- UnRegisterActionOnEvent method [.NET Framework hosting]
- ICLROnEventManager::UnRegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: 4c02ec37-cdf0-46b2-890e-235092741236
topic_type:
- apiref
ms.openlocfilehash: 8131c58669ff7be0fdc2b2e063c70d3b370921e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789819"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a>ICLROnEventManager::UnregisterActionOnEvent (Método)

Anula el registro de un puntero de devolución de llamada registrado previamente para el evento especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `event`  
 de Uno de los valores de [EClrEvent](eclrevent-enumeration.md) , que indica el evento para el que se va a anular el registro del puntero de devolución de llamada descrito por `pAction` .  
  
 `pAction`  
 de Un puntero a un objeto [IActionOnCLREvent](iactiononclrevent-interface.md) que se pasó como parámetro al método [RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`UnregisterActionOnEvent` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrEvent (Enumeración)](eclrevent-enumeration.md)
- [IActionOnCLREvent (Interfaz)](iactiononclrevent-interface.md)
- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
- [ICLROnEventManager (Interfaz)](iclroneventmanager-interface.md)
