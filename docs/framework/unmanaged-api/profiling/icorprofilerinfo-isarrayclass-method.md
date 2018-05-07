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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f34fee19c796f65d315fcbd26d55e1d5322303a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfoisarrayclass-method"></a>ICorProfilerInfo::IsArrayClass (Método)
Determina si la clase especificada es una clase de matriz.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `classId`  
 [in] El identificador de la clase se va a examinar.  
  
 `pBaseElemType`  
 [out] Un puntero a un valor de la enumeración CorElementType que indica el tipo de los elementos de matriz.  
  
 `pBaseClassId`  
 [out] Un puntero al identificador de clase de los elementos de matriz, si está disponible.  
  
 `pcRank`  
 [out] Un puntero a un entero que indica el rango (es decir, el número de dimensiones) de la matriz.  
  
## <a name="remarks"></a>Comentarios  
 Si la clase especificada es una clase de matriz, el `IsArrayClass` método devuelve un HRESULT de S_OK y valores para cualquier parámetro de salida distinto de null. En caso contrario, devuelve S_FALSE.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
