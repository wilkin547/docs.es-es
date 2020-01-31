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
ms.openlocfilehash: 6e6cc44c2f9028c0e26c4f933242cad93e3a98c3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866096"
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
  
## <a name="parameters"></a>Parameters  
 `objectId`  
 de IDENTIFICADOR del objeto que hace referencia a los objetos.  
  
 `classId`  
 de IDENTIFICADOR de la clase de la que el objeto especificado es una instancia de.  
  
 `cObjectRefs`  
 de El número de objetos a los que hace referencia el objeto especificado (es decir, el número de elementos de la matriz `objectRefIds`).  
  
 `objectRefIds`  
 de Matriz de identificadores de los objetos a los que hace referencia `objectId`.  
  
## <a name="remarks"></a>Notas  
 Se llama al método `ObjectReferences` para cada objeto restante en el montón después de que se haya completado una recolección de elementos no utilizados. Si el generador de perfiles devuelve un error de esta devolución de llamada, los servicios de generación de perfiles interrumpirán la invocación de esta devolución de llamada hasta la siguiente recolección de elementos no utilizados.  
  
 La devolución de llamada de `ObjectReferences` se puede usar junto con la devolución de llamada [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) para crear un gráfico de referencia de objeto completo para el tiempo de ejecución. El Common Language Runtime (CLR) garantiza que cada referencia de objeto se notifique solo una vez por el método `ObjectReferences`.  
  
 Los identificadores de objeto devueltos por `ObjectReferences` no son válidos durante la devolución de llamada, ya que la recolección de elementos no utilizados podría estar en medio de mover objetos. Por lo tanto, los perfiles no deben intentar inspeccionar objetos durante una llamada `ObjectReferences`. Cuando se llama a [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) , se completa la recolección de elementos no utilizados y se puede realizar la inspección de forma segura.  
  
 Un valor null `ClassId` indica que `objectId` tiene un tipo que se está descargando.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
