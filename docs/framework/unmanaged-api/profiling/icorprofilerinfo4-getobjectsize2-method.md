---
title: ICorProfilerInfo4::GetObjectSize2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
ms.openlocfilehash: b605419a291f7bee76ecad7e07be9a7a989f9fe9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496014"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a>ICorProfilerInfo4::GetObjectSize2 (Método)
Devuelve el tamaño de un objeto especificado. Reemplaza el método [ICorProfilerInfo:: GetObjectSize (](icorprofilerinfo-getobjectsize-method.md) por los tamaños de los objetos que son más grandes que los que se pueden expresar en `ULONG` .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a>Parámetros  
 `objectId`  
 de IDENTIFICADOR del objeto.  
  
 `pcSize`  
 enuncia Puntero al tamaño del objeto, en bytes.  
  
## <a name="remarks"></a>Comentarios  
 A menudo, los distintos objetos de los mismos tipos tienen el mismo tamaño. Sin embargo, algunos tipos, como matrices o cadenas, pueden tener un tamaño diferente para cada objeto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerInfo4 (Interfaz)](icorprofilerinfo4-interface.md)
