---
title: "CorUnmanagedCallingConvention (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorUnmanagedCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorUnmanagedCallingConvention
helpviewer_keywords: CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f66cb036de8450d4c1b3431b92487260956d47f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corunmanagedcallingconvention-enumeration"></a>CorUnmanagedCallingConvention (Enumeración)
Especifica las convenciones de llamada de código no administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|La convención de llamada de lenguaje C.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|La convención de llamada estándar.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|"Este" convención de llamada.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|La convención de llamada "rápida".|  
|`IMAGE_CEE_CS_CALLCONV_C`|No usado.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|No usado.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|No usado.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|No usado.|  
  
## <a name="remarks"></a>Comentarios  
 El CLR no admite la convención de llamada "fast" en la versión 1.0 de .NET Framework.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
