---
title: "CorUnmanagedCallingConvention (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorUnmanagedCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorUnmanagedCallingConvention
helpviewer_keywords: CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f66cb036de8450d4c1b3431b92487260956d47f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="9d2c6-102">CorUnmanagedCallingConvention (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9d2c6-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="9d2c6-103">Especifica las convenciones de llamada de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="9d2c6-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d2c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d2c6-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="9d2c6-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9d2c6-105">Members</span></span>  
  
|<span data-ttu-id="9d2c6-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9d2c6-106">Member</span></span>|<span data-ttu-id="9d2c6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d2c6-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="9d2c6-108">La convención de llamada de lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="9d2c6-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="9d2c6-109">La convención de llamada estándar.</span><span class="sxs-lookup"><span data-stu-id="9d2c6-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="9d2c6-110">"Este" convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="9d2c6-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="9d2c6-111">La convención de llamada "rápida".</span><span class="sxs-lookup"><span data-stu-id="9d2c6-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="9d2c6-112">No usado.</span><span class="sxs-lookup"><span data-stu-id="9d2c6-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="9d2c6-113">No usado.</span><span class="sxs-lookup"><span data-stu-id="9d2c6-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="9d2c6-114">No usado.</span><span class="sxs-lookup"><span data-stu-id="9d2c6-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="9d2c6-115">No usado.</span><span class="sxs-lookup"><span data-stu-id="9d2c6-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d2c6-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9d2c6-116">Remarks</span></span>  
 <span data-ttu-id="9d2c6-117">El CLR no admite la convención de llamada "fast" en la versión 1.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9d2c6-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d2c6-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d2c6-118">Requirements</span></span>  
 <span data-ttu-id="9d2c6-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d2c6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d2c6-120">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9d2c6-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9d2c6-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d2c6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d2c6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d2c6-122">See Also</span></span>  
 [<span data-ttu-id="9d2c6-123">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="9d2c6-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
