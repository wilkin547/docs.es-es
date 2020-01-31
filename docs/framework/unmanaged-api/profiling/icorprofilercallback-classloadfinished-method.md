---
title: ICorProfilerCallback::ClassLoadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
ms.openlocfilehash: e0ff90f99c1127b5a4626f47514ba7099b5d48af
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866603"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a>ICorProfilerCallback::ClassLoadFinished (Método)
Notifica al generador de perfiles que se ha terminado de cargar una clase.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a>Parameters

- `classId`

  \[en] identifica la clase que se cargó.

- `hrStatus`

  \[in] un valor HRESULT que indica si la clase se cargó correctamente.

## <a name="remarks"></a>Notas  
 El valor de `classId` no es válido para una solicitud de información hasta que se llama al método `ClassLoadFinished`.  
  
 Algunas partes de la carga de la clase podrían continuar después de la devolución de llamada de `ClassLoadFinished`. Un valor HRESULT de error en `hrStatus` indica un error. Sin embargo, un valor HRESULT correcto en `hrStatus` solo indica que la primera parte de la carga de la clase se ha realizado correctamente.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
- [ClassLoadStarted (método)](icorprofilercallback-classloadstarted-method.md)
