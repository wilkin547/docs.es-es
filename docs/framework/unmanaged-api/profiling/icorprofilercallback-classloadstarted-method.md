---
title: ICorProfilerCallback::ClassLoadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
ms.openlocfilehash: c9faff2d616d03d823c80fb2d9cd71d5fd5759ae
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445084"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a>ICorProfilerCallback::ClassLoadStarted (Método)
Notifica al generador de perfiles que se está cargando una clase.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a>Parámetros  
 `classId`  
 de Identifica la clase que se está cargando.  
  
## <a name="remarks"></a>Comentarios  
 El valor de `classId` no es válido para una solicitud de información hasta que se llama al método [ICorProfilerCallback:: classloadfinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
