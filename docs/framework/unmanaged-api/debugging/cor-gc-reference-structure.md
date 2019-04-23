---
title: COR_GC_REFERENCE (Estructura)
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1e31e95473136bf7e7c196eacc278fa8a1caab2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093662"
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
|`domain`|Un puntero al dominio de aplicación a la que pertenece el objeto o identificador. Su valor puede ser `null`.|  
|`location`|ICorDebugValue o una ICorDebugReferenceValue (interfaz) que se corresponde con el objeto que se recopilan de elementos no utilizados.|  
|`type`|Un [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valor de enumeración que indica de dónde procede la raíz. Para obtener más información, vea la sección Comentarios.|  
|`extraData`|Datos adicionales sobre el objeto que se recopilan de elementos no utilizados. Esta información depende del origen del objeto, tal y como indica la `type` campo. Para obtener más información, vea la sección Comentarios.|  
  
## <a name="remarks"></a>Comentarios  
 El `type` campo es un [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valor de enumeración que indica de dónde procede la referencia. Una determinada `COR_GC_REFERENCE` valor puede reflejar cualquiera de los siguientes tipos de objetos administrados:  
  
-   Los objetos de todas las pilas administradas (`CorGCReferenceType.CorReferenceStack`). Esto incluye referencias activas en código administrado, así como los objetos creados por common language runtime.  
  
-   Objetos de la tabla de identificadores (`CorGCReferenceType.CorHandle*`). Esto incluye las referencias fuertes (`HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT`) y las variables estáticas en un módulo.  
  
-   Los objetos de la cola del finalizador (`CorGCReferenceType.CorReferenceFinalizer`). La cola del finalizador raíces objetos hasta que se ha ejecutado el finalizador.  
  
 El `extraData` campo contiene datos adicionales según el origen (o tipo) de la referencia. Los valores posibles son:  
  
-   `DependentSource`. Si el `type` es `CorGCREferenceType.CorHandleStrongDependent`, este campo es el objeto que, si se activa, raíces para recopilar los elementos no utilizados en el objeto de `COR_GC_REFERENCE.Location`.  
  
-   `RefCount`. Si el `type` es `CorGCREferenceType.CorHandleStrongRefCount`, este campo es el recuento de referencias del identificador.  
  
-   `Size`. Si el `type` es `CorGCREferenceType.CorHandleStrongSizedByref`, este campo es el último tamaño del árbol de objetos para el que el recolector de elementos no utilizados calcula las raíces de objeto. Tenga en cuenta que este cálculo no es necesariamente actualizado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
