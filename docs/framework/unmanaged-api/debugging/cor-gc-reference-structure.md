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
ms.openlocfilehash: e22269b76c230f702f4712298fddcd0df1fde50d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179325"
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
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`domain`|Puntero al dominio de aplicación al que pertenece el identificador o el objeto. Su valor `null`puede ser .|  
|`location`|Un ICorDebugValue o un ICorDebugReferenceValue interfaz que corresponde al objeto que se va a recopilar como elementos no utilizados.|  
|`type`|Un valor de enumeración [CorGCReferenceType](corgcreferencetype-enumeration.md) que indica de dónde procede la raíz. Para obtener más información, vea la sección Comentarios.|  
|`extraData`|Datos adicionales sobre el objeto que se va a recopilar. Esta información depende del origen del objeto, `type` como se indica en el campo. Para obtener más información, vea la sección Comentarios.|  
  
## <a name="remarks"></a>Observaciones  
 El `type` campo es un valor de enumeración [CorGCReferenceType](corgcreferencetype-enumeration.md) que indica de dónde procede la referencia. Un `COR_GC_REFERENCE` valor determinado puede reflejar cualquiera de los siguientes tipos de objetos administrados:  
  
- Objetos de todas`CorGCReferenceType.CorReferenceStack`las pilas administradas ( ). Esto incluye referencias en vivo en código administrado, así como objetos creados por Common Language Runtime.  
  
- Objetos de la`CorGCReferenceType.CorHandle*`tabla de identificadores ( ). Esto incluye referencias`HNDTYPE_STRONG` `HNDTYPE_REFCOUNT`seguras ( y ) y variables estáticas en un módulo.  
  
- Objetos de la`CorGCReferenceType.CorReferenceFinalizer`cola del finalizador ( ). El finalizador enraiza los objetos hasta que se ha ejecutado el finalizador.  
  
 El `extraData` campo contiene datos adicionales en función del origen (o tipo) de la referencia. Los valores posibles son:  
  
- `DependentSource`. Si `type` es `CorGCREferenceType.CorHandleStrongDependent`, este campo es el objeto que, si está vivo, arraiga el objeto que se va a recopilar como elementos no utilizados en `COR_GC_REFERENCE.Location`.  
  
- `RefCount`. Si `type` es `CorGCREferenceType.CorHandleStrongRefCount`, este campo es el recuento de referencias del identificador.  
  
- `Size`. Si `type` es `CorGCREferenceType.CorHandleStrongSizedByref`, este campo es el último tamaño del árbol de objetos para el que el recolector de elementos no utilizados calculó las raíces del objeto. Tenga en cuenta que este cálculo no está necesariamente actualizado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
