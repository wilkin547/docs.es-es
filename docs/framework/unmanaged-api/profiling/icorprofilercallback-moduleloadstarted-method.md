---
title: ICorProfilerCallback::ModuleLoadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
ms.openlocfilehash: a04f72fff9a88c8689821131b08b35500c23b3d9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503359"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a>ICorProfilerCallback::ModuleLoadStarted (Método)
Notifica al generador de perfiles que se está cargando un módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleId`  
 de IDENTIFICADOR del módulo que se está cargando.  
  
## <a name="remarks"></a>Comentarios  
 El valor de `moduleId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
