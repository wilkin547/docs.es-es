---
title: Interfaz ICorDebugReferenceValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
ms.openlocfilehash: 2efba22b4ec372c5ddedd4982a29d66945d3511c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792125"
---
# <a name="icordebugreferencevalue-interface"></a>Interfaz ICorDebugReferenceValue
Proporciona métodos que administran un valor que es una referencia a un objeto. (Es decir, esta interfaz proporciona métodos que administran un puntero). Esta interfaz implementa "ICorDebugValue".  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Dereference (método)](icordebugreferencevalue-dereference-method.md)|Obtiene el objeto al que se hace referencia.|  
|[DereferenceStrong (método)](icordebugreferencevalue-dereferencestrong-method.md)|Sin implementar. No llame a este método.|  
|[GetValue (método)](icordebugreferencevalue-getvalue-method.md)|Obtiene la dirección de memoria actual del objeto al que se hace referencia.|  
|[IsNull (método)](icordebugreferencevalue-isnull-method.md)|Obtiene un valor que indica si este `ICorDebugReferenceValue` es un valor null, en cuyo caso el `ICorDebugReferenceValue` no señala a un objeto.|  
|[SetValue (método)](icordebugreferencevalue-setvalue-method.md)|Establece la dirección de memoria actual. Es decir, este método establece este `ICorDebugReferenceValue` para que apunte a un objeto.|  
  
## <a name="remarks"></a>Notas  
 El Common Language Runtime (CLR) puede realizar una recolección de elementos no utilizados en objetos cuando continúa el proceso depurado. La recolección de elementos no utilizados puede mover objetos alrededor de la memoria. Una `ICorDebugReferenceValue` cooperará con la recolección de elementos no utilizados para que su información se actualice después de la recolección de elementos no utilizados o se invalidará implícitamente antes de la recolección de elementos no utilizados.  
  
 El objeto `ICorDebugReferenceValue` se puede invalidar implícitamente una vez que se ha continuado el proceso depurado. La "ICorDebugHandleValue" derivada no se invalida hasta que se libera o expone explícitamente.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
