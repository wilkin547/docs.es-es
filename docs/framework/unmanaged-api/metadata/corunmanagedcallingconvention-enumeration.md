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
ms.openlocfilehash: ff308a81282a1cc14c35583daf9cbb057149e556
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178456"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="ca263-102">CorUnmanagedCallingConvention (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ca263-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="ca263-103">Especifica las convenciones de llamada para código no administrado.</span><span class="sxs-lookup"><span data-stu-id="ca263-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca263-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca263-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ca263-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ca263-105">Members</span></span>  
  
|<span data-ttu-id="ca263-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ca263-106">Member</span></span>|<span data-ttu-id="ca263-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca263-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="ca263-108">La convención de llamada de lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="ca263-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="ca263-109">La convención de llamada estándar.</span><span class="sxs-lookup"><span data-stu-id="ca263-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="ca263-110">"This" convención de llamada.</span><span class="sxs-lookup"><span data-stu-id="ca263-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="ca263-111">La convención de llamada "rápida".</span><span class="sxs-lookup"><span data-stu-id="ca263-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="ca263-112">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="ca263-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="ca263-113">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="ca263-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="ca263-114">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="ca263-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="ca263-115">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="ca263-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca263-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca263-116">Remarks</span></span>  
 <span data-ttu-id="ca263-117">El CLR no admite la convención de llamada "rápida" en la versión 1.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca263-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca263-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca263-118">Requirements</span></span>  
 <span data-ttu-id="ca263-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca263-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca263-120">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ca263-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ca263-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca263-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca263-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca263-122">See also</span></span>

- [<span data-ttu-id="ca263-123">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="ca263-123">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
