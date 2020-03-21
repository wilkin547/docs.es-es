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
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="b778f-102">CeeSectionRelocType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b778f-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="b778f-103">Proporciona valores para influir `reloc` en el tipo de instrucción emitida en una llamada a [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span><span class="sxs-lookup"><span data-stu-id="b778f-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b778f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b778f-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b778f-105">Members</span><span class="sxs-lookup"><span data-stu-id="b778f-105">Members</span></span>  
  
|<span data-ttu-id="b778f-106">Member</span><span class="sxs-lookup"><span data-stu-id="b778f-106">Member</span></span>|<span data-ttu-id="b778f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b778f-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="b778f-108">Genera solo una `reloc`sección relativa, enviando nada a una sección .reloc.</span><span class="sxs-lookup"><span data-stu-id="b778f-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="b778f-109">Genera `reloc` un para una ubicación del tamaño de un puntero.</span><span class="sxs-lookup"><span data-stu-id="b778f-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="b778f-110">Esto se transforma en BASED_HIGHLOW o BASED_DIR64 dependiendo de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="b778f-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="b778f-111">Genera `reloc` a para los 16 bits superiores de un número de 32 bits, donde los 16 bits inferiores se incluyen en la siguiente palabra de la tabla .reloc.</span><span class="sxs-lookup"><span data-stu-id="b778f-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="b778f-112">Genera una reubicación de mapa de token, sin enviar nada a una sección .reloc.</span><span class="sxs-lookup"><span data-stu-id="b778f-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="b778f-113">Indica que el valor es una corrección de direcciones relativas.</span><span class="sxs-lookup"><span data-stu-id="b778f-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="b778f-114">Genera solo una `reloc`sección relativa, enviando nada a una sección .reloc.</span><span class="sxs-lookup"><span data-stu-id="b778f-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="b778f-115">Esto `reloc` es relativo a la posición del archivo de la sección, no a la dirección virtual de la sección.</span><span class="sxs-lookup"><span data-stu-id="b778f-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="b778f-116">Especifica una corrección de direcciones relativas al código.</span><span class="sxs-lookup"><span data-stu-id="b778f-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="b778f-117">Genera `reloc` una dirección para una dirección de `movl` 64 bits en una instrucción ia64.</span><span class="sxs-lookup"><span data-stu-id="b778f-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="b778f-118">Genera `reloc` a para una dirección de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b778f-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="b778f-119">Genere `reloc` una dirección relativa a PC de 25 bits `br.call` en una instrucción ia64.</span><span class="sxs-lookup"><span data-stu-id="b778f-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="b778f-120">Genera `reloc` una dirección relativa a PC de 64 bits `brl.call` en una instrucción ia64.</span><span class="sxs-lookup"><span data-stu-id="b778f-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="b778f-121">Genera una sección relativa `reloc`de 30 bits, utilizada para los valores de puntero etiquetados.</span><span class="sxs-lookup"><span data-stu-id="b778f-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="b778f-122">Un valor centinela para ayudar a garantizar que las adiciones a esta enumeración se reflejen en la matriz de nombres interna. `reloc`</span><span class="sxs-lookup"><span data-stu-id="b778f-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="b778f-123">Especifica que no se `reloc`emita una base .</span><span class="sxs-lookup"><span data-stu-id="b778f-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="b778f-124">Valor que indica que el contenido previo a la corrección de la memoria es un puntero en lugar de un desplazamiento de sección.</span><span class="sxs-lookup"><span data-stu-id="b778f-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b778f-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b778f-125">Requirements</span></span>  
 <span data-ttu-id="b778f-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b778f-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b778f-127">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b778f-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b778f-128">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b778f-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b778f-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b778f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b778f-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b778f-130">See also</span></span>

- [<span data-ttu-id="b778f-131">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="b778f-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="b778f-132">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b778f-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [<span data-ttu-id="b778f-133">AddSectionReloc (Método)</span><span class="sxs-lookup"><span data-stu-id="b778f-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
