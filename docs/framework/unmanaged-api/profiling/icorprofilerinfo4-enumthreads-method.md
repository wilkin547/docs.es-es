---
title: ICorProfilerInfo4::EnumThreads (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
ms.openlocfilehash: df0e66c8563404d7de4f1e11f41483f2f61f519c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721561"
---
# <a name="icorprofilerinfo4enumthreads-method"></a>ICorProfilerInfo4::EnumThreads (Método)

Devuelve un enumerador que proporciona métodos para recorrer secuencialmente en iteración la colección de todos los subprocesos administrados en el proceso de la que se van a realizar perfiles.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppEnum`  
 enuncia Puntero a una interfaz [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerThreadEnum (Interfaz)](icorprofilerthreadenum-interface.md)
- [ICorProfilerInfo4 (Interfaz)](icorprofilerinfo4-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
