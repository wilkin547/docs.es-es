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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16f6d7bf6fa1730d50cfe81526817e492a453dad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781984"
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
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|Indica el comportamiento predeterminado, que no generan mensajes de error.|  
|`MDErrorOutOfOrderNone`|Indica que el compilador no debe generar mensajes de error.|  
|`MDErrorOutOfOrderAll`|Indica que el compilador debe generar un mensaje de error cuando un campo, propiedad, evento, método o parámetro que se emite sin orden.|  
|`MDMethodOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando un método que se emite sin orden.|  
|`MDFieldOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando un campo se emite sin orden.|  
|`MDParamOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando un parámetro que se emite sin orden.|  
|`MDPropertyOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando una propiedad se emite sin orden.|  
|`MDEventOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando se emite un evento en el orden correcto.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
