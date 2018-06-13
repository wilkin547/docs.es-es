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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b249d26335a66b55d0643f3e75bfd90554f731e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448874"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="635f8-102">CorUnmanagedCallingConvention (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="635f8-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="635f8-103">Especifica las convenciones de llamada de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="635f8-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="635f8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="635f8-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="635f8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="635f8-105">Members</span></span>  
  
|<span data-ttu-id="635f8-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="635f8-106">Member</span></span>|<span data-ttu-id="635f8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="635f8-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="635f8-108">La convención de llamada de lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="635f8-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="635f8-109">La convención de llamada estándar.</span><span class="sxs-lookup"><span data-stu-id="635f8-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="635f8-110">"Este" convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="635f8-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="635f8-111">La convención de llamada "rápida".</span><span class="sxs-lookup"><span data-stu-id="635f8-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="635f8-112">No usado.</span><span class="sxs-lookup"><span data-stu-id="635f8-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="635f8-113">No usado.</span><span class="sxs-lookup"><span data-stu-id="635f8-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="635f8-114">No usado.</span><span class="sxs-lookup"><span data-stu-id="635f8-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="635f8-115">No usado.</span><span class="sxs-lookup"><span data-stu-id="635f8-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="635f8-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="635f8-116">Remarks</span></span>  
 <span data-ttu-id="635f8-117">El CLR no admite la convención de llamada "fast" en la versión 1.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="635f8-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="635f8-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="635f8-118">Requirements</span></span>  
 <span data-ttu-id="635f8-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="635f8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="635f8-120">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="635f8-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="635f8-121">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="635f8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="635f8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="635f8-122">See Also</span></span>  
 [<span data-ttu-id="635f8-123">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="635f8-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
