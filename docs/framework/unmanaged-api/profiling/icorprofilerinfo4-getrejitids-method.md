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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d2d48e5fb070ec0334de579d2e28146177a87b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049484"
---
# <a name="icorprofilerinfo4getrejitids-method"></a>ICorProfilerInfo4::GetReJITIDs (Método)
Devuelve una matriz de identificadores que identifican todas recompilada con JIT las versiones de la función especificada que todavía se asignan. Esto incluye versiones recompilada con JIT de funciones que se han revertido posteriormente, pero aún no se ha liberado (por ejemplo, cuando el dominio de aplicación que contiene la función revertida todavía está en uso).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] El `FunctionID` de la instancia de la función para que se enumeran las versiones.  
  
 `cReJitIds`  
 [in] El número de identificadores recompilada con JIT asignada en el `reJitIds` matriz.  
  
 `pcReJitIds`  
 [out] El número real de los identificadores de recompilada con JIT.  
  
 `reJitIds`  
 [out] Una matriz asignada por el llamador que contendrá los identificadores recompilada con JIT para la función especificada.  
  
## <a name="remarks"></a>Comentarios  
 `GetReJITIDs` Enumera los identificadores de recompilada con JIT activos para una instancia de la función especificada. Sigue el mismo patrón de uso como otro `ICorProfilerInfo` funciones que aceptan los búferes asignados por el llamador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
