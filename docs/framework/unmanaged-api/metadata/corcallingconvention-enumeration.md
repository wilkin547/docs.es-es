---
title: CorCallingConvention (Enumeración)
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44a4b5903cec2249eb1e176381fe3d8e600dd5e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145878"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="3120a-102">CorCallingConvention (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3120a-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="3120a-103">Contiene valores que describen los tipos de convenciones de llamada que se realizan en código administrado.</span><span class="sxs-lookup"><span data-stu-id="3120a-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3120a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3120a-104">Syntax</span></span>  
  
```  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="3120a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3120a-105">Members</span></span>  
  
|<span data-ttu-id="3120a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3120a-106">Member</span></span>|<span data-ttu-id="3120a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3120a-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="3120a-108">Indica una convención de llamada predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3120a-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="3120a-109">Indica que el método toma un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="3120a-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="3120a-110">Indica que la llamada es a un campo.</span><span class="sxs-lookup"><span data-stu-id="3120a-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="3120a-111">Indica que la llamada es a un método local.</span><span class="sxs-lookup"><span data-stu-id="3120a-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="3120a-112">Indica que la llamada es a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="3120a-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="3120a-113">Indica que la llamada no administrada.</span><span class="sxs-lookup"><span data-stu-id="3120a-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="3120a-114">Indica la creación de instancias de un método genérico.</span><span class="sxs-lookup"><span data-stu-id="3120a-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="3120a-115">Indica una llamada PInvoke de 64 bits a un método que toma un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="3120a-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="3120a-116">Describe un valor de 4 bits no válido.</span><span class="sxs-lookup"><span data-stu-id="3120a-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="3120a-117">Indica que la convención de llamada se describe en los cuatro bits inferiores.</span><span class="sxs-lookup"><span data-stu-id="3120a-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="3120a-118">Indica que el bit superior describe un `this` parámetro.</span><span class="sxs-lookup"><span data-stu-id="3120a-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="3120a-119">Indica que un `this` es describir explícitamente en la firma del parámetro.</span><span class="sxs-lookup"><span data-stu-id="3120a-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="3120a-120">Indica una firma de método genérico con un número de argumentos de tipo explícito.</span><span class="sxs-lookup"><span data-stu-id="3120a-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="3120a-121">Esto precede a un número de parámetros ordinarios.</span><span class="sxs-lookup"><span data-stu-id="3120a-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3120a-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3120a-122">Requirements</span></span>  
 <span data-ttu-id="3120a-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3120a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3120a-124">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3120a-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3120a-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3120a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3120a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="3120a-126">See also</span></span>

- [<span data-ttu-id="3120a-127">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="3120a-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
