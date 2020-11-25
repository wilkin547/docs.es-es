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
ms.openlocfilehash: bb4a8f7ff3ee54474804e3e5620dcce7c9f79fb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726618"
---
# <a name="cor_gc_reference-structure"></a>COR_GC_REFERENCE (Estructura)

Contiene información sobre un objeto que se va a recolectar con elemento no utilizado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`domain`|Puntero al dominio de aplicación al que pertenece el identificador u objeto. Su valor puede ser `null` .|  
|`location`|Una interfaz ICorDebugValue o ICorDebugReferenceValue que corresponde al objeto que se va a recolectar como elemento no utilizado.|  
|`type`|Un valor de enumeración de [corgcreferencetype (](corgcreferencetype-enumeration.md) que indica de dónde procede la raíz. Para obtener más información, vea la sección Comentarios.|  
|`extraData`|Datos adicionales sobre el objeto que se va a recolectar como elemento no utilizado. Esta información depende del origen del objeto, como se indica en el `type` campo. Para obtener más información, vea la sección Comentarios.|  
  
## <a name="remarks"></a>Comentarios  

 El `type` campo es un valor de enumeración [corgcreferencetype (](corgcreferencetype-enumeration.md) que indica de dónde procede la referencia. Un `COR_GC_REFERENCE` valor determinado puede reflejar cualquiera de los siguientes tipos de objetos administrados:  
  
- Objetos de todas las pilas administradas ( `CorGCReferenceType.CorReferenceStack` ). Esto incluye las referencias dinámicas en el código administrado, así como los objetos creados por el Common Language Runtime.  
  
- Objetos de la tabla de identificadores ( `CorGCReferenceType.CorHandle*` ). Esto incluye referencias seguras ( `HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT` ) y variables estáticas en un módulo.  
  
- Objetos de la cola del finalizador ( `CorGCReferenceType.CorReferenceFinalizer` ). Los objetos raíces de la cola del finalizador hasta que se haya ejecutado el finalizador.  
  
 El `extraData` campo contiene datos adicionales en función del origen (o tipo) de la referencia. Los valores posibles son:  
  
- `DependentSource`. Si `type` es `CorGCREferenceType.CorHandleStrongDependent` , este campo es el objeto que, si está activo, es la raíz del objeto en el que se va a realizar la recolección de elementos no utilizados `COR_GC_REFERENCE.Location` .  
  
- `RefCount`. Si `type` es `CorGCREferenceType.CorHandleStrongRefCount` , este campo es el recuento de referencias del identificador.  
  
- `Size`. Si `type` es `CorGCREferenceType.CorHandleStrongSizedByref` , este campo es el último tamaño del árbol de objetos para el que el recolector de elementos no utilizados calculó las raíces del objeto. Tenga en cuenta que este cálculo no está necesariamente actualizado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
