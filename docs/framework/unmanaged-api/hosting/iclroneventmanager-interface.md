---
title: ICLROnEventManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
ms.openlocfilehash: 30312e6e09535cee2968b1f9e8ac87b461c5ff40
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703521"
---
# <a name="iclroneventmanager-interface"></a>ICLROnEventManager (Interfaz)
Proporciona métodos que permiten al host registrar y anular el registro de devoluciones de llamada para eventos de Common Language Runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md)|Registra un puntero de devolución de llamada para el evento especificado.|  
|[Método UnregisterActionOnEvent](iclroneventmanager-unregisteractiononevent-method.md)|Anula el registro de un puntero de devolución de llamada registrado previamente para el evento especificado.|  
  
## <a name="remarks"></a>Observaciones  
 Para registrar y anular el registro de las devoluciones de llamada de eventos, el host obtiene una referencia a llamando al `ICLROnEventManager` método [ICLRControl:: GetCLRManager (](iclrcontrol-getclrmanager-method.md) .  
  
> [!NOTE]
> Los eventos descritos por [EClrEvent](eclrevent-enumeration.md) se pueden desencadenar más de una vez y desde distintos subprocesos para indicar una descarga o la deshabilitación de CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [EClrEvent (Enumeración)](eclrevent-enumeration.md)
- [IActionOnCLREvent (Interfaz)](iactiononclrevent-interface.md)
- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
