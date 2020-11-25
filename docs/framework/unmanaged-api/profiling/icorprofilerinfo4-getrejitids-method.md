---
title: ICorProfilerInfo4::GetReJITIDs (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
ms.openlocfilehash: 2ac645cbaaa45554568874653be016e4691bbd2f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707482"
---
# <a name="icorprofilerinfo4getrejitids-method"></a>ICorProfilerInfo4::GetReJITIDs (Método)

Devuelve una matriz de identificadores que identifican todas las versiones compiladas con JIT de la función especificada que se siguen asignando. Esto incluye las versiones de funciones compiladas con JIT que se han revertido posteriormente pero que todavía no se han liberado (por ejemplo, cuando el dominio de aplicación que contiene la función revertida todavía está en uso).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `functionId`  
 de `FunctionID` De la instancia de la función para la que se van a enumerar las versiones.  
  
 `cReJitIds`  
 de Número de identificadores de recompilación JIT asignados en la `reJitIds` matriz.  
  
 `pcReJitIds`  
 enuncia Número real de identificadores recompilados con JIT.  
  
 `reJitIds`  
 enuncia Matriz asignada por el llamador que contendrá los identificadores de recompilación JIT de la función especificada.  
  
## <a name="remarks"></a>Comentarios  

 `GetReJITIDs` enumera los identificadores de compilación JIT activos para una instancia de función determinada. Sigue el mismo patrón de uso que otras `ICorProfilerInfo` funciones que aceptan búferes asignados por el autor de la llamada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerInfo4 (Interfaz)](icorprofilerinfo4-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
