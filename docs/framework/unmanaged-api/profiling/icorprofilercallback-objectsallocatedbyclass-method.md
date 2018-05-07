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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78dde5c50666333c02c8c1a9a167e17af3f40341
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>ICorProfilerCallback::ObjectsAllocatedByClass (Método)
Notifica al generador de perfiles sobre el número de instancias de cada clase especificada que se han creado desde la recolección de elementos no utilizados más reciente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cClassCount`  
 [in] El tamaño de la `classIds` y `cObjects` matrices.  
  
 `classIds`  
 [in] Una matriz de identificadores, donde cada identificador especifica una clase con una o varias instancias de clases.  
  
 `cObjects`  
 [in] Una matriz de enteros, donde cada entero que especifica el número de instancias de la clase correspondiente en el `classIds` matriz.  
  
## <a name="remarks"></a>Comentarios  
 El `classIds` y `cObjects` son matrices paralelas. Por ejemplo, `classIds[i]` y `cObjects[i]` hacen referencia a la misma clase. Si no se ha creado ninguna instancia de una clase desde la recopilación de elementos no utilizados anterior, se omite la clase. El `ObjectsAllocatedByClass` devolución de llamada no informarán los objetos asignados en el montón de objetos grandes.  
  
 Los números notifican por `ObjectsAllocatedByClass` sólo son estimaciones. Para obtener recuentos exactos, utilice [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).  
  
 El `classIds` matriz puede contener una o varias entradas null si el correspondiente `cObjects` matriz tiene tipos que se están descargando.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
