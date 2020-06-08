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
ms.openlocfilehash: 890bb9bdd3b639d38f4f290eed86ad72b6a53f0f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494454"
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
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
