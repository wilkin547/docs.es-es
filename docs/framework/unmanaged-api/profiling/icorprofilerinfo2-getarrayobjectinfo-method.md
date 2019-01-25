---
title: ICorProfilerInfo2::GetArrayObjectInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0444b6a5fd1bb286df573b1bba7d35b0d2d14a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498848"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a>ICorProfilerInfo2::GetArrayObjectInfo (Método)
Obtiene información detallada sobre un objeto de matriz.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `objectId`  
 [in] El identificador de un objeto de matriz válida.  
  
 `cDimensions`  
 [in] El rango (número de dimensiones) de la matriz.  
  
 `pDimensionSizes`  
 [out] Una matriz que contiene enteros, cada uno que representa el tamaño de una dimensión de la matriz.  
  
 `pDimensionLowerBounds`  
 [out] Una matriz que contiene enteros, cada uno que representa la parte inferior se enlaza de una dimensión de la matriz.  
  
 `ppData`  
 [out] Un puntero a la dirección del búfer sin formato para la matriz, que se distribuyen según la convención de C++.  
  
## <a name="remarks"></a>Comentarios  
 El `pDimensionSizes` y `pDimensionLowerBounds` son matrices paralelas, por lo que los elementos que se encuentra en el mismo índice de cada matriz son características de la misma entidad.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
