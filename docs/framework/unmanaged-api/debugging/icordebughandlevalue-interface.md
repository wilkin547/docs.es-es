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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6dddc1665dff5c1a0629d25aa99066ce6eeca94a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981444"
---
# <a name="icordebughandlevalue-interface"></a>ICorDebugHandleValue (Interfaz)

Una subclase de ICorDebugReferenceValue que representa un valor de referencia a la que el depurador ha creado un identificador para la recolección.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Dispose (método)](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|Libera el identificador que hace referencia esta `ICorDebugHandleValue` objeto sin liberar explícitamente el puntero de interfaz.|  
|[GetHandleType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|Obtiene un valor de CorDebugHandleType que describe el tipo de identificador que hace referencia esta `ICorDebugHandleValue`.|  
  
## <a name="remarks"></a>Comentarios  
 Un `ICorDebugReferenceValue` objeto queda invalidado por una interrupción en la ejecución del código depurado. Un `ICorDebugHandleValue` mantiene su referencia a través de interrupciones y continuaciones, hasta que se libera explícitamente.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
