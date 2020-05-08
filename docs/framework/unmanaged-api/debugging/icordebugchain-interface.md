---
title: Interfaz ICorDebugChain
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
ms.openlocfilehash: 6ae0fec0f8de2bbe3862f9f70ed9cf3d32af34c4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894211"
---
# <a name="icordebugchain-interface"></a>Interfaz ICorDebugChain

Representa un segmento de una pila de llamadas física o lógica.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnumerateFrames](icordebugchain-enumerateframes-method.md)|Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, empezando por el fotograma más reciente.|  
|[GetActiveFrame (Método)](icordebugchain-getactiveframe-method.md)|Obtiene el marco activo (es decir, el más reciente) de la cadena.|  
|[Método GetCallee](icordebugchain-getcallee-method.md)|Obtiene la cadena a la que llamó esta cadena.|  
|[Método GetCaller](icordebugchain-getcaller-method.md)|Obtiene la cadena que llamó a esta cadena.|  
|[Método GetContext](icordebugchain-getcontext-method.md)|No implementado.|  
|[Método GetNext](icordebugchain-getnext-method.md)|Obtiene la cadena de fotogramas siguiente para el subproceso.|  
|[Método GetPrevious](icordebugchain-getprevious-method.md)|Obtiene la cadena de fotogramas anterior para el subproceso.|  
|[Método GetReason](icordebugchain-getreason-method.md)|Obtiene el motivo del Genesis de esta cadena de llamada.|  
|[GetRegisterSet (Método)](icordebugchain-getregisterset-method.md)|Obtiene el conjunto de registros para la parte activa de esta cadena.|  
|[GetStackRange (Método)](icordebugchain-getstackrange-method.md)|Obtiene el intervalo de direcciones del segmento de pila para esta cadena.|  
|[Método GetThread](icordebugchain-getthread-method.md)|Obtiene el subproceso físico del que forma parte esta cadena de llamadas.|  
|[Método IsManaged](icordebugchain-ismanaged-method.md)|Obtiene un valor que indica si esta cadena ejecuta código administrado.|  
  
## <a name="remarks"></a>Observaciones  
 Los marcos de pila de una cadena ocupan el espacio de pila contiguo y comparten el mismo subproceso y contexto. Una cadena puede representar cadenas de código administradas o no administradas. Una instancia `ICorDebugChain` vacía representa una cadena de código no administrada.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Interfaces para depuración](debugging-interfaces.md)
