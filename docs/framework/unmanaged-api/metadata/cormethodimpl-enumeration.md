---
title: CorMethodImpl (Enumeración)
ms.date: 03/30/2017
api_name:
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
ms.openlocfilehash: b32e8f0b03ef6d550c384f3d932cc295a7270028
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007668"
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="5f486-102">CorMethodImpl (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5f486-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="5f486-103">Contiene valores que describen las características de implementación de un método.</span><span class="sxs-lookup"><span data-stu-id="5f486-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f486-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f486-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a><span data-ttu-id="5f486-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5f486-105">Members</span></span>  
  
|<span data-ttu-id="5f486-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5f486-106">Member</span></span>|<span data-ttu-id="5f486-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f486-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="5f486-108">Marcas que describen el tipo de código.</span><span class="sxs-lookup"><span data-stu-id="5f486-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="5f486-109">Especifica que la implementación del método es el lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="5f486-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="5f486-110">Especifica que la implementación del método es nativa.</span><span class="sxs-lookup"><span data-stu-id="5f486-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="5f486-111">Especifica que la implementación del método es OPTIl.</span><span class="sxs-lookup"><span data-stu-id="5f486-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="5f486-112">Especifica que la implementación del método la proporciona el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="5f486-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="5f486-113">Marcas que indican si el código es administrado o no administrado.</span><span class="sxs-lookup"><span data-stu-id="5f486-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="5f486-114">Especifica que la implementación del método no está administrada.</span><span class="sxs-lookup"><span data-stu-id="5f486-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="5f486-115">Especifica que la implementación del método está administrada.</span><span class="sxs-lookup"><span data-stu-id="5f486-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="5f486-116">Especifica que el método está definido.</span><span class="sxs-lookup"><span data-stu-id="5f486-116">Specifies that the method is defined.</span></span> <span data-ttu-id="5f486-117">Esta marca se utiliza principalmente en escenarios de combinación.</span><span class="sxs-lookup"><span data-stu-id="5f486-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="5f486-118">Especifica que la firma del método no se puede alterar para una conversión HRESULT.</span><span class="sxs-lookup"><span data-stu-id="5f486-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="5f486-119">Reservado para uso interno por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="5f486-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="5f486-120">Especifica que el método tiene un único subproceso a través de su cuerpo.</span><span class="sxs-lookup"><span data-stu-id="5f486-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="5f486-121">Especifica que el método no se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="5f486-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="5f486-122">Especifica que el método debe insertarse si es posible.</span><span class="sxs-lookup"><span data-stu-id="5f486-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="5f486-123">Especifica que el método no se debe optimizar.</span><span class="sxs-lookup"><span data-stu-id="5f486-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="5f486-124">Valor máximo válido para `CorMethodImpl` .</span><span class="sxs-lookup"><span data-stu-id="5f486-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f486-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f486-125">Requirements</span></span>  
 <span data-ttu-id="5f486-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f486-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f486-127">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="5f486-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5f486-128">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f486-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f486-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f486-129">See also</span></span>

- [<span data-ttu-id="5f486-130">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="5f486-130">Metadata Enumerations</span></span>](metadata-enumerations.md)
