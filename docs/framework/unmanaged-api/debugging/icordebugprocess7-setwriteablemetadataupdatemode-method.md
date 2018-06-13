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
ms.openlocfilehash: a67f93a3f3f75b89bc3f0240995471bc0bf44992
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419762"
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
  
#### <a name="parameters"></a>Parámetros  
 `flags`  
 A [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) valor de enumeración que especifica si las actualizaciones en memoria de metadatos en el proceso de destino son visibles (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) o no está visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) para el depurador.  
  
## <a name="remarks"></a>Comentarios  
 Actualiza los metadatos del proceso de destino que proceden de Editar y Continuar, de un generador de perfiles o de <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugProcess7 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
