---
title: "CorMethodImpl (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorMethodImpl
api_location: mscoree.dll
api_type: COM
f1_keywords: CorMethodImpl
helpviewer_keywords: CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 85ee55c0d4ec0d3fb8c18dff570afefeb2eaf25e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="e702c-102">CorMethodImpl (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e702c-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="e702c-103">Contiene valores que describen las características de implementación de un método.</span><span class="sxs-lookup"><span data-stu-id="e702c-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e702c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e702c-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="e702c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e702c-105">Members</span></span>  
  
|<span data-ttu-id="e702c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e702c-106">Member</span></span>|<span data-ttu-id="e702c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e702c-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="e702c-108">Marcas que describen el tipo de código.</span><span class="sxs-lookup"><span data-stu-id="e702c-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="e702c-109">Especifica que la implementación del método es el lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="e702c-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="e702c-110">Especifica que la implementación del método es nativa.</span><span class="sxs-lookup"><span data-stu-id="e702c-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="e702c-111">Especifica que la implementación del método es OPTIL.</span><span class="sxs-lookup"><span data-stu-id="e702c-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="e702c-112">Especifica que common language runtime proporciona la implementación del método.</span><span class="sxs-lookup"><span data-stu-id="e702c-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="e702c-113">Marcas que indican si el código es administrado o no administrado.</span><span class="sxs-lookup"><span data-stu-id="e702c-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="e702c-114">Especifica que la implementación del método es no administrada.</span><span class="sxs-lookup"><span data-stu-id="e702c-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="e702c-115">Especifica que se administra la implementación del método.</span><span class="sxs-lookup"><span data-stu-id="e702c-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="e702c-116">Especifica que se define el método.</span><span class="sxs-lookup"><span data-stu-id="e702c-116">Specifies that the method is defined.</span></span> <span data-ttu-id="e702c-117">Esta marca se utiliza principalmente en escenarios de combinación.</span><span class="sxs-lookup"><span data-stu-id="e702c-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="e702c-118">Especifica que la firma del método no se puede trastocar para una conversión HRESULT.</span><span class="sxs-lookup"><span data-stu-id="e702c-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="e702c-119">Reservado para uso interno por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="e702c-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="e702c-120">Especifica que el método tiene un único subproceso a través de su cuerpo.</span><span class="sxs-lookup"><span data-stu-id="e702c-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="e702c-121">Especifica que el método no se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="e702c-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="e702c-122">Especifica que el método debe ser entre línea si es posible.</span><span class="sxs-lookup"><span data-stu-id="e702c-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="e702c-123">Especifica que el método no se debe optimizar.</span><span class="sxs-lookup"><span data-stu-id="e702c-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="e702c-124">El valor válido máximo para un `CorMethodImpl`.</span><span class="sxs-lookup"><span data-stu-id="e702c-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e702c-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e702c-125">Requirements</span></span>  
 <span data-ttu-id="e702c-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e702c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e702c-127">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e702c-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e702c-128">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e702c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e702c-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e702c-129">See Also</span></span>  
 [<span data-ttu-id="e702c-130">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="e702c-130">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
