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
ms.openlocfilehash: 882242da493c49a2e6aa09888e9503dcf2933589
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119592"
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
|`srRelocAbsolute`|Genera solo una sección relacionados con `reloc`y envía nada en una sección .reloc.|  
|`srRelocHighLow`|Genera un `reloc` para una ubicación dimensionado por puntero. Esto se transforma en BASED_HIGHLOW o BASED_DIR64, dependiendo de la plataforma.|  
|`srRelocHighAdj`|Genera un `reloc` para la parte superior de 16 bits de un número de 32 bits, donde los 16 bits inferiores se incluyen en la siguiente palabra en la tabla .reloc.|  
|`srRelocMapToken`|Genera una reubicación de asignación de token, envía nada a una sección .reloc.|  
|`srRelocRelative`|Indica que el valor es una corrección de la dirección relativa.|  
|`srRelocFilePos`|Genera solo una sección relacionados con `reloc`y envía nada en una sección .reloc. Esto `reloc` es relativo a la posición de la sección, no direcciones virtuales de la sección del archivo.|  
|`srRelocCodeRelative`|Especifica una dirección relativa del código de corrección.|  
|`srRelocIA64Imm64`|Genera un `reloc` para una dirección de 64 bits en ia64 `movl` instrucción.|  
|`srRelocDir64`|Genera un `reloc` para una dirección de 64 bits.|  
|`srRelocIA64PcRel25`|Generar un `reloc` para una dirección relativa de PC de 25 bits en ia64 `br.call` instrucción.|  
|`srRelocIA64PcRel64`|Genera un `reloc` para una dirección relativa de PC de 64 bits en ia64 `brl.call` instrucción.|  
|`srRelocAbsoluteTagged`|Genera un 30 bits-relativa a la sección `reloc`, que se usa para los valores de puntero etiquetadas.|  
|`srRelocSentinel`|Un valor de Centinela para ayudar a garantizar las adiciones a esta enumeración se reflejan en el interno `reloc` matriz nombre.|  
|`srNoBaseReloc`|Especifica que no emita una base de `reloc`.|  
|`srRelocPtr`|Un valor que indica que el contenido anterior a la corrección de memoria es un puntero en lugar de una sección de desplazamiento.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [ICeeGen (interfaz)](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [AddSectionReloc (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
