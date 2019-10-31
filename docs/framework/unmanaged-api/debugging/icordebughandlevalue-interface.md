---
title: ICorDebugHandleValue (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
ms.openlocfilehash: 94472e84b73cdffe09505088b1e7fbc20a209bc3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138476"
---
# <a name="icordebughandlevalue-interface"></a>ICorDebugHandleValue (Interfaz)

Subclase de ICorDebugReferenceValue que representa un valor de referencia en el que el depurador ha creado un identificador para la recolección de elementos no utilizados.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Dispose (método)](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|Libera el identificador al que hace referencia este objeto `ICorDebugHandleValue` sin liberar explícitamente el puntero de interfaz.|  
|[GetHandleType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|Obtiene un valor CorDebugHandleType (que describe el tipo de identificador al que hace referencia este `ICorDebugHandleValue`.|  
  
## <a name="remarks"></a>Comentarios  
 Un objeto `ICorDebugReferenceValue` invalidado por una interrupción en la ejecución de código depurado. Un `ICorDebugHandleValue` mantiene su referencia a través de saltos y continuaciones hasta que se libera explícitamente.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
