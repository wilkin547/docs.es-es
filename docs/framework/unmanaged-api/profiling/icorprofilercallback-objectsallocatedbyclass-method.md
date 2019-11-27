---
title: ICorProfilerCallback::ObjectsAllocatedByClass (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
ms.openlocfilehash: 9ba021ec223d00e57081567b76f70f59768e6b9a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445856"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>ICorProfilerCallback::ObjectsAllocatedByClass (Método)
Notifica al generador de perfiles el número de instancias de cada clase especificada que se han creado desde la última recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a>Parámetros  
 `cClassCount`  
 de Tamaño de las matrices de `classIds` y `cObjects`.  
  
 `classIds`  
 de Matriz de identificadores de clase, donde cada identificador especifica una clase con una o más instancias.  
  
 `cObjects`  
 de Matriz de enteros, donde cada entero especifica el número de instancias de la clase correspondiente en la matriz de `classIds`.  
  
## <a name="remarks"></a>Comentarios  
 Las matrices `classIds` y `cObjects` son matrices paralelas. Por ejemplo, `classIds[i]` y `cObjects[i]` hacen referencia a la misma clase. Si no se ha creado ninguna instancia de una clase desde la recolección de elementos no utilizados anterior, se omite la clase. La devolución de llamada de `ObjectsAllocatedByClass` no notificará los objetos asignados en el montón de objetos grandes.  
  
 Los números devueltos por `ObjectsAllocatedByClass` son solo estimaciones. Para los recuentos exactos, utilice [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).  
  
 La matriz de `classIds` puede contener una o varias entradas nulas si la matriz de `cObjects` correspondiente tiene tipos que se están descargando.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
