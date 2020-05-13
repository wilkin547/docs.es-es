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
ms.openlocfilehash: 6c6ff428e378e973d8846674ffacdcd04b2dbdbc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378346"
---
# <a name="icordebugreferencevalue-interface"></a>Interfaz ICorDebugReferenceValue
Proporciona métodos que administran un valor que es una referencia a un objeto. (Es decir, esta interfaz proporciona métodos que administran un puntero). Esta interfaz implementa "ICorDebugValue".  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Dereference](icordebugreferencevalue-dereference-method.md)|Obtiene el objeto al que se hace referencia.|  
|[Método DereferenceStrong](icordebugreferencevalue-dereferencestrong-method.md)|No implementado. No llame a este método.|  
|[Método GetValue](icordebugreferencevalue-getvalue-method.md)|Obtiene la dirección de memoria actual del objeto al que se hace referencia.|  
|[Método IsNull](icordebugreferencevalue-isnull-method.md)|Obtiene un valor que indica si `ICorDebugReferenceValue` se trata de un valor null, en cuyo caso `ICorDebugReferenceValue` no apunta a un objeto.|  
|[Método SetValue](icordebugreferencevalue-setvalue-method.md)|Establece la dirección de memoria actual. Es decir, este método establece esto `ICorDebugReferenceValue` para que apunte a un objeto.|  
  
## <a name="remarks"></a>Observaciones  
 El Common Language Runtime (CLR) puede realizar una recolección de elementos no utilizados en objetos cuando continúa el proceso depurado. La recolección de elementos no utilizados puede mover objetos alrededor de la memoria. Un `ICorDebugReferenceValue` objeto cooperará con la recolección de elementos no utilizados para que su información se actualice después de la recolección de elementos no utilizados o se invalidará implícitamente antes de la recolección de elementos no utilizados.  
  
 El `ICorDebugReferenceValue` objeto se puede invalidar implícitamente una vez que se ha continuado el proceso depurado. La "ICorDebugHandleValue" derivada no se invalida hasta que se libera o expone explícitamente.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
