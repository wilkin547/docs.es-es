---
description: 'Más información sobre: ICorProfilerCallback:: Classunloadfinished ((método)'
title: ICorProfilerCallback::ClassUnloadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
ms.openlocfilehash: ae1ef56a1eb3b9b45c2165ecceb0af826cc7a2ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657741"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a>ICorProfilerCallback::ClassUnloadFinished (Método)

Notifica al generador de perfiles que una clase ha terminado de descargarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a>Parámetros

- `classId`

  \[in] identifica la clase que se ha descargado.

- `hrStatus`

  \[in] un valor HRESULT que indica si la clase se ha descargado correctamente.
  
## <a name="remarks"></a>Observaciones  

 Algunas partes de la descarga de la clase podrían continuar después de la `ClassUnloadFinished` devolución de llamada. Un valor HRESULT de error en `hrStatus` indica un error. Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la descarga de la clase se ha realizado correctamente.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método ClassUnloadStarted](icorprofilercallback-classunloadstarted-method.md)
