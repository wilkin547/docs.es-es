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
ms.openlocfilehash: 9d35f6b1928d714216b669704ec28e53895f6549
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699071"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="64eb8-102">CorUnmanagedCallingConvention (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="64eb8-102">CorUnmanagedCallingConvention Enumeration</span></span>

<span data-ttu-id="64eb8-103">Especifica las convenciones de llamada para el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="64eb8-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64eb8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64eb8-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="64eb8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="64eb8-105">Members</span></span>  
  
|<span data-ttu-id="64eb8-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="64eb8-106">Member</span></span>|<span data-ttu-id="64eb8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="64eb8-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="64eb8-108">Convención de llamada del lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="64eb8-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="64eb8-109">La Convención de llamada estándar.</span><span class="sxs-lookup"><span data-stu-id="64eb8-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="64eb8-110">Convención de llamada "this".</span><span class="sxs-lookup"><span data-stu-id="64eb8-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="64eb8-111">Convención de llamada "rápida".</span><span class="sxs-lookup"><span data-stu-id="64eb8-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="64eb8-112">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="64eb8-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="64eb8-113">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="64eb8-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="64eb8-114">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="64eb8-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="64eb8-115">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="64eb8-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64eb8-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64eb8-116">Remarks</span></span>  

 <span data-ttu-id="64eb8-117">CLR no admite la Convención de llamada "Fast" en la .NET Framework versión 1,0.</span><span class="sxs-lookup"><span data-stu-id="64eb8-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64eb8-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64eb8-118">Requirements</span></span>  

 <span data-ttu-id="64eb8-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64eb8-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64eb8-120">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="64eb8-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="64eb8-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64eb8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64eb8-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64eb8-122">See also</span></span>

- [<span data-ttu-id="64eb8-123">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="64eb8-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
