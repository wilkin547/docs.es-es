---
description: 'Más información acerca de: ICorProfilerFunctionEnum:: Clone (método)'
title: ICorProfilerFunctionEnum::Clone (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
ms.openlocfilehash: 6cadadd98f64a27de0cd4e7d264fe797d22c33a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737680"
---
# <a name="icorprofilerfunctionenumclone-method"></a>ICorProfilerFunctionEnum::Clone (Método)

Obtiene un puntero de interfaz a una copia de esta interfaz [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppEnum`  
 enuncia Un puntero al puntero de interfaz, que, a su vez, apunta a la copia de esta interfaz [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) . La copia del enumerador mantiene su propio estado de enumeración por separado de este enumerador. Sin embargo, la posición inicial del cursor de la copia es la misma que la posición actual del cursor de este enumerador.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerFunctionEnum (Interfaz)](icorprofilerfunctionenum-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
