---
title: ICorProfilerCallback::ObjectAllocated (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
ms.openlocfilehash: 66643bbb8dbc914b2e0e48a7f0c87630fe95e5d3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445855"
---
# <a name="icorprofilercallbackobjectallocated-method"></a>ICorProfilerCallback::ObjectAllocated (Método)
Notifica al generador de perfiles que se ha asignado memoria en el montón para un objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a>Parámetros  
 `objectId`  
 de IDENTIFICADOR del objeto para el que se asignó la memoria.  
  
 `classId`  
 de IDENTIFICADOR de la clase de la que el objeto es una instancia de.  
  
## <a name="remarks"></a>Comentarios  
 No se llama al método `ObjectedAllocated` para las asignaciones de la pila o la memoria no administrada. El parámetro `classId` puede hacer referencia a una clase de código administrado que todavía no se ha cargado. El generador de perfiles recibirá una devolución de llamada de carga de clase para esa clase inmediatamente después de la devolución de llamada `ObjectAllocated`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ClassLoadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [ClassLoadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
