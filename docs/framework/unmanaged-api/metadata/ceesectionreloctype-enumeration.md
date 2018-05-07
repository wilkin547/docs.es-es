---
title: CeeSectionRelocType (Enumeración)
ms.date: 03/30/2017
api_name:
- CeeSectionRelocType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocType
helpviewer_keywords:
- CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: babd7d87f1bb6f238c347d68814a3ecdaef64b40
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType (Enumeración)
Proporciona valores para influir en el tipo de `reloc` instrucción se emite en una llamada a [ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum  {  
    srRelocAbsolute,  
    srRelocHighLow          = 3,  
    srRelocHighAdj,       
    srRelocMapToken,  
    srRelocRelative,  
    srRelocFilePos,  
    srRelocCodeRelative,  
    srRelocIA64Imm64,  
    srRelocDir64,  
    srRelocIA64PcRel25,  
    srRelocIA64PcRel64,    srRelocAbsoluteTagged,    srRelocSentinel,    srNoBaseReloc       = 0x4000,  
    srRelocPtr          = 0x8000,  
    srRelocAbsolutePtr      = srRelocPtr + srRelocAbsolute,  
    srRelocHighLowPtr       = srRelocPtr + srRelocHighLow,  
    srRelocRelativePtr      = srRelocPtr + srRelocRelative,  
    srRelocIA64Imm64Ptr     = srRelocPtr + srRelocIA64Imm64,  
    srRelocDir64Ptr         = srRelocPtr + srRelocDir64  
    } CeeSectionRelocType;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`srRelocAbsolute`|Genera solo un-relativa a la sección `reloc`y envía nada en una sección .reloc.|  
|`srRelocHighLow`|Genera un `reloc` para una ubicación de tamaño de puntero. Esto se transforma en BASED_HIGHLOW o BASED_DIR64, dependiendo de la plataforma.|  
|`srRelocHighAdj`|Genera un `reloc` para los 16 bits superiores de un número de 32 bits, en la siguiente palabra en la tabla .reloc que se incluyen los 16 bits inferiores.|  
|`srRelocMapToken`|Genera una reubicación del mapa de token, envía nada a una sección .reloc.|  
|`srRelocRelative`|Indica que el valor es una corrección de la dirección relativa.|  
|`srRelocFilePos`|Genera solo un-relativa a la sección `reloc`y envía nada en una sección .reloc. Esto `reloc` es relativa a la posición del archivo de la sección, no direcciones virtuales de la sección.|  
|`srRelocCodeRelative`|Especifica una corrección de la dirección relativa del código.|  
|`srRelocIA64Imm64`|Genera un `reloc` para una dirección de 64 bits en un ia64 `movl` instrucción.|  
|`srRelocDir64`|Genera un `reloc` para una dirección de 64 bits.|  
|`srRelocIA64PcRel25`|Generar un `reloc` para una dirección relativa de PC de 25 bits en un ia64 `br.call` instrucción.|  
|`srRelocIA64PcRel64`|Genera un `reloc` para una dirección relativa de PC de 64 bits en un ia64 `brl.call` instrucción.|  
|`srRelocAbsoluteTagged`|Genera un 30 bits-relativa a la sección `reloc`, que se usa para los valores de puntero etiquetado.|  
|`srRelocSentinel`|Un valor centinela para ayudar a garantizar las adiciones a esta enumeración se reflejan para interno `reloc` matriz de nombre.|  
|`srNoBaseReloc`|Especifica que no se emita una base de `reloc`.|  
|`srRelocPtr`|Un valor que indica que el contenido anterior a la corrección de memoria es un puntero en lugar de una sección de desplazamiento.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [ICeeGen (interfaz)](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 [AddSectionReloc (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
