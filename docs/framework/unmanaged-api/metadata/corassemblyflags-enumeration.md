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
ms.openlocfilehash: eca4b66a3f7c1a96bb06827dde477f34cb904ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906248"
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
|`afPA_IA64`|Indica que la arquitectura de procesador Itanium (PE32 +).|  
|`afPA_AMD64`|Indica que la arquitectura de procesador AMD X64 (PE32 +).|  
|`afPA_ARM`|Indica que la arquitectura de procesador ARM (PE32).|  
|`afPA_NoPlatform`|Indica que el ensamblado es un ensamblado de referencia; es decir, se aplica a cualquier arquitectura pero no se puede ejecutar en cualquier arquitectura. Por lo tanto, la marca es el mismo que `afPA_Mask`.|  
|`afPA_Specified`|Indica que se deben propagar las marcas de la arquitectura de procesador para el `AssemblyRef` registro.|  
|`afPA_Mask`|Una máscara que describe la arquitectura del procesador.|  
|`afPA_FullMask`|Especifica que se incluye la descripción de la arquitectura de procesador.|  
|`afPA_Shift`|Indica un valor de desplazamiento en las marcas de la arquitectura de procesador a y desde el índice.|  
|`afEnableJITcompileTracking`|Indica el valor correspondiente de la <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> de la <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afDisableJITcompileOptimizer`|Indica el valor correspondiente de la <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> de la <xref:System.Diagnostics.DebuggableAttribute>.|  
|`afRetargetable`|Indica que el ensamblado puede cambiarse en tiempo de ejecución a un ensamblado desde un publicador diferente.|  
|`afContentType_Mask`|Una máscara que describe el tipo de contenido.|  
|`afContentType_Default`|Indica el tipo de contenido predeterminado.|  
|`afContentType_WindowsRuntime`|Indica el [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo de contenido.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
