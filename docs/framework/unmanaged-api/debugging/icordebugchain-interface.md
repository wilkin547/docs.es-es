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
ms.openlocfilehash: f4bacfe94178ea78b1c3afd15a2e100076c38a84
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777994"
---
# <a name="icordebugchain-interface"></a>Interfaz ICorDebugChain

Representa un segmento de una pila de llamadas física o lógica.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumerateFrames (método)](icordebugchain-enumerateframes-method.md)|Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, empezando por el fotograma más reciente.|  
|[GetActiveFrame (método)](icordebugchain-getactiveframe-method.md)|Obtiene el marco activo (es decir, el más reciente) de la cadena.|  
|[GetCallee (método)](icordebugchain-getcallee-method.md)|Obtiene la cadena a la que llamó esta cadena.|  
|[GetCaller (método)](icordebugchain-getcaller-method.md)|Obtiene la cadena que llamó a esta cadena.|  
|[GetContext (método)](icordebugchain-getcontext-method.md)|Sin implementar.|  
|[GetNext (método)](icordebugchain-getnext-method.md)|Obtiene la cadena de fotogramas siguiente para el subproceso.|  
|[GetPrevious (método)](icordebugchain-getprevious-method.md)|Obtiene la cadena de fotogramas anterior para el subproceso.|  
|[GetReason (método)](icordebugchain-getreason-method.md)|Obtiene el motivo del Genesis de esta cadena de llamada.|  
|[GetRegisterSet (método)](icordebugchain-getregisterset-method.md)|Obtiene el conjunto de registros para la parte activa de esta cadena.|  
|[GetStackRange (método)](icordebugchain-getstackrange-method.md)|Obtiene el intervalo de direcciones del segmento de pila para esta cadena.|  
|[GetThread (método)](icordebugchain-getthread-method.md)|Obtiene el subproceso físico del que forma parte esta cadena de llamadas.|  
|[IsManaged (método)](icordebugchain-ismanaged-method.md)|Obtiene un valor que indica si esta cadena ejecuta código administrado.|  
  
## <a name="remarks"></a>Notas  
 Los marcos de pila de una cadena ocupan el espacio de pila contiguo y comparten el mismo subproceso y contexto. Una cadena puede representar cadenas de código administradas o no administradas. Una instancia de `ICorDebugChain` vacía representa una cadena de código no administrada.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
