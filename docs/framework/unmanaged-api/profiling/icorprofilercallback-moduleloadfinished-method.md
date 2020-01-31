---
title: ICorProfilerCallback::ModuleLoadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
ms.openlocfilehash: 661229e5fbd5d106662f0e823a1753bd76c33311
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866174"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a>ICorProfilerCallback::ModuleLoadFinished (Método)
Notifica al generador de perfiles que un módulo ha terminado de cargarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a>Parameters  
 `moduleId`  
 de IDENTIFICADOR del módulo que ha terminado de cargarse.  
  
 `hrStatus`  
 de HRESULT que indica si el módulo se cargó correctamente.  
  
## <a name="remarks"></a>Notas  
 El valor de `moduleId` no es válido para una solicitud de información hasta que se llama al método `ModuleLoadFinished`.  
  
 Algunas partes de la carga del módulo pueden continuar después de la devolución de llamada de `ModuleLoadFinished`. Un valor HRESULT de error en `hrStatus` indica un error. Sin embargo, un valor HRESULT correcto en `hrStatus` solo indica que la primera parte de la carga del módulo se ha realizado correctamente.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
- [ModuleLoadStarted (método)](icorprofilercallback-moduleloadstarted-method.md)
