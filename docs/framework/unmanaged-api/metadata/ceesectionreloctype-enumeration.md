---
description: 'Más información sobre: enumeración Ceesectionreloctype ('
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
ms.openlocfilehash: 49f7b39b3cc4c2e71dd3e4e426d0ca787e9ac0b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678840"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="7ed65-103">CeeSectionRelocType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="7ed65-103">CeeSectionRelocType Enumeration</span></span>

<span data-ttu-id="7ed65-104">Proporciona valores para influir en el tipo de `reloc` instrucción emitida en una llamada a [ICeeGen:: AddSectionReloc (](iceegen-addsectionreloc-method.md).</span><span class="sxs-lookup"><span data-stu-id="7ed65-104">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ed65-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ed65-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="7ed65-106">Members</span><span class="sxs-lookup"><span data-stu-id="7ed65-106">Members</span></span>  
  
|<span data-ttu-id="7ed65-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="7ed65-107">Member</span></span>|<span data-ttu-id="7ed65-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ed65-108">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="7ed65-109">Genera solo una sección relativa `reloc` , sin enviar nada en una sección. reloc.</span><span class="sxs-lookup"><span data-stu-id="7ed65-109">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="7ed65-110">Genera un `reloc` para una ubicación de tamaño del puntero.</span><span class="sxs-lookup"><span data-stu-id="7ed65-110">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="7ed65-111">Esto se transforma en BASED_HIGHLOW o BASED_DIR64 según la plataforma.</span><span class="sxs-lookup"><span data-stu-id="7ed65-111">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="7ed65-112">Genera un `reloc` para los 16 bits superiores de un número de 32 bits, donde los 16 bits inferiores se incluyen en la siguiente palabra de la tabla. reloc.</span><span class="sxs-lookup"><span data-stu-id="7ed65-112">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="7ed65-113">Genera una reubicación de asignación de tokens, sin enviar nada a una sección. reloc.</span><span class="sxs-lookup"><span data-stu-id="7ed65-113">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="7ed65-114">Indica que el valor es una corrección de dirección relativa.</span><span class="sxs-lookup"><span data-stu-id="7ed65-114">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="7ed65-115">Genera solo una sección relativa `reloc` , sin enviar nada en una sección. reloc.</span><span class="sxs-lookup"><span data-stu-id="7ed65-115">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="7ed65-116">`reloc`Es relativo a la posición de archivo de la sección, no a la dirección virtual de la sección.</span><span class="sxs-lookup"><span data-stu-id="7ed65-116">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="7ed65-117">Especifica una corrección de dirección relativa del código.</span><span class="sxs-lookup"><span data-stu-id="7ed65-117">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="7ed65-118">Genera `reloc` para una dirección de 64 bits en una instrucción de IA64 `movl` .</span><span class="sxs-lookup"><span data-stu-id="7ed65-118">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="7ed65-119">Genera `reloc` para una dirección de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="7ed65-119">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="7ed65-120">Genere `reloc` para una dirección relativa de PC de 25 bits en una instrucción de IA64 `br.call` .</span><span class="sxs-lookup"><span data-stu-id="7ed65-120">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="7ed65-121">Genera `reloc` para una dirección relativa de PC de 64 bits en una instrucción de IA64 `brl.call` .</span><span class="sxs-lookup"><span data-stu-id="7ed65-121">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="7ed65-122">Genera una sección relativa de 30 bits, que se `reloc` usa para los valores de puntero etiquetados.</span><span class="sxs-lookup"><span data-stu-id="7ed65-122">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="7ed65-123">Un valor de Centinela para ayudar a garantizar que las adiciones a esta enumeración se reflejan en la `reloc` matriz de nombres interna.</span><span class="sxs-lookup"><span data-stu-id="7ed65-123">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="7ed65-124">Especifica que no se debe emitir una base `reloc` .</span><span class="sxs-lookup"><span data-stu-id="7ed65-124">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="7ed65-125">Un valor que indica que el contenido previo a la corrección de la memoria es un puntero en lugar de un desplazamiento de sección.</span><span class="sxs-lookup"><span data-stu-id="7ed65-125">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ed65-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ed65-126">Requirements</span></span>  

 <span data-ttu-id="7ed65-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ed65-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ed65-128">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7ed65-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ed65-129">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7ed65-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ed65-130">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ed65-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ed65-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ed65-131">See also</span></span>

- [<span data-ttu-id="7ed65-132">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="7ed65-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="7ed65-133">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ed65-133">ICeeGen Interface</span></span>](iceegen-interface.md)
- [<span data-ttu-id="7ed65-134">Método AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="7ed65-134">AddSectionReloc Method</span></span>](iceegen-addsectionreloc-method.md)
