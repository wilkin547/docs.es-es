---
title: WriteableMetadataUpdateMode (Enumeración)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b49b63049d33c41757db1abae82ed2a4e266b42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572219"
---
# <a name="writeablemetadataupdatemode-enumeration"></a>WriteableMetadataUpdateMode (Enumeración)
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
  
## <a name="remarks"></a>Comentarios  
 Un miembro de la `WriteableMetadataUpdateMode` enumeración puede pasarse a la [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) método para controlar si las actualizaciones en memoria a los metadatos en el proceso de destino son visibles para el depurador.  
  
 La opción `LegacyCompatPolicy` aplica el mismo comportamiento que en las versiones de .NET Framework anteriores a la 4.5.2. Esto suele significar que los metadatos de las actualizaciones no son visibles. Sin embargo, las llamadas a varios métodos de depuración obligan implícitamente al depurador a hacer las actualizaciones visibles. Por ejemplo, si el depurador pasa [ICorDebugILFrame:: GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) el índice de una variable no se encuentra en los metadatos original del método, todos los metadatos para el módulo se actualiza a una instantánea que coincida con el estado actual de la proceso. En otras palabras, con la opción `LegacyCompatPolicy`, el depurador podría ver ninguna, algunas o todas las actualizaciones de metadatos disponibles, según cómo use otras partes de la API de depuración no administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [SetWriteableMetadataUpdateMode (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
