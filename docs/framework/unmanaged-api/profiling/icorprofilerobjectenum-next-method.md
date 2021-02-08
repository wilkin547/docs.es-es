---
description: 'Más información acerca de: ICorProfilerObjectEnum:: Next (método)'
title: ICorProfilerObjectEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type:
- apiref
ms.openlocfilehash: 7f61fa1d4e28043bf5eda95f67dde0d8e87d8c0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781420"
---
# <a name="icorprofilerobjectenumnext-method"></a>ICorProfilerObjectEnum::Next (Método)

Obtiene el número especificado de objetos contiguos de una colección secuencial de objetos, empezando en la posición actual del enumerador en la secuencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `celt`  
 [in] Número de objetos que se van a recuperar.  
  
 `objects`  
 enuncia Matriz de `ObjectID` valores, cada uno de los cuales representa un objeto recuperado.  
  
 `pceltFetched`  
 [out] Puntero al número de elementos realmente devueltos en la matriz `objects`.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerObjectEnum (Interfaz)](icorprofilerobjectenum-interface.md)
