---
description: 'Más información sobre: ICorProfilerCallback:: Assemblyunloadstarted ((método)'
title: ICorProfilerCallback::AssemblyUnloadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
ms.openlocfilehash: e9c72d481df7242f305b5efa6f747866984b31f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657845"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a>ICorProfilerCallback::AssemblyUnloadStarted (Método)

Notifica al generador de perfiles que se está descargando un ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a>Parámetros

- `assemblyId`

  \[en] identifica el ensamblado que se está descargando.

## <a name="remarks"></a>Observaciones  

 El valor de `assemblyId` no es válido para una solicitud de información después de que se `AssemblyUnloadStarted` devuelva el método; esta es la última oportunidad del generador de perfiles para obtener información sobre este ensamblado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método AssemblyUnloadFinished](icorprofilercallback-assemblyunloadfinished-method.md)
