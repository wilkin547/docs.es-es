---
description: 'Más información acerca de: ICorProfilerInfo2:: Getobjectgeneration ((método)'
title: ICorProfilerInfo2::GetObjectGeneration (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetObjectGeneration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type:
- apiref
ms.openlocfilehash: f4927c081393a11f7dad7d59cce311b82072659c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716450"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a>ICorProfilerInfo2::GetObjectGeneration (Método)

Obtiene el segmento del montón que contiene el objeto especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a>Parámetros  

 `objectId`  
 de IDENTIFICADOR del objeto.  
  
 `range`  
 enuncia Puntero a una estructura de [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) , que describe un intervalo (es decir, un bloque) de memoria dentro de la generación que se está sometiendo a la recolección de elementos no utilizados. Este intervalo contiene el objeto especificado.  
  
## <a name="remarks"></a>Observaciones  

 `GetObjectGeneration`Se puede llamar al método desde cualquier devolución de llamada del generador de perfiles, siempre que la recolección de elementos no utilizados no esté en curso. Es decir, se puede llamar desde cualquier devolución de llamada excepto las que se producen entre [ICorProfilerCallback2:: garbagecollectionstarted (](icorprofilercallback2-garbagecollectionstarted-method.md) y [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)
