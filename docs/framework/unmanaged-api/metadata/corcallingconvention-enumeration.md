---
title: "CorCallingConvention (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorCallingConvention
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCallingConvention
helpviewer_keywords: CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 154fbcc393bb56ab2c249a4928a4451dced9761a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="25fbf-102">CorCallingConvention (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="25fbf-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="25fbf-103">Contiene valores que describen los tipos de convenciones de llamada que se realizan en código administrado.</span><span class="sxs-lookup"><span data-stu-id="25fbf-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25fbf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25fbf-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="25fbf-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="25fbf-105">Members</span></span>  
  
|<span data-ttu-id="25fbf-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="25fbf-106">Member</span></span>|<span data-ttu-id="25fbf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="25fbf-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="25fbf-108">Indica una convención de llamada predeterminada.</span><span class="sxs-lookup"><span data-stu-id="25fbf-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="25fbf-109">Indica que el método toma un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="25fbf-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="25fbf-110">Indica que la llamada es a un campo.</span><span class="sxs-lookup"><span data-stu-id="25fbf-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="25fbf-111">Indica que la llamada es a un método local.</span><span class="sxs-lookup"><span data-stu-id="25fbf-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="25fbf-112">Indica que la llamada es a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="25fbf-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="25fbf-113">Indica que la llamada no administrada.</span><span class="sxs-lookup"><span data-stu-id="25fbf-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="25fbf-114">Indica la creación de una instancia de método genérico.</span><span class="sxs-lookup"><span data-stu-id="25fbf-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="25fbf-115">Indica una llamada PInvoke de 64 bits a un método que toma un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="25fbf-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="25fbf-116">Describe un valor de 4 bits no válido.</span><span class="sxs-lookup"><span data-stu-id="25fbf-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="25fbf-117">Indica que la convención de llamada es descrita por los cuatro bits inferiores.</span><span class="sxs-lookup"><span data-stu-id="25fbf-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="25fbf-118">Indica que el bit superior describe un `this` parámetro.</span><span class="sxs-lookup"><span data-stu-id="25fbf-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="25fbf-119">Indica que un `this` parámetro está descrito explícitamente en la firma.</span><span class="sxs-lookup"><span data-stu-id="25fbf-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="25fbf-120">Indica una firma de método genérico con un número de argumentos de tipo explícito.</span><span class="sxs-lookup"><span data-stu-id="25fbf-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="25fbf-121">Esto precede a un recuento de parámetros ordinario.</span><span class="sxs-lookup"><span data-stu-id="25fbf-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="25fbf-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25fbf-122">Requirements</span></span>  
 <span data-ttu-id="25fbf-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25fbf-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25fbf-124">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="25fbf-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="25fbf-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25fbf-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25fbf-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="25fbf-126">See Also</span></span>  
 [<span data-ttu-id="25fbf-127">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="25fbf-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
