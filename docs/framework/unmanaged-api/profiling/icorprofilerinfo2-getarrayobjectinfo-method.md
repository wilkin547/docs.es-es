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
ms.openlocfilehash: 97b127c9a6aac0a0fefe25faf294791dcd2c8e41
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436034"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a>ICorProfilerInfo2::GetArrayObjectInfo (Método)
Obtiene información detallada sobre un objeto de matriz.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a>Parámetros  
 `objectId`  
 de IDENTIFICADOR de un objeto de matriz válido.  
  
 `cDimensions`  
 de Rango (número de dimensiones) de la matriz.  
  
 `pDimensionSizes`  
 enuncia Una matriz que contiene enteros, cada uno de los cuales representa el tamaño de una dimensión de la matriz.  
  
 `pDimensionLowerBounds`  
 enuncia Una matriz que contiene enteros, cada uno de los cuales representa el límite inferior de una dimensión de la matriz.  
  
 `ppData`  
 enuncia Puntero a la dirección del búfer sin formato de la matriz, que se distribuye según la C++ Convención.  
  
## <a name="remarks"></a>Comentarios  
 Los `pDimensionSizes` y `pDimensionLowerBounds` son matrices paralelas, por lo que los elementos que se encuentran en el mismo índice de cada matriz son características de la misma entidad.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
