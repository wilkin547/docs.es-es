---
title: Interfaz ICorDebugArrayValue
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
ms.openlocfilehash: 0944f3379c18cba56ab65fe40a5b94a64d8a8991
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778202"
---
# <a name="icordebugarrayvalue-interface"></a>Interfaz ICorDebugArrayValue

Subclase de ICorDebugHeapValue que representa una matriz unidimensional o multidimensional.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetBaseIndicies (método)](icordebugarrayvalue-getbaseindicies-method.md)|Obtiene el índice base de cada dimensión de la matriz.|  
|[GetCount (método)](icordebugarrayvalue-getcount-method.md)|Obtiene el número total de elementos de la matriz.|  
|[GetDimensions (método)](icordebugarrayvalue-getdimensions-method.md)|Obtiene las dimensiones de la matriz.|  
|[GetElement (método)](icordebugarrayvalue-getelement-method.md)|Obtiene un valor que representa el elemento especificado en la matriz.|  
|[GetElementAtPosition (método)](icordebugarrayvalue-getelementatposition-method.md)|Obtiene el elemento en la posición especificada y trata la matriz como una matriz unidimensional de base cero.|  
|[GetElementType (método)](icordebugarrayvalue-getelementtype-method.md)|Obtiene el tipo simple de los elementos de la matriz.|  
|[GetRank (método)](icordebugarrayvalue-getrank-method.md)|Obtiene el número de dimensiones de la matriz.|  
|[HasBaseIndicies (método)](icordebugarrayvalue-hasbaseindicies-method.md)|Determina si la matriz tiene índices base.|  
  
## <a name="remarks"></a>Notas  
 `ICorDebugArrayValue` admite Matrices unidimensionales y multidimensionales.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
