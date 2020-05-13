---
title: ICorDebugMDA (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
ms.openlocfilehash: d711f36b4e2071dac9458a023e1d3cf4743e77b3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212638"
---
# <a name="icordebugmda-interface"></a>ICorDebugMDA (Interfaz)
Representa un mensaje del asistente para la depuración administrada (MDA).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetDescription](icordebugmda-getdescription-method.md)|Obtiene una cadena que contiene una descripción de este MDA.|  
|[Método GetFlags](icordebugmda-getflags-method.md)|Obtiene las marcas asociadas a este MDA.|  
|[Método GetName](icordebugmda-getname-method.md)|Obtiene una cadena que contiene el nombre de este MDA.|  
|[Método GetOSThreadId](icordebugmda-getosthreadid-method.md)|Obtiene el identificador del subproceso del sistema operativo en el que se ejecuta este MDA.|  
|[Método GetXML](icordebugmda-getxml-method.md)|Obtiene la secuencia XML completa asociada a este MDA.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Diagnóstico de errores con asistentes de depuraciones administradas](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
