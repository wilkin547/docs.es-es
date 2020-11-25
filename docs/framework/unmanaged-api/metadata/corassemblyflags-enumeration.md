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
ms.openlocfilehash: 615c4ac95ab777e8081e630cafb6671e64dea78a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719013"
---
# <a name="corassemblyflags-enumeration"></a><span data-ttu-id="6d17b-102">CorAssemblyFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6d17b-102">CorAssemblyFlags Enumeration</span></span>

<span data-ttu-id="6d17b-103">Contiene valores que describen los metadatos aplicados a una compilación de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6d17b-103">Contains values that describe the metadata applied to an assembly compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d17b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d17b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6d17b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="6d17b-105">Members</span></span>  
  
|<span data-ttu-id="6d17b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="6d17b-106">Member</span></span>|<span data-ttu-id="6d17b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d17b-107">Description</span></span>|  
|------------|-----------------|  
|`afPublicKey`|<span data-ttu-id="6d17b-108">Indica que la referencia de ensamblado contiene la clave pública completa sin hash.</span><span class="sxs-lookup"><span data-stu-id="6d17b-108">Indicates that the assembly reference holds the full, unhashed public key.</span></span>|  
|`afPA_None`|<span data-ttu-id="6d17b-109">Indica que la arquitectura de procesador no está especificada.</span><span class="sxs-lookup"><span data-stu-id="6d17b-109">Indicates that the processor architecture is unspecified.</span></span>|  
|`afPA_MSIL`|<span data-ttu-id="6d17b-110">Indica que la arquitectura del procesador es neutra (PE32).</span><span class="sxs-lookup"><span data-stu-id="6d17b-110">Indicates that the processor architecture is neutral (PE32).</span></span>|  
|`afPA_x86`|<span data-ttu-id="6d17b-111">Indica que la arquitectura del procesador es x86 (PE32).</span><span class="sxs-lookup"><span data-stu-id="6d17b-111">Indicates that the processor architecture is x86 (PE32).</span></span>|  
|`afPA_IA64`|<span data-ttu-id="6d17b-112">Indica que la arquitectura de procesador es Itanium (PE32 +).</span><span class="sxs-lookup"><span data-stu-id="6d17b-112">Indicates that the processor architecture is Itanium (PE32+).</span></span>|  
|`afPA_AMD64`|<span data-ttu-id="6d17b-113">Indica que la arquitectura de procesador es AMD x64 (PE32 +).</span><span class="sxs-lookup"><span data-stu-id="6d17b-113">Indicates that the processor architecture is AMD X64 (PE32+).</span></span>|  
|`afPA_ARM`|<span data-ttu-id="6d17b-114">Indica que la arquitectura del procesador es ARM (PE32).</span><span class="sxs-lookup"><span data-stu-id="6d17b-114">Indicates that the processor architecture is ARM (PE32).</span></span>|  
|`afPA_NoPlatform`|<span data-ttu-id="6d17b-115">Indica que el ensamblado es un ensamblado de referencia; es decir, se aplica a cualquier arquitectura, pero no se puede ejecutar en ninguna arquitectura.</span><span class="sxs-lookup"><span data-stu-id="6d17b-115">Indicates that the assembly is a reference assembly; that is, it applies to any architecture but cannot run on any architecture.</span></span> <span data-ttu-id="6d17b-116">Por lo tanto, la marca es igual que `afPA_Mask` .</span><span class="sxs-lookup"><span data-stu-id="6d17b-116">Thus, the flag is the same as `afPA_Mask`.</span></span>|  
|`afPA_Specified`|<span data-ttu-id="6d17b-117">Indica que las marcas de arquitectura de procesador deben propagarse al `AssemblyRef` registro.</span><span class="sxs-lookup"><span data-stu-id="6d17b-117">Indicates that the processor architecture flags should be propagated to the `AssemblyRef` record.</span></span>|  
|`afPA_Mask`|<span data-ttu-id="6d17b-118">Máscara que describe la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="6d17b-118">A mask that describes the processor architecture.</span></span>|  
|`afPA_FullMask`|<span data-ttu-id="6d17b-119">Especifica que se incluye la descripción de la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="6d17b-119">Specifies that the processor architecture description is included.</span></span>|  
|`afPA_Shift`|<span data-ttu-id="6d17b-120">Indica un recuento de desplazamiento en las marcas de la arquitectura del procesador hacia y desde el índice.</span><span class="sxs-lookup"><span data-stu-id="6d17b-120">Indicates a shift count in the processor architecture flags to and from the index.</span></span>|  
|`afEnableJITcompileTracking`|<span data-ttu-id="6d17b-121">Indica el valor correspondiente de la <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> de <xref:System.Diagnostics.DebuggableAttribute> .</span><span class="sxs-lookup"><span data-stu-id="6d17b-121">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afDisableJITcompileOptimizer`|<span data-ttu-id="6d17b-122">Indica el valor correspondiente de la <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> de <xref:System.Diagnostics.DebuggableAttribute> .</span><span class="sxs-lookup"><span data-stu-id="6d17b-122">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afRetargetable`|<span data-ttu-id="6d17b-123">Indica que se puede redestinar el ensamblado en tiempo de ejecución a un ensamblado de un publicador diferente.</span><span class="sxs-lookup"><span data-stu-id="6d17b-123">Indicates that the assembly can be retargeted at run time to an assembly from a different publisher.</span></span>|  
|`afContentType_Mask`|<span data-ttu-id="6d17b-124">Máscara que describe el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="6d17b-124">A mask that describes the content type.</span></span>|  
|`afContentType_Default`|<span data-ttu-id="6d17b-125">Indica el tipo de contenido predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6d17b-125">Indicates the default content type.</span></span>|  
|`afContentType_WindowsRuntime`|<span data-ttu-id="6d17b-126">Indica el tipo de contenido Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="6d17b-126">Indicates the Windows Runtime content type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d17b-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d17b-127">Requirements</span></span>  

 <span data-ttu-id="6d17b-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d17b-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d17b-129">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="6d17b-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6d17b-130">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d17b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d17b-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d17b-131">See also</span></span>

- [<span data-ttu-id="6d17b-132">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="6d17b-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
