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
ms.openlocfilehash: a147aee1ebba57b86dbbf8a7648456b8d7494936
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793199"
---
# <a name="icordebugmda-interface"></a>ICorDebugMDA (Interfaz)
Representa un mensaje del asistente para la depuración administrada (MDA).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetDescription (método)](icordebugmda-getdescription-method.md)|Obtiene una cadena que contiene una descripción de este MDA.|  
|[GetFlags (método)](icordebugmda-getflags-method.md)|Obtiene las marcas asociadas a este MDA.|  
|[GetName (método)](icordebugmda-getname-method.md)|Obtiene una cadena que contiene el nombre de este MDA.|  
|[GetOSThreadId (método)](icordebugmda-getosthreadid-method.md)|Obtiene el identificador del subproceso del sistema operativo en el que se ejecuta este MDA.|  
|[GetXML (método)](icordebugmda-getxml-method.md)|Obtiene la secuencia XML completa asociada a este MDA.|  
  
## <a name="remarks"></a>Notas  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [Diagnóstico de errores con asistentes para la depuración administrada](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
