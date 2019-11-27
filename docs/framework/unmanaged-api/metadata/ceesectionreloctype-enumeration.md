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
ms.openlocfilehash: efce0c13944b383c42cbff6a6af4795293ee2989
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444156"
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType (Enumeración)
Proporciona valores para influir en el tipo de `reloc` instrucción emitida en una llamada a [ICeeGen:: AddSectionReloc (](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).  
  
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
|`srRelocAbsolute`|Genera solo un `reloc`relativo a la sección, sin enviar nada en una sección. reloc.|  
|`srRelocHighLow`|Genera una `reloc` para una ubicación de tamaño de puntero. Esto se transforma en BASED_HIGHLOW o BASED_DIR64 según la plataforma.|  
|`srRelocHighAdj`|Genera un `reloc` para los 16 bits superiores de un número de 32 bits, donde los 16 bits inferiores se incluyen en la siguiente palabra de la tabla. reloc.|  
|`srRelocMapToken`|Genera una reubicación de asignación de tokens, sin enviar nada a una sección. reloc.|  
|`srRelocRelative`|Indica que el valor es una corrección de dirección relativa.|  
|`srRelocFilePos`|Genera solo un `reloc`relativo a la sección, sin enviar nada en una sección. reloc. Este `reloc` es relativo a la posición de archivo de la sección, no a la dirección virtual de la sección.|  
|`srRelocCodeRelative`|Especifica una corrección de dirección relativa del código.|  
|`srRelocIA64Imm64`|Genera una `reloc` para una dirección de 64 bits en una instrucción de `movl` ia64.|  
|`srRelocDir64`|Genera una `reloc` para una dirección de 64 bits.|  
|`srRelocIA64PcRel25`|Genere un `reloc` para una dirección relativa de PC de 25 bits en una instrucción de `br.call` ia64.|  
|`srRelocIA64PcRel64`|Genera una `reloc` para una dirección relativa de PC de 64 bits en una instrucción de `brl.call` ia64.|  
|`srRelocAbsoluteTagged`|Genera un `reloc`relativo a la sección de 30 bits, que se usa para los valores de puntero etiquetados.|  
|`srRelocSentinel`|Un valor de Centinela para ayudar a garantizar que las adiciones a esta enumeración se reflejan en la matriz de nombres `reloc` interna.|  
|`srNoBaseReloc`|Especifica que no se debe emitir un `reloc`base.|  
|`srRelocPtr`|Un valor que indica que el contenido previo a la corrección de la memoria es un puntero en lugar de un desplazamiento de sección.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [ICeeGen (interfaz)](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [AddSectionReloc (método)](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
