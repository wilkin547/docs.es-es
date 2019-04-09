---
title: ICorDebugProcess7::SetWriteableMetadataUpdateMode (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94e2f1c13c91c50daa5730898adf0aedf00f6579
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092622"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a>ICorDebugProcess7::SetWriteableMetadataUpdateMode (Método)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Configura cómo el depurador controla las actualizaciones en memoria de los metadatos dentro del proceso de destino.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `flags`  
 Un [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) valor de enumeración que especifica si las actualizaciones en memoria de metadatos en el proceso de destino son visibles (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) o no es visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) al depurador.  
  
## <a name="remarks"></a>Comentarios  
 Actualiza los metadatos del proceso de destino que proceden de Editar y Continuar, de un generador de perfiles o de <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess7 (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)
- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
