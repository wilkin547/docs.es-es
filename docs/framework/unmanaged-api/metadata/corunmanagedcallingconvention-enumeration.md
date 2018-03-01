---
title: "CorUnmanagedCallingConvention (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 446a948c8809d9f098ede8fbb9b426f6169ce812
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="d8f82-102">CorUnmanagedCallingConvention (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8f82-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="d8f82-103">Especifica las convenciones de llamada de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="d8f82-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8f82-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8f82-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="d8f82-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d8f82-105">Members</span></span>  
  
|<span data-ttu-id="d8f82-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d8f82-106">Member</span></span>|<span data-ttu-id="d8f82-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8f82-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="d8f82-108">La convención de llamada de lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="d8f82-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="d8f82-109">La convención de llamada estándar.</span><span class="sxs-lookup"><span data-stu-id="d8f82-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="d8f82-110">"Este" convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="d8f82-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="d8f82-111">La convención de llamada "rápida".</span><span class="sxs-lookup"><span data-stu-id="d8f82-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="d8f82-112">No usado.</span><span class="sxs-lookup"><span data-stu-id="d8f82-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="d8f82-113">No usado.</span><span class="sxs-lookup"><span data-stu-id="d8f82-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="d8f82-114">No usado.</span><span class="sxs-lookup"><span data-stu-id="d8f82-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="d8f82-115">No usado.</span><span class="sxs-lookup"><span data-stu-id="d8f82-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8f82-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8f82-116">Remarks</span></span>  
 <span data-ttu-id="d8f82-117">El CLR no admite la convención de llamada "fast" en la versión 1.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8f82-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8f82-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8f82-118">Requirements</span></span>  
 <span data-ttu-id="d8f82-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8f82-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8f82-120">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="d8f82-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d8f82-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8f82-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f82-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8f82-122">See Also</span></span>  
 [<span data-ttu-id="d8f82-123">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="d8f82-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
