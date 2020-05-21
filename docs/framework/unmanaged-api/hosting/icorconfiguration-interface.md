---
title: ICorConfiguration (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
ms.openlocfilehash: 3b8c9421dea4040a9f183b886f1ad8575cace780
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762440"
---
# <a name="icorconfiguration-interface"></a>ICorConfiguration (Interfaz)
Proporciona métodos para configurar el Common Language Runtime (CLR).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método AddDebuggerSpecialThread](icorconfiguration-adddebuggerspecialthread-method.md)|Indica a los servicios de depuración que se debe permitir que un subproceso determinado se siga ejecutando mientras el depurador tiene una aplicación detenida durante escenarios de depuración administrados o no administrados.|  
|[Método SetDebuggerThreadControl](icorconfiguration-setdebuggerthreadcontrol-method.md)|Establece la interfaz de devolución de llamada a la que los servicios de depuración llamarán cuando los subprocesos CLR se bloquean y desbloquean para la depuración.|  
|[Método SetGCHostControl](icorconfiguration-setgchostcontrol-method.md)|Establece la interfaz de devolución de llamada que va a utilizar el recolector de elementos no utilizados para solicitar al host que cambie los límites de la memoria virtual.|  
|[Método SetGCThreadControl](icorconfiguration-setgcthreadcontrol-method.md)|Establece la interfaz de devolución de llamada para programar subprocesos para tareas no en tiempo de ejecución que, de lo contrario, se bloquearían para una recolección de elementos no utilizados.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Interfaces de hospedaje](hosting-interfaces.md)
- [CorRuntimeHost (Coclase)](corruntimehost-coclass.md)
