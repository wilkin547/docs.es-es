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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9206fbde13f457d4b2e2941ee744d645c6df9774
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781993"
---
# <a name="corunmanagedcallingconvention-enumeration"></a>CorUnmanagedCallingConvention (Enumeración)
Especifica las convenciones de llamada para código no administrado.  
  
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
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|La convención de llamada de lenguaje C.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|La convención de llamada estándar.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|"This" convención de llamada.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|La convención de llamada "rápida".|  
|`IMAGE_CEE_CS_CALLCONV_C`|No se utiliza.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|No se utiliza.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|No se utiliza.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|No se utiliza.|  
  
## <a name="remarks"></a>Comentarios  
 El CLR no admite la convención de llamada "rápida" en la versión 1.0 de .NET Framework.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
