---
title: ICorProfilerThreadEnum::Clone (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
ms.openlocfilehash: de2584b56701f4cffb6a108a5872641ec40e5762
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702529"
---
# <a name="icorprofilerthreadenumclone-method"></a>ICorProfilerThreadEnum::Clone (Método)

Obtiene un puntero de interfaz a una copia de esta interfaz [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppEnum`  
 enuncia Puntero al puntero de interfaz, que, a su vez, apunta a la copia de esta interfaz [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) . La copia del enumerador mantiene su propio estado de enumeración por separado de este enumerador. Sin embargo, la posición inicial del cursor de la copia es la misma que la posición actual del cursor del enumerador.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
