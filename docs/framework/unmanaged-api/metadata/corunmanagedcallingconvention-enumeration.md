---
description: 'Más información sobre: enumeración CorUnmanagedCallingConvention ('
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
ms.openlocfilehash: a4b5c70b7dcb4750d641540662941ed3cc08c94b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707298"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="78bba-103">CorUnmanagedCallingConvention (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="78bba-103">CorUnmanagedCallingConvention Enumeration</span></span>

<span data-ttu-id="78bba-104">Especifica las convenciones de llamada para el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="78bba-104">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78bba-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78bba-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="78bba-106">Members</span><span class="sxs-lookup"><span data-stu-id="78bba-106">Members</span></span>  
  
|<span data-ttu-id="78bba-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="78bba-107">Member</span></span>|<span data-ttu-id="78bba-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="78bba-108">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="78bba-109">Convención de llamada del lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="78bba-109">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="78bba-110">La Convención de llamada estándar.</span><span class="sxs-lookup"><span data-stu-id="78bba-110">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="78bba-111">Convención de llamada "this".</span><span class="sxs-lookup"><span data-stu-id="78bba-111">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="78bba-112">Convención de llamada "rápida".</span><span class="sxs-lookup"><span data-stu-id="78bba-112">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="78bba-113">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="78bba-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="78bba-114">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="78bba-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="78bba-115">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="78bba-115">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="78bba-116">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="78bba-116">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78bba-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="78bba-117">Remarks</span></span>  

 <span data-ttu-id="78bba-118">CLR no admite la Convención de llamada "Fast" en la .NET Framework versión 1,0.</span><span class="sxs-lookup"><span data-stu-id="78bba-118">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78bba-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78bba-119">Requirements</span></span>  

 <span data-ttu-id="78bba-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78bba-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78bba-121">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="78bba-121">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="78bba-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78bba-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78bba-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="78bba-123">See also</span></span>

- [<span data-ttu-id="78bba-124">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="78bba-124">Metadata Enumerations</span></span>](metadata-enumerations.md)
