---
title: ICorProfilerCallback2::FinalizeableObjectQueued (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
ms.openlocfilehash: b9093f920a8c14247bc51471da3682c7e500afa4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865810"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a>ICorProfilerCallback2::FinalizeableObjectQueued (Método)
Notifica al generador de perfiles de código que un objeto con un finalizador se ha puesto en cola en el subproceso finalizador para la ejecución de su método `Finalize`.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a>Parameters  
 `finalizerFlags`  
 de Un valor de la enumeración [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) que describe aspectos del finalizador.  
  
 `objectID`  
 de IDENTIFICADOR del objeto que se ha puesto en la cola.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerCallback2 (interfaz)](icorprofilercallback2-interface.md)
