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
ms.openlocfilehash: 481fc2c40331e31f6a018d012fb2b2543d4fd9b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503372"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a>ICorProfilerCallback::ModuleLoadFinished (Método)
Notifica al generador de perfiles que un módulo ha terminado de cargarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleId`  
 de IDENTIFICADOR del módulo que ha terminado de cargarse.  
  
 `hrStatus`  
 de HRESULT que indica si el módulo se cargó correctamente.  
  
## <a name="remarks"></a>Comentarios  
 El valor de `moduleId` no es válido para una solicitud de información hasta que `ModuleLoadFinished` se llama al método.  
  
 Algunas partes de la carga del módulo pueden continuar después de la `ModuleLoadFinished` devolución de llamada. Un valor HRESULT de error en `hrStatus` indica un error. Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la carga del módulo se ha realizado correctamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método ModuleLoadStarted](icorprofilercallback-moduleloadstarted-method.md)
