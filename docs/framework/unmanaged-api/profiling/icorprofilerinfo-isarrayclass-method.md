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
ms.openlocfilehash: 2608f91a7c5baa935e48fbe58ad4d14aaaad1f0d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722510"
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

 Si la clase especificada es una clase de matriz, el `IsArrayClass` método devuelve un S_OK HRESULT y valores para cualquier parámetro de salida que no sea NULL. De lo contrario, devuelve S_FALSE.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
