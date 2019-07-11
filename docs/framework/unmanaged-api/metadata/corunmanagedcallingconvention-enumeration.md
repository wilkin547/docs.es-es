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
ms.openlocfilehash: 9206fbde13f457d4b2e2941ee744d645c6df9774
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781993"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="8d524-102">CorUnmanagedCallingConvention (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8d524-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="8d524-103">Especifica las convenciones de llamada para código no administrado.</span><span class="sxs-lookup"><span data-stu-id="8d524-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d524-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d524-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="8d524-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8d524-105">Members</span></span>  
  
|<span data-ttu-id="8d524-106">Member</span><span class="sxs-lookup"><span data-stu-id="8d524-106">Member</span></span>|<span data-ttu-id="8d524-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8d524-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="8d524-108">La convención de llamada de lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="8d524-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="8d524-109">La convención de llamada estándar.</span><span class="sxs-lookup"><span data-stu-id="8d524-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="8d524-110">"This" convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="8d524-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="8d524-111">La convención de llamada "rápida".</span><span class="sxs-lookup"><span data-stu-id="8d524-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="8d524-112">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="8d524-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="8d524-113">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="8d524-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="8d524-114">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="8d524-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="8d524-115">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="8d524-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d524-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8d524-116">Remarks</span></span>  
 <span data-ttu-id="8d524-117">El CLR no admite la convención de llamada "rápida" en la versión 1.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8d524-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d524-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d524-118">Requirements</span></span>  
 <span data-ttu-id="8d524-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d524-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d524-120">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="8d524-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8d524-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d524-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d524-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d524-122">See also</span></span>

- [<span data-ttu-id="8d524-123">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="8d524-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
