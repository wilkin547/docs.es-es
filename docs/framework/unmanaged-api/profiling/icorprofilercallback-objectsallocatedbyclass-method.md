---
description: 'Más información sobre: ICorProfilerCallback:: ObjectsAllocatedByClass ((método)'
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
ms.openlocfilehash: df9f3dde27664de7db4afb264b221f640753ddb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745065"
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
 de Tamaño de las `classIds` matrices y `cObjects` .  
  
 `classIds`  
 de Matriz de identificadores de clase, donde cada identificador especifica una clase con una o más instancias.  
  
 `cObjects`  
 de Matriz de enteros, donde cada entero especifica el número de instancias de la clase correspondiente en la `classIds` matriz.  
  
## <a name="remarks"></a>Observaciones  

 Las `classIds` `cObjects` matrices y son matrices paralelas. Por ejemplo, `classIds[i]` y `cObjects[i]` hacen referencia a la misma clase. Si no se ha creado ninguna instancia de una clase desde la recolección de elementos no utilizados anterior, se omite la clase. La `ObjectsAllocatedByClass` devolución de llamada no notificará los objetos asignados en el montón de objetos grandes.  
  
 Los números devueltos por `ObjectsAllocatedByClass` son solo estimaciones. Para los recuentos exactos, utilice [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md).  
  
 La `classIds` matriz puede contener una o varias entradas nulas si la `cObjects` matriz correspondiente tiene tipos que se están descargando.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
