---
description: 'Más información acerca de: interfaz ICorConfiguration'
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
ms.openlocfilehash: f75e9e445c7fe4615abcae27756bcc420b5255b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636694"
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
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](hosting-interfaces.md)
- [CorRuntimeHost (Coclase)](corruntimehost-coclass.md)
