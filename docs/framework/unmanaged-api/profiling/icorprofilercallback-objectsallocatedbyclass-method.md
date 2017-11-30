---
title: "ICorProfilerCallback::ObjectsAllocatedByClass (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectsAllocatedByClass
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 28c0ff537a5b2133bdeb1db8aeadf5545d8dfd0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
