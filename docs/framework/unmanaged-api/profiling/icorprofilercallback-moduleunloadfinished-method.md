---
title: ICorProfilerCallback::ModuleUnloadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a4637ac7466a575c94f8244168576c4a5542689
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a>ICorProfilerCallback::ModuleUnloadFinished (Método)
Notifica al generador de perfiles que un módulo ha terminado de descargarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `moduleId`  
 [in] El identificador del módulo que se descargó.  
  
 `hrStatus`  
 [in] Un valor HRESULT que indica si el módulo se descargó correctamente.  
  
## <a name="remarks"></a>Comentarios  
 El valor de `moduleId` no es válido para una solicitud de información después de la [ICorProfilerCallback:: ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) devuelve del método.  
  
 Algunas partes de la descarga de la clase podrían continuar después de la `ModuleUnloadFinished` devolución de llamada. Un valor HRESULT de error en `hrStatus` indica un error. Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de la descarga del módulo se ha realizado correctamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
