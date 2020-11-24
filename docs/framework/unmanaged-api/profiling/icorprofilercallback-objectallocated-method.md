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
ms.openlocfilehash: fda234a6a280aeea1f497ad195d6d41efb6aa951
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674351"
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

 `ObjectedAllocated`No se llama al método para las asignaciones de la pila o la memoria no administrada. El `classId` parámetro puede hacer referencia a una clase de código administrado que todavía no se ha cargado. El generador de perfiles recibirá una devolución de llamada de carga de clase para esa clase inmediatamente después de la `ObjectAllocated` devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método ClassLoadStarted](icorprofilercallback-classloadstarted-method.md)
- [Método ClassLoadFinished](icorprofilercallback-classloadfinished-method.md)
