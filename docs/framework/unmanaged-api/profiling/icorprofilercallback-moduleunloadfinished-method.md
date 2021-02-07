---
description: 'Más información sobre: ICorProfilerCallback:: Moduleunloadfinished ((método)'
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
ms.openlocfilehash: 32182beb879813a4e60f69494bd93799c0f66e1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745263"
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
  
## <a name="remarks"></a>Observaciones  

 El valor de `moduleId` no es válido para una solicitud de información después de que el método [ICorProfilerCallback:: ModuleUnloadStarted (](icorprofilercallback-moduleunloadstarted-method.md) devuelva.  
  
 Algunas partes de la descarga de la clase podrían continuar después de la `ModuleUnloadFinished` devolución de llamada. Un valor HRESULT de error en `hrStatus` indica un error. Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la descarga del módulo se ha realizado correctamente.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
