---
title: ICorProfilerCallback::ObjectReferences (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
ms.openlocfilehash: 4f8cfd912a3d6f66f5f2586a8942c7ce9bd52a63
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445890"
---
# <a name="icorprofilercallbackobjectreferences-method"></a>ICorProfilerCallback::ObjectReferences (Método)
Notifica al generador de perfiles sobre los objetos de memoria a los que hace referencia el objeto especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a>Parámetros  
 `objectId`  
 de IDENTIFICADOR del objeto que hace referencia a los objetos.  
  
 `classId`  
 de IDENTIFICADOR de la clase de la que el objeto especificado es una instancia de.  
  
 `cObjectRefs`  
 de El número de objetos a los que hace referencia el objeto especificado (es decir, el número de elementos de la matriz `objectRefIds`).  
  
 `objectRefIds`  
 de Matriz de identificadores de los objetos a los que hace referencia `objectId`.  
  
## <a name="remarks"></a>Comentarios  
 Se llama al método `ObjectReferences` para cada objeto restante en el montón después de que se haya completado una recolección de elementos no utilizados. Si el generador de perfiles devuelve un error de esta devolución de llamada, los servicios de generación de perfiles interrumpirán la invocación de esta devolución de llamada hasta la siguiente recolección de elementos no utilizados.  
  
 La devolución de llamada de `ObjectReferences` se puede usar junto con la devolución de llamada [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) para crear un gráfico de referencia de objeto completo para el tiempo de ejecución. El Common Language Runtime (CLR) garantiza que cada referencia de objeto se notifique solo una vez por el método `ObjectReferences`.  
  
 Los identificadores de objeto devueltos por `ObjectReferences` no son válidos durante la devolución de llamada, ya que la recolección de elementos no utilizados podría estar en medio de mover objetos. Por lo tanto, los perfiles no deben intentar inspeccionar objetos durante una llamada `ObjectReferences`. Cuando se llama a [ICorProfilerCallback2:: garbagecollectionfinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) , se completa la recolección de elementos no utilizados y se puede realizar la inspección de forma segura.  
  
 Un valor null `ClassId` indica que `objectId` tiene un tipo que se está descargando.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
