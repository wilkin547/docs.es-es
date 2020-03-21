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
ms.openlocfilehash: 44a84e0752eecc1c694f3b8cf6e568b72b7d0f5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176219"
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType (Enumeración)
Proporciona valores para influir `reloc` en el tipo de instrucción emitida en una llamada a [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`srRelocAbsolute`|Genera solo una `reloc`sección relativa, enviando nada a una sección .reloc.|  
|`srRelocHighLow`|Genera `reloc` un para una ubicación del tamaño de un puntero. Esto se transforma en BASED_HIGHLOW o BASED_DIR64 dependiendo de la plataforma.|  
|`srRelocHighAdj`|Genera `reloc` a para los 16 bits superiores de un número de 32 bits, donde los 16 bits inferiores se incluyen en la siguiente palabra de la tabla .reloc.|  
|`srRelocMapToken`|Genera una reubicación de mapa de token, sin enviar nada a una sección .reloc.|  
|`srRelocRelative`|Indica que el valor es una corrección de direcciones relativas.|  
|`srRelocFilePos`|Genera solo una `reloc`sección relativa, enviando nada a una sección .reloc. Esto `reloc` es relativo a la posición del archivo de la sección, no a la dirección virtual de la sección.|  
|`srRelocCodeRelative`|Especifica una corrección de direcciones relativas al código.|  
|`srRelocIA64Imm64`|Genera `reloc` una dirección para una dirección de `movl` 64 bits en una instrucción ia64.|  
|`srRelocDir64`|Genera `reloc` a para una dirección de 64 bits.|  
|`srRelocIA64PcRel25`|Genere `reloc` una dirección relativa a PC de 25 bits `br.call` en una instrucción ia64.|  
|`srRelocIA64PcRel64`|Genera `reloc` una dirección relativa a PC de 64 bits `brl.call` en una instrucción ia64.|  
|`srRelocAbsoluteTagged`|Genera una sección relativa `reloc`de 30 bits, utilizada para los valores de puntero etiquetados.|  
|`srRelocSentinel`|Un valor centinela para ayudar a garantizar que las adiciones a esta enumeración se reflejen en la matriz de nombres interna. `reloc`|  
|`srNoBaseReloc`|Especifica que no se `reloc`emita una base .|  
|`srRelocPtr`|Valor que indica que el contenido previo a la corrección de la memoria es un puntero en lugar de un desplazamiento de sección.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [ICeeGen (Interfaz)](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [AddSectionReloc (Método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
