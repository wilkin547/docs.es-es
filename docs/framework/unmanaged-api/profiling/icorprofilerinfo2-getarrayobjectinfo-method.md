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
ms.openlocfilehash: 368b8f270797beb525e0745a29990667913f4071
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497366"
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
 enuncia Puntero a la dirección del búfer sin formato de la matriz, que se distribuye según la Convención de C++.  
  
## <a name="remarks"></a>Comentarios  
 `pDimensionSizes`Y `pDimensionLowerBounds` son matrices paralelas, por lo que los elementos que se encuentran en el mismo índice de cada matriz son características de la misma entidad.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)
