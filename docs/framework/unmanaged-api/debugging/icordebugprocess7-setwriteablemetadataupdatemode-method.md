---
description: 'Más información sobre: Icordebugprocess7 (:: Setwriteablemetadataupdatemode ((método)'
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
ms.openlocfilehash: 86ece68e160fbd61f44adcf495656c7b5d6b5153
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691268"
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
 Un valor de enumeración [writeablemetadataupdatemode (](writeablemetadataupdatemode-enumeration.md) que especifica si las actualizaciones en memoria de los metadatos en el proceso de destino son visibles ( `WriteableMetadataUpdateMode::AlwaysShowUpdates` ) o no ( `WriteableMetadataUpdateMode::LegacyCompatPolicy` ) en el depurador.  
  
## <a name="remarks"></a>Observaciones  

 Actualiza los metadatos del proceso de destino que proceden de Editar y Continuar, de un generador de perfiles o de <xref:System.Reflection.Emit?displayProperty=nameWithType>.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess7 (Interfaz)](icordebugprocess7-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
