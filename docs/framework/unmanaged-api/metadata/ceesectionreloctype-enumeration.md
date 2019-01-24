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
ms.openlocfilehash: c1541c6fa2b1d307fc8e854a67b7cc3068b7bb4d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580725"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="a1669-102">CeeSectionRelocType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a1669-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="a1669-103">Proporciona valores para influir en el tipo de `reloc` instrucción se emite en una llamada a [ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span><span class="sxs-lookup"><span data-stu-id="a1669-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1669-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1669-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="a1669-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a1669-105">Members</span></span>  
  
|<span data-ttu-id="a1669-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a1669-106">Member</span></span>|<span data-ttu-id="a1669-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1669-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="a1669-108">Genera solo una sección relacionados con `reloc`y envía nada en una sección .reloc.</span><span class="sxs-lookup"><span data-stu-id="a1669-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="a1669-109">Genera un `reloc` para una ubicación dimensionado por puntero.</span><span class="sxs-lookup"><span data-stu-id="a1669-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="a1669-110">Esto se transforma en BASED_HIGHLOW o BASED_DIR64, dependiendo de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="a1669-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="a1669-111">Genera un `reloc` para la parte superior de 16 bits de un número de 32 bits, donde los 16 bits inferiores se incluyen en la siguiente palabra en la tabla .reloc.</span><span class="sxs-lookup"><span data-stu-id="a1669-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="a1669-112">Genera una reubicación de asignación de token, envía nada a una sección .reloc.</span><span class="sxs-lookup"><span data-stu-id="a1669-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="a1669-113">Indica que el valor es una corrección de la dirección relativa.</span><span class="sxs-lookup"><span data-stu-id="a1669-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="a1669-114">Genera solo una sección relacionados con `reloc`y envía nada en una sección .reloc.</span><span class="sxs-lookup"><span data-stu-id="a1669-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="a1669-115">Esto `reloc` es relativo a la posición de la sección, no direcciones virtuales de la sección del archivo.</span><span class="sxs-lookup"><span data-stu-id="a1669-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="a1669-116">Especifica una dirección relativa del código de corrección.</span><span class="sxs-lookup"><span data-stu-id="a1669-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="a1669-117">Genera un `reloc` para una dirección de 64 bits en ia64 `movl` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a1669-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="a1669-118">Genera un `reloc` para una dirección de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="a1669-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="a1669-119">Generar un `reloc` para una dirección relativa de PC de 25 bits en ia64 `br.call` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a1669-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="a1669-120">Genera un `reloc` para una dirección relativa de PC de 64 bits en ia64 `brl.call` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a1669-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="a1669-121">Genera un 30 bits-relativa a la sección `reloc`, que se usa para los valores de puntero etiquetadas.</span><span class="sxs-lookup"><span data-stu-id="a1669-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="a1669-122">Un valor de Centinela para ayudar a garantizar las adiciones a esta enumeración se reflejan en el interno `reloc` matriz nombre.</span><span class="sxs-lookup"><span data-stu-id="a1669-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="a1669-123">Especifica que no emita una base de `reloc`.</span><span class="sxs-lookup"><span data-stu-id="a1669-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="a1669-124">Un valor que indica que el contenido anterior a la corrección de memoria es un puntero en lugar de una sección de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="a1669-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1669-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1669-125">Requirements</span></span>  
 <span data-ttu-id="a1669-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1669-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1669-127">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="a1669-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1669-128">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1669-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1669-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1669-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1669-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1669-130">See also</span></span>
- [<span data-ttu-id="a1669-131">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="a1669-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="a1669-132">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1669-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [<span data-ttu-id="a1669-133">AddSectionReloc (método)</span><span class="sxs-lookup"><span data-stu-id="a1669-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
