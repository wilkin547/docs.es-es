---
description: 'Más información sobre: enumeración Corassemblyflags ('
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
ms.openlocfilehash: bd74534b1f607eea15f1d8615f66723428ddae3f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678495"
---
# <a name="corassemblyflags-enumeration"></a>CorAssemblyFlags (Enumeración)

Contiene valores que describen los metadatos aplicados a una compilación de ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`afPublicKey`|Indica que la referencia de ensamblado contiene la clave pública completa sin hash.|  
|`afPA_None`|Indica que la arquitectura de procesador no está especificada.|  
|`afPA_MSIL`|Indica que la arquitectura del procesador es neutra (PE32).|  
|`afPA_x86`|Indica que la arquitectura del procesador es x86 (PE32).|  
|`afPA_IA64`|Indica que la arquitectura de procesador es Itanium (PE32 +).|  
|`afPA_AMD64`|Indica que la arquitectura de procesador es AMD x64 (PE32 +).|  
|`afPA_ARM`|Indica que la arquitectura del procesador es ARM (PE32).|  
|`afPA_NoPlatform`|Indica que el ensamblado es un ensamblado de referencia; es decir, se aplica a cualquier arquitectura, pero no se puede ejecutar en ninguna arquitectura. Por lo tanto, la marca es igual que `afPA_Mask` .|  
|`afPA_Specified`|Indica que las marcas de arquitectura de procesador deben propagarse al `AssemblyRef` registro.|  
|`afPA_Mask`|Máscara que describe la arquitectura del procesador.|  
|`afPA_FullMask`|Especifica que se incluye la descripción de la arquitectura del procesador.|  
|`afPA_Shift`|Indica un recuento de desplazamiento en las marcas de la arquitectura del procesador hacia y desde el índice.|  
|`afEnableJITcompileTracking`|Indica el valor correspondiente de la <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> de <xref:System.Diagnostics.DebuggableAttribute> .|  
|`afDisableJITcompileOptimizer`|Indica el valor correspondiente de la <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> de <xref:System.Diagnostics.DebuggableAttribute> .|  
|`afRetargetable`|Indica que se puede redestinar el ensamblado en tiempo de ejecución a un ensamblado de un publicador diferente.|  
|`afContentType_Mask`|Máscara que describe el tipo de contenido.|  
|`afContentType_Default`|Indica el tipo de contenido predeterminado.|  
|`afContentType_WindowsRuntime`|Indica el tipo de contenido Windows Runtime.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](metadata-enumerations.md)
