---
title: COR_GC_REFERENCE (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_REFERENCE
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_GC_REFERENCE
helpviewer_keywords: COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a86604febb7641eef147608e564a27883fdc4bec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreference-structure"></a>COR_GC_REFERENCE (Estructura)
Contiene información sobre un objeto que se va a recolectar con elemento no utilizado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`domain`|Un puntero al dominio de aplicación a la que pertenece el identificador o el objeto. Su valor puede ser `null`.|  
|`location`|ICorDebugValue o en una ICorDebugReferenceValue (interfaz) que corresponde al objeto al que se recolectarán como elementos no utilizados.|  
|`type`|A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valor de enumeración que indica de dónde procede la raíz. Para obtener más información, vea la sección Comentarios.|  
|`extraData`|Datos adicionales sobre el objeto al que se recolectarán como elementos no utilizados. Esta información depende del origen del objeto, tal y como indica la `type` campo. Para obtener más información, vea la sección Comentarios.|  
  
## <a name="remarks"></a>Comentarios  
 El `type` campo es un [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valor de enumeración que indica de dónde procede la referencia. Un determinado `COR_GC_REFERENCE` valor puede reflejar cualquiera de los siguientes tipos de objetos administrados:  
  
-   Objetos de todas las pilas administradas (`CorGCReferenceType.CorReferenceStack`). Esto incluye referencias directas en código administrado, así como los objetos creados por common language runtime.  
  
-   Objetos de la tabla de identificadores (`CorGCReferenceType.CorHandle*`). Esto incluye las referencias fuertes (`HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT`) y las variables estáticas en un módulo.  
  
-   Objetos de la cola del finalizador (`CorGCReferenceType.CorReferenceFinalizer`). La cola del finalizador raíces de objetos hasta que ha ejecutado el finalizador.  
  
 El `extraData` campo contiene datos adicionales según el origen (o tipo) de la referencia. Los valores posibles son:  
  
-   `DependentSource`. Si el `type` es `CorGCREferenceType.CorHandleStrongDependent`, este campo es el objeto que, si se activa, raíces del objeto para que la recolección en `COR_GC_REFERENCE.Location`.  
  
-   `RefCount`. Si el `type` es `CorGCREferenceType.CorHandleStrongRefCount`, este campo es el recuento de referencias del identificador.  
  
-   `Size`. Si el `type` es `CorGCREferenceType.CorHandleStrongSizedByref`, este campo es el último tamaño del árbol de objetos para el que el recolector de elementos no utilizados calcula las raíces de objeto. Tenga en cuenta que este cálculo no es necesariamente actualizado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
