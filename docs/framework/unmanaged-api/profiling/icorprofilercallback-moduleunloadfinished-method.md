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
ms.openlocfilehash: 40cb666c47c690dc930ec2cb7f6c89662464780e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445910"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a>ICorProfilerCallback::ModuleUnloadFinished (Método)
Notifica al generador de perfiles que un módulo ha terminado de descargarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleId`  
 de IDENTIFICADOR del módulo que se ha descargado.  
  
 `hrStatus`  
 de HRESULT que indica si el módulo se ha descargado correctamente.  
  
## <a name="remarks"></a>Comentarios  
 El valor de `moduleId` no es válido para una solicitud de información después de que se devuelva el método [ICorProfilerCallback:: ModuleUnloadStarted (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) .  
  
 Algunas partes de la descarga de la clase podrían continuar después de la devolución de llamada de `ModuleUnloadFinished`. Un valor HRESULT de error en `hrStatus` indica un error. Sin embargo, un valor HRESULT correcto en `hrStatus` solo indica que la primera parte de la descarga del módulo se ha realizado correctamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
