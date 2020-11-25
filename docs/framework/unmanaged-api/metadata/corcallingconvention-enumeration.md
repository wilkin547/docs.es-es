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
ms.openlocfilehash: c9b20500a4a9e4649a938e00e3b059d1395da1d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718935"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="59445-102">CorCallingConvention (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="59445-102">CorCallingConvention Enumeration</span></span>

<span data-ttu-id="59445-103">Contiene valores que describen los tipos de convenciones de llamada que se realizan en código administrado.</span><span class="sxs-lookup"><span data-stu-id="59445-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59445-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59445-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="59445-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="59445-105">Members</span></span>  
  
|<span data-ttu-id="59445-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="59445-106">Member</span></span>|<span data-ttu-id="59445-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="59445-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="59445-108">Indica una Convención de llamada predeterminada.</span><span class="sxs-lookup"><span data-stu-id="59445-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="59445-109">Indica que el método toma un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="59445-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="59445-110">Indica que la llamada es a un campo.</span><span class="sxs-lookup"><span data-stu-id="59445-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="59445-111">Indica que la llamada es a un método local.</span><span class="sxs-lookup"><span data-stu-id="59445-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="59445-112">Indica que la llamada a es una propiedad.</span><span class="sxs-lookup"><span data-stu-id="59445-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="59445-113">Indica que la llamada no está administrada.</span><span class="sxs-lookup"><span data-stu-id="59445-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="59445-114">Indica una creación de instancias de método genérico.</span><span class="sxs-lookup"><span data-stu-id="59445-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="59445-115">Indica una llamada PInvoke de 64 bits a un método que toma un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="59445-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="59445-116">Describe un valor de 4 bits no válido.</span><span class="sxs-lookup"><span data-stu-id="59445-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="59445-117">Indica que la Convención de llamada se describe en los cuatro bits inferiores.</span><span class="sxs-lookup"><span data-stu-id="59445-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="59445-118">Indica que el bit superior describe un `this` parámetro.</span><span class="sxs-lookup"><span data-stu-id="59445-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="59445-119">Indica que un `this` parámetro se describe explícitamente en la firma.</span><span class="sxs-lookup"><span data-stu-id="59445-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="59445-120">Indica una firma de método genérico con un número explícito de argumentos de tipo.</span><span class="sxs-lookup"><span data-stu-id="59445-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="59445-121">Esto precede a un recuento de parámetros ordinarios.</span><span class="sxs-lookup"><span data-stu-id="59445-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59445-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59445-122">Requirements</span></span>  

 <span data-ttu-id="59445-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59445-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59445-124">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="59445-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="59445-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59445-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59445-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59445-126">See also</span></span>

- [<span data-ttu-id="59445-127">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="59445-127">Metadata Enumerations</span></span>](metadata-enumerations.md)
