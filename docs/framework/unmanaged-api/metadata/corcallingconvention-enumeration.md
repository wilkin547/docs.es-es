---
description: 'Más información sobre: enumeración Corcallingconvention ('
title: CorCallingConvention (Enumeración)
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
ms.openlocfilehash: 2e823fe3566ef7a54f759cd5debbbd7d5dcf3ceb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678450"
---
# <a name="corcallingconvention-enumeration"></a>CorCallingConvention (Enumeración)

Contiene valores que describen los tipos de convenciones de llamada que se realizan en código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|Indica una Convención de llamada predeterminada.|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|Indica que el método toma un número variable de parámetros.|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|Indica que la llamada es a un campo.|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|Indica que la llamada es a un método local.|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|Indica que la llamada a es una propiedad.|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|Indica que la llamada no está administrada.|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|Indica una creación de instancias de método genérico.|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|Indica una llamada PInvoke de 64 bits a un método que toma un número variable de parámetros.|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|Describe un valor de 4 bits no válido.|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|Indica que la Convención de llamada se describe en los cuatro bits inferiores.|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|Indica que el bit superior describe un `this` parámetro.|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|Indica que un `this` parámetro se describe explícitamente en la firma.|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|Indica una firma de método genérico con un número explícito de argumentos de tipo. Esto precede a un recuento de parámetros ordinarios.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
