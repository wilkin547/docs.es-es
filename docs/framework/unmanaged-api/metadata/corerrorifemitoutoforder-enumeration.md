---
title: CorErrorIfEmitOutOfOrder (Enumeración)
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
ms.openlocfilehash: fec049297bfa12d86cb2a7f7950e84ae540832b1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007447"
---
# <a name="corerrorifemitoutoforder-enumeration"></a>CorErrorIfEmitOutOfOrder (Enumeración)
Contiene valores de marca que indican las condiciones en las que se debe generar un mensaje de error cuando los metadatos se emiten sin orden.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|Indica el comportamiento predeterminado, que no genera mensajes de error.|  
|`MDErrorOutOfOrderNone`|Indica que el compilador no debe generar mensajes de error.|  
|`MDErrorOutOfOrderAll`|Indica que el compilador debe generar un mensaje de error cuando un campo, una propiedad, un evento, un método o un parámetro se emiten de forma desordenada.|  
|`MDMethodOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando un método se emite de forma desordenada.|  
|`MDFieldOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando un campo se emite de forma desordenada.|  
|`MDParamOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando un parámetro se emite de forma desordenada.|  
|`MDPropertyOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando una propiedad se emite de forma desordenada.|  
|`MDEventOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando se emite un evento sin orden.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
