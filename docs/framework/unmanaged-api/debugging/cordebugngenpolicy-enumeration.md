---
title: CorDebugNGenPolicy (Enumeración)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
ms.openlocfilehash: 036d3f12b38c19259fefaba674d0f9025a58d688
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795760"
---
# <a name="cordebugngenpolicy-enumeration"></a>CorDebugNGenPolicy (Enumeración)
Proporciona un valor que determina si un depurador carga imágenes nativas (NGen) desde la caché de imágenes nativas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a>Members  
  
|Nombre del miembro|Descripción|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|En una aplicación de la tienda Windows 8. x, el uso de imágenes de la memoria caché de imágenes nativas local está deshabilitado. En una aplicación de escritorio, este valor no tiene ningún efecto.|  
  
## <a name="remarks"></a>Comentarios  
 El `CorDebugNGENPolicy` método [ICorDebugProcess5:: enablengenpolicy (](icordebugprocess5-enablengenpolicy-method.md) usa la enumeración. Deshabilitar el uso de imágenes de la memoria caché de imágenes nativas local proporciona una experiencia de depuración coherente asegurándose de que el depurador carga imágenes compiladas por JIT depurables en lugar de imágenes nativas optimizadas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
