---
title: CorUnmanagedCallingConvention (Enumeración)
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
ms.openlocfilehash: 9d35f6b1928d714216b669704ec28e53895f6549
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699071"
---
# <a name="corunmanagedcallingconvention-enumeration"></a>CorUnmanagedCallingConvention (Enumeración)

Especifica las convenciones de llamada para el código no administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|Convención de llamada del lenguaje C.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|La Convención de llamada estándar.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|Convención de llamada "this".|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|Convención de llamada "rápida".|  
|`IMAGE_CEE_CS_CALLCONV_C`|No se utiliza.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|No se utiliza.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|No se utiliza.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|No se utiliza.|  
  
## <a name="remarks"></a>Comentarios  

 CLR no admite la Convención de llamada "Fast" en la .NET Framework versión 1,0.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
