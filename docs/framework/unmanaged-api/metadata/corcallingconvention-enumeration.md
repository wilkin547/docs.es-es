---
description: 'Más información sobre: enumeración Corcallingconvention ('
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
ms.openlocfilehash: 2e823fe3566ef7a54f759cd5debbbd7d5dcf3ceb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678450"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="e5a65-103">CorCallingConvention (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e5a65-103">CorCallingConvention Enumeration</span></span>

<span data-ttu-id="e5a65-104">Contiene valores que describen los tipos de convenciones de llamada que se realizan en código administrado.</span><span class="sxs-lookup"><span data-stu-id="e5a65-104">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5a65-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5a65-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="e5a65-106">Members</span><span class="sxs-lookup"><span data-stu-id="e5a65-106">Members</span></span>  
  
|<span data-ttu-id="e5a65-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="e5a65-107">Member</span></span>|<span data-ttu-id="e5a65-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5a65-108">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="e5a65-109">Indica una Convención de llamada predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e5a65-109">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="e5a65-110">Indica que el método toma un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="e5a65-110">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="e5a65-111">Indica que la llamada es a un campo.</span><span class="sxs-lookup"><span data-stu-id="e5a65-111">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="e5a65-112">Indica que la llamada es a un método local.</span><span class="sxs-lookup"><span data-stu-id="e5a65-112">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="e5a65-113">Indica que la llamada a es una propiedad.</span><span class="sxs-lookup"><span data-stu-id="e5a65-113">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="e5a65-114">Indica que la llamada no está administrada.</span><span class="sxs-lookup"><span data-stu-id="e5a65-114">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="e5a65-115">Indica una creación de instancias de método genérico.</span><span class="sxs-lookup"><span data-stu-id="e5a65-115">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="e5a65-116">Indica una llamada PInvoke de 64 bits a un método que toma un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="e5a65-116">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="e5a65-117">Describe un valor de 4 bits no válido.</span><span class="sxs-lookup"><span data-stu-id="e5a65-117">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="e5a65-118">Indica que la Convención de llamada se describe en los cuatro bits inferiores.</span><span class="sxs-lookup"><span data-stu-id="e5a65-118">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="e5a65-119">Indica que el bit superior describe un `this` parámetro.</span><span class="sxs-lookup"><span data-stu-id="e5a65-119">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="e5a65-120">Indica que un `this` parámetro se describe explícitamente en la firma.</span><span class="sxs-lookup"><span data-stu-id="e5a65-120">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="e5a65-121">Indica una firma de método genérico con un número explícito de argumentos de tipo.</span><span class="sxs-lookup"><span data-stu-id="e5a65-121">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="e5a65-122">Esto precede a un recuento de parámetros ordinarios.</span><span class="sxs-lookup"><span data-stu-id="e5a65-122">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5a65-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5a65-123">Requirements</span></span>  

 <span data-ttu-id="e5a65-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5a65-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5a65-125">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="e5a65-125">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e5a65-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5a65-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a65-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5a65-127">See also</span></span>

- [<span data-ttu-id="e5a65-128">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="e5a65-128">Metadata Enumerations</span></span>](metadata-enumerations.md)
