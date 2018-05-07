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
ms.openlocfilehash: d4e9d03dcf4603f9470f8f2509050eb6f875746a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="corerrorifemitoutoforder-enumeration"></a>CorErrorIfEmitOutOfOrder (Enumeración)
Contiene valores de marca que indican las condiciones en las que se debe generar un mensaje de error cuando los metadatos se emiten sin orden.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|`MDErrorOutOfOrderDefault`|Indica el comportamiento predeterminado, que no generan mensajes de error.|  
|`MDErrorOutOfOrderNone`|Indica que el compilador no debe generar mensajes de error.|  
|`MDErrorOutOfOrderAll`|Indica que el compilador debe generar un mensaje de error cuando un campo, propiedad, evento, método o parámetro se emite sin orden.|  
|`MDMethodOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando un método no se emite en el orden correcto.|  
|`MDFieldOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando un campo no se emite en el orden correcto.|  
|`MDParamOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando un parámetro no se emite en el orden correcto.|  
|`MDPropertyOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando una propiedad se emite sin orden.|  
|`MDEventOutOfOrder`|Indica que el compilador debe generar un mensaje de error cuando se genera un evento fuera de servicio.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
