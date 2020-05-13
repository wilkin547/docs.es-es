---
title: Interfaz ICorDebugHandleValue
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
ms.openlocfilehash: c901e21521e941c51939958175a5316808890e9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208647"
---
# <a name="icordebughandlevalue-interface"></a>Interfaz ICorDebugHandleValue

Subclase de ICorDebugReferenceValue que representa un valor de referencia en el que el depurador ha creado un identificador para la recolección de elementos no utilizados.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Dispose (Método)](icordebughandlevalue-dispose-method.md)|Libera el identificador al que hace referencia este `ICorDebugHandleValue` objeto sin liberar explícitamente el puntero de interfaz.|  
|[Método GetHandleType](icordebughandlevalue-gethandletype-method.md)|Obtiene un valor CorDebugHandleType (que describe el tipo de identificador al que hace referencia este `ICorDebugHandleValue` .|  
  
## <a name="remarks"></a>Observaciones  
 Un `ICorDebugReferenceValue` objeto queda invalidado por una interrupción en la ejecución de código depurado. Un `ICorDebugHandleValue` mantiene su referencia mediante saltos y continuaciones hasta que se libera explícitamente.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
