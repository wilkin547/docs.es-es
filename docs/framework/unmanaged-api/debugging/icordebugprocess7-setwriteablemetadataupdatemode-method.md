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
ms.openlocfilehash: 35767529d9433764b7eed0b3b4acdd806f399962
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792181"
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
  
## <a name="parameters"></a>Parameters  
 `flags`  
 Un valor de enumeración [writeablemetadataupdatemode (](writeablemetadataupdatemode-enumeration.md) que especifica si las actualizaciones en memoria de los metadatos en el proceso de destino son visibles (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) o no visibles (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) en el depurador.  
  
## <a name="remarks"></a>Notas  
 Actualiza los metadatos del proceso de destino que proceden de Editar y Continuar, de un generador de perfiles o de <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess7 (interfaz)](icordebugprocess7-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
