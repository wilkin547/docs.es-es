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
ms.openlocfilehash: 310319e8fefe80017c58706e2beaee5eb1e78422
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007915"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="c49cc-102">CorCallingConvention (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c49cc-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="c49cc-103">Contiene valores que describen los tipos de convenciones de llamada que se realizan en código administrado.</span><span class="sxs-lookup"><span data-stu-id="c49cc-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c49cc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c49cc-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c49cc-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c49cc-105">Members</span></span>  
  
|<span data-ttu-id="c49cc-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c49cc-106">Member</span></span>|<span data-ttu-id="c49cc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c49cc-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="c49cc-108">Indica una Convención de llamada predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c49cc-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="c49cc-109">Indica que el método toma un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="c49cc-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="c49cc-110">Indica que la llamada es a un campo.</span><span class="sxs-lookup"><span data-stu-id="c49cc-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="c49cc-111">Indica que la llamada es a un método local.</span><span class="sxs-lookup"><span data-stu-id="c49cc-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="c49cc-112">Indica que la llamada a es una propiedad.</span><span class="sxs-lookup"><span data-stu-id="c49cc-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="c49cc-113">Indica que la llamada no está administrada.</span><span class="sxs-lookup"><span data-stu-id="c49cc-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="c49cc-114">Indica una creación de instancias de método genérico.</span><span class="sxs-lookup"><span data-stu-id="c49cc-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="c49cc-115">Indica una llamada PInvoke de 64 bits a un método que toma un número variable de parámetros.</span><span class="sxs-lookup"><span data-stu-id="c49cc-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="c49cc-116">Describe un valor de 4 bits no válido.</span><span class="sxs-lookup"><span data-stu-id="c49cc-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="c49cc-117">Indica que la Convención de llamada se describe en los cuatro bits inferiores.</span><span class="sxs-lookup"><span data-stu-id="c49cc-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="c49cc-118">Indica que el bit superior describe un `this` parámetro.</span><span class="sxs-lookup"><span data-stu-id="c49cc-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="c49cc-119">Indica que un `this` parámetro se describe explícitamente en la firma.</span><span class="sxs-lookup"><span data-stu-id="c49cc-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="c49cc-120">Indica una firma de método genérico con un número explícito de argumentos de tipo.</span><span class="sxs-lookup"><span data-stu-id="c49cc-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="c49cc-121">Esto precede a un recuento de parámetros ordinarios.</span><span class="sxs-lookup"><span data-stu-id="c49cc-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c49cc-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c49cc-122">Requirements</span></span>  
 <span data-ttu-id="c49cc-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c49cc-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c49cc-124">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="c49cc-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c49cc-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c49cc-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c49cc-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c49cc-126">See also</span></span>

- [<span data-ttu-id="c49cc-127">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="c49cc-127">Metadata Enumerations</span></span>](metadata-enumerations.md)
