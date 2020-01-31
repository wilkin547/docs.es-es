---
title: WriteableMetadataUpdateMode (enumeración)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
ms.openlocfilehash: 5c3f2f7a9c0804b71c9c8a52bb032aca7c03825e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790292"
---
# <a name="writeablemetadataupdatemode-enumeration"></a>WriteableMetadataUpdateMode (enumeración)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Proporciona valores que especifican si las actualizaciones en memoria de los metadatos son visibles para un depurador.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a>Miembros  
  
|Nombre de miembro|Descripción|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|Mantiene la compatibilidad con versiones anteriores de .NET Framework al hacer que las actualizaciones en memoria de los metadatos sean visibles. Vea la sección Comentarios para obtener más información.|  
|`AlwaysShowUpdates`|Hace que las actualizaciones en memoria de los metadatos sean visibles para el depurador.|  
  
## <a name="remarks"></a>Notas  
 Un miembro de la enumeración `WriteableMetadataUpdateMode` se puede pasar al método [setwriteablemetadataupdatemode (](icordebugprocess7-setwriteablemetadataupdatemode-method.md) para controlar si las actualizaciones en memoria de los metadatos en el proceso de destino son visibles para el depurador.  
  
 La opción `LegacyCompatPolicy` aplica el mismo comportamiento que en las versiones de .NET Framework anteriores a la 4.5.2. Esto suele significar que los metadatos de las actualizaciones no son visibles. Sin embargo, las llamadas a varios métodos de depuración obligan implícitamente al depurador a hacer las actualizaciones visibles. Por ejemplo, si el depurador pasa [ICorDebugILFrame:: getlocalvariable (](icordebugilframe-getlocalvariable-method.md) , el índice de una variable no se encuentra en los metadatos originales del método, todos los metadatos del módulo se actualizan a una instantánea que coincide con el estado actual del proceso. En otras palabras, con la opción `LegacyCompatPolicy`, el depurador podría ver ninguna, algunas o todas las actualizaciones de metadatos disponibles, según cómo use otras partes de la API de depuración no administrada.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
- [SetWriteableMetadataUpdateMode (método)](icordebugprocess7-setwriteablemetadataupdatemode-method.md)
