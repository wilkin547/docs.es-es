---
title: ICorProfilerCallback::ModuleUnloadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadStarted
helpviewer_keywords:
- ModuleUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadStarted method [.NET Framework profiling]
ms.assetid: 2debcaab-6005-4245-afdb-4268bb7e74bd
topic_type:
- apiref
ms.openlocfilehash: 12d5f7e073337af6034b8f313a2e0161620a65ea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720963"
---
# <a name="icorprofilercallbackmoduleunloadstarted-method"></a>ICorProfilerCallback::ModuleUnloadStarted (Método)

Notifica al generador de perfiles que se está descargando un módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ModuleUnloadStarted(  
    [in] ModuleID moduleId);
```  
  
## <a name="parameters"></a>Parámetros  

 `moduleId`  
 de IDENTIFICADOR del módulo que se está descargando.  
  
## <a name="remarks"></a>Comentarios  

 El valor de `moduleId` no es válido para una solicitud de información después de que se `ModuleUnloadStarted` devuelva el método; esta es la última oportunidad del generador de perfiles para obtener información acerca de este módulo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método ModuleUnloadFinished](icorprofilercallback-moduleunloadfinished-method.md)
