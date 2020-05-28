---
title: CorUnmanagedCallingConvention (Enumeración)
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
ms.openlocfilehash: b4c521489f38360d45c2cf8ff3780e057299f0b4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008955"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="02faa-102">CorUnmanagedCallingConvention (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="02faa-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="02faa-103">Especifica las convenciones de llamada para el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="02faa-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02faa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02faa-104">Syntax</span></span>  
  
```cpp  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="02faa-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="02faa-105">Members</span></span>  
  
|<span data-ttu-id="02faa-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="02faa-106">Member</span></span>|<span data-ttu-id="02faa-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="02faa-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="02faa-108">Convención de llamada del lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="02faa-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="02faa-109">La Convención de llamada estándar.</span><span class="sxs-lookup"><span data-stu-id="02faa-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="02faa-110">Convención de llamada "this".</span><span class="sxs-lookup"><span data-stu-id="02faa-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="02faa-111">Convención de llamada "rápida".</span><span class="sxs-lookup"><span data-stu-id="02faa-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="02faa-112">No se usa.</span><span class="sxs-lookup"><span data-stu-id="02faa-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="02faa-113">No se usa.</span><span class="sxs-lookup"><span data-stu-id="02faa-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="02faa-114">No se usa.</span><span class="sxs-lookup"><span data-stu-id="02faa-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="02faa-115">No se usa.</span><span class="sxs-lookup"><span data-stu-id="02faa-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02faa-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02faa-116">Remarks</span></span>  
 <span data-ttu-id="02faa-117">CLR no admite la Convención de llamada "Fast" en la .NET Framework versión 1,0.</span><span class="sxs-lookup"><span data-stu-id="02faa-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02faa-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02faa-118">Requirements</span></span>  
 <span data-ttu-id="02faa-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02faa-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02faa-120">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="02faa-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="02faa-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02faa-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02faa-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02faa-122">See also</span></span>

- [<span data-ttu-id="02faa-123">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="02faa-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
