---
title: ICorProfilerInfo::IsArrayClass (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
ms.openlocfilehash: 57515ac4670b9b7e25bb496851347a62e1b246df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438709"
---
# <a name="icorprofilerinfoisarrayclass-method"></a>ICorProfilerInfo::IsArrayClass (Método)
Determina si la clase especificada es una clase de matriz.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a>Parámetros  
 `classId`  
 de IDENTIFICADOR de la clase que se va a examinar.  
  
 `pBaseElemType`  
 enuncia Un puntero a un valor de la enumeración CorElementType que indica el tipo de los elementos de la matriz.  
  
 `pBaseClassId`  
 enuncia Puntero al identificador de clase de los elementos de la matriz, si está disponible.  
  
 `pcRank`  
 enuncia Un puntero a un entero que indica el rango (es decir, el número de dimensiones) de la matriz.  
  
## <a name="remarks"></a>Comentarios  
 Si la clase especificada es una clase de matriz, el método `IsArrayClass` devuelve un S_OK HRESULT y valores para cualquier parámetro de salida que no sea NULL. De lo contrario, devuelve S_FALSE.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
