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
ms.openlocfilehash: f7aa9699e9929608c90020c6b2d66c301fc11955
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732715"
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType (Enumeración)

Proporciona valores para influir en el tipo de `reloc` instrucción emitida en una llamada a [ICeeGen:: AddSectionReloc (](iceegen-addsectionreloc-method.md).  
  
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
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`srRelocAbsolute`|Genera solo una sección relativa `reloc` , sin enviar nada en una sección. reloc.|  
|`srRelocHighLow`|Genera un `reloc` para una ubicación de tamaño del puntero. Esto se transforma en BASED_HIGHLOW o BASED_DIR64 según la plataforma.|  
|`srRelocHighAdj`|Genera un `reloc` para los 16 bits superiores de un número de 32 bits, donde los 16 bits inferiores se incluyen en la siguiente palabra de la tabla. reloc.|  
|`srRelocMapToken`|Genera una reubicación de asignación de tokens, sin enviar nada a una sección. reloc.|  
|`srRelocRelative`|Indica que el valor es una corrección de dirección relativa.|  
|`srRelocFilePos`|Genera solo una sección relativa `reloc` , sin enviar nada en una sección. reloc. `reloc`Es relativo a la posición de archivo de la sección, no a la dirección virtual de la sección.|  
|`srRelocCodeRelative`|Especifica una corrección de dirección relativa del código.|  
|`srRelocIA64Imm64`|Genera `reloc` para una dirección de 64 bits en una instrucción de IA64 `movl` .|  
|`srRelocDir64`|Genera `reloc` para una dirección de 64 bits.|  
|`srRelocIA64PcRel25`|Genere `reloc` para una dirección relativa de PC de 25 bits en una instrucción de IA64 `br.call` .|  
|`srRelocIA64PcRel64`|Genera `reloc` para una dirección relativa de PC de 64 bits en una instrucción de IA64 `brl.call` .|  
|`srRelocAbsoluteTagged`|Genera una sección relativa de 30 bits, que se `reloc` usa para los valores de puntero etiquetados.|  
|`srRelocSentinel`|Un valor de Centinela para ayudar a garantizar que las adiciones a esta enumeración se reflejan en la `reloc` matriz de nombres interna.|  
|`srNoBaseReloc`|Especifica que no se debe emitir una base `reloc` .|  
|`srRelocPtr`|Un valor que indica que el contenido previo a la corrección de la memoria es un puntero en lugar de un desplazamiento de sección.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
- [ICeeGen (Interfaz)](iceegen-interface.md)
- [Método AddSectionReloc](iceegen-addsectionreloc-method.md)
