---
description: 'Más información sobre: enumeración CorMethodImpl ('
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
ms.openlocfilehash: 157db81a72742f1f2aae7e95249b819b2396ef4b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784397"
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="b79db-103">CorMethodImpl (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b79db-103">CorMethodImpl Enumeration</span></span>

<span data-ttu-id="b79db-104">Contiene valores que describen las características de implementación de un método.</span><span class="sxs-lookup"><span data-stu-id="b79db-104">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b79db-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b79db-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b79db-106">Members</span><span class="sxs-lookup"><span data-stu-id="b79db-106">Members</span></span>  
  
|<span data-ttu-id="b79db-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="b79db-107">Member</span></span>|<span data-ttu-id="b79db-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b79db-108">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="b79db-109">Marcas que describen el tipo de código.</span><span class="sxs-lookup"><span data-stu-id="b79db-109">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="b79db-110">Especifica que la implementación del método es el lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="b79db-110">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="b79db-111">Especifica que la implementación del método es nativa.</span><span class="sxs-lookup"><span data-stu-id="b79db-111">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="b79db-112">Especifica que la implementación del método es OPTIl.</span><span class="sxs-lookup"><span data-stu-id="b79db-112">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="b79db-113">Especifica que la implementación del método la proporciona el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b79db-113">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="b79db-114">Marcas que indican si el código es administrado o no administrado.</span><span class="sxs-lookup"><span data-stu-id="b79db-114">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="b79db-115">Especifica que la implementación del método no está administrada.</span><span class="sxs-lookup"><span data-stu-id="b79db-115">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="b79db-116">Especifica que la implementación del método está administrada.</span><span class="sxs-lookup"><span data-stu-id="b79db-116">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="b79db-117">Especifica que el método está definido.</span><span class="sxs-lookup"><span data-stu-id="b79db-117">Specifies that the method is defined.</span></span> <span data-ttu-id="b79db-118">Esta marca se utiliza principalmente en escenarios de combinación.</span><span class="sxs-lookup"><span data-stu-id="b79db-118">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="b79db-119">Especifica que la firma del método no se puede alterar para una conversión HRESULT.</span><span class="sxs-lookup"><span data-stu-id="b79db-119">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="b79db-120">Reservado para uso interno por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b79db-120">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="b79db-121">Especifica que el método tiene un único subproceso a través de su cuerpo.</span><span class="sxs-lookup"><span data-stu-id="b79db-121">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="b79db-122">Especifica que el método no se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="b79db-122">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="b79db-123">Especifica que el método debe insertarse si es posible.</span><span class="sxs-lookup"><span data-stu-id="b79db-123">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="b79db-124">Especifica que el método no se debe optimizar.</span><span class="sxs-lookup"><span data-stu-id="b79db-124">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="b79db-125">Valor máximo válido para `CorMethodImpl` .</span><span class="sxs-lookup"><span data-stu-id="b79db-125">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b79db-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b79db-126">Requirements</span></span>  

 <span data-ttu-id="b79db-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b79db-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b79db-128">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="b79db-128">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b79db-129">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b79db-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b79db-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b79db-130">See also</span></span>

- [<span data-ttu-id="b79db-131">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="b79db-131">Metadata Enumerations</span></span>](metadata-enumerations.md)
