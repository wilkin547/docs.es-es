---
title: "ICorProfilerInfo4::GetReJITIDs (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fb1e507bea6f52e4959f241f1507807a76c0ec5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4getrejitids-method"></a>ICorProfilerInfo4::GetReJITIDs (Método)
Devuelve una matriz de identificadores que identifican todas las recompilado con JIT versiones de la función especificada que todavía se asignarán. Esto incluye versiones recompilado con JIT de funciones que se han revertido posteriormente pero que aún no se ha liberado (por ejemplo, cuando el dominio de aplicación que contiene la función revertida aún está en uso).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] El `FunctionID` de la instancia de la función para la que se va a enumerar versiones.  
  
 `cReJitIds`  
 [in] El número de identificadores recompilado con JIT asignada en el `reJitIds` matriz.  
  
 `pcReJitIds`  
 [out] El número real de identificadores recompilado con JIT.  
  
 `reJitIds`  
 [out] Una matriz asignada por el llamador que contendrá los identificadores recompilado con JIT para la función especificada.  
  
## <a name="remarks"></a>Comentarios  
 `GetReJITIDs`Enumera los identificadores activos recompilado con JIT para una instancia de la función especificada. Sigue el mismo patrón de uso que otros `ICorProfilerInfo` funciones que aceptan búferes asignados al llamador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
