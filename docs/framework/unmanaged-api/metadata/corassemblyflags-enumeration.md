---
title: CorAssemblyFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorAssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAssemblyFlags
helpviewer_keywords:
- CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d6ec37bbd8750c27a41b5f18180c7726cdcd483
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="corassemblyflags-enumeration"></a>CorAssemblyFlags (Enumeración)
Contiene valores que describen los metadatos aplicados a una compilación de ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`afPublicKey`|Indica que la referencia de ensamblado contiene la clave pública completa, sin valor de hash.|  
|`afPA_None`|Indica que la arquitectura de procesador no está especificada.|  
|`afPA_MSIL`|Indica que la arquitectura del procesador es neutra (PE32).|  
|`afPA_x86`|Indica que la arquitectura del procesador es x86 (PE32).|  
|`afPA_IA64`|Indica que la arquitectura del procesador es Itanium (PE32 +).|  
|`afPA_AMD64`|Indica que la arquitectura del procesador es AMD X64 (PE32 +).|  
|`afPA_ARM`|Indica que la arquitectura de procesador ARM (PE32).|  
|`afPA_NoPlatform`|Indica que el ensamblado es un ensamblado de referencia; es decir, se aplica a cualquier arquitectura pero no se puede ejecutar en cualquier arquitectura. Por lo tanto, la marca es el mismo que `afPA_Mask`.|  
|`afPA_Specified`|Indica que se deberían propagar los indicadores de la arquitectura de procesador para el `AssemblyRef` registro.|  
|`afPA_Mask`|Máscara que describe la arquitectura de procesador.|  
|`afPA_FullMask`|Especifica que se incluye la descripción de la arquitectura de procesador.|  
|`afPA_Shift`|Indica un recuento de desplazamientos en los indicadores de la arquitectura de procesador a y desde el índice.|  
|`afEnableJITcompileTracking`|Indica el valor correspondiente de la <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> de la <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afDisableJITcompileOptimizer`|Indica el valor correspondiente de la <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> de la <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afRetargetable`|Indica que el ensamblado puede redestinarse en tiempo de ejecución a un ensamblado de un publicador diferente.|  
|`afContentType_Mask`|Máscara que describe el tipo de contenido.|  
|`afContentType_Default`|Indica el tipo de contenido de forma predeterminada.|  
|`afContentType_WindowsRuntime`|Indica el [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo de contenido.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
