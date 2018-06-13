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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4bb91423b2eaeda7d945cf14553609fd33ce9b0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443494"
---
# <a name="cormethodimpl-enumeration"></a><span data-ttu-id="c74ff-102">CorMethodImpl (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c74ff-102">CorMethodImpl Enumeration</span></span>
<span data-ttu-id="c74ff-103">Contiene valores que describen las características de implementación de un método.</span><span class="sxs-lookup"><span data-stu-id="c74ff-103">Contains values that describe method implementation features.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c74ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c74ff-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c74ff-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c74ff-105">Members</span></span>  
  
|<span data-ttu-id="c74ff-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c74ff-106">Member</span></span>|<span data-ttu-id="c74ff-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c74ff-107">Description</span></span>|  
|------------|-----------------|  
|`miCodeTypeMask`|<span data-ttu-id="c74ff-108">Marcas que describen el tipo de código.</span><span class="sxs-lookup"><span data-stu-id="c74ff-108">Flags that describe code type.</span></span>|  
|`miIL`|<span data-ttu-id="c74ff-109">Especifica que la implementación del método es el lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="c74ff-109">Specifies that the method implementation is Microsoft intermediate language (MSIL).</span></span>|  
|`miNative`|<span data-ttu-id="c74ff-110">Especifica que la implementación del método es nativa.</span><span class="sxs-lookup"><span data-stu-id="c74ff-110">Specifies that the method implementation is native.</span></span>|  
|`miOPTIL`|<span data-ttu-id="c74ff-111">Especifica que la implementación del método es OPTIL.</span><span class="sxs-lookup"><span data-stu-id="c74ff-111">Specifies that the method implementation is OPTIL.</span></span>|  
|`miRuntime`|<span data-ttu-id="c74ff-112">Especifica que common language runtime proporciona la implementación del método.</span><span class="sxs-lookup"><span data-stu-id="c74ff-112">Specifies that the method implementation is provided by the common language runtime.</span></span>|  
|`miManagedMask`|<span data-ttu-id="c74ff-113">Marcas que indican si el código es administrado o no administrado.</span><span class="sxs-lookup"><span data-stu-id="c74ff-113">Flags that indicate whether the code is managed or unmanaged.</span></span>|  
|`miUnmanaged`|<span data-ttu-id="c74ff-114">Especifica que la implementación del método es no administrada.</span><span class="sxs-lookup"><span data-stu-id="c74ff-114">Specifies that the method implementation is unmanaged.</span></span>|  
|`miManaged`|<span data-ttu-id="c74ff-115">Especifica que se administra la implementación del método.</span><span class="sxs-lookup"><span data-stu-id="c74ff-115">Specifies that the method implementation is managed.</span></span>|  
|`miForwardRef`|<span data-ttu-id="c74ff-116">Especifica que se define el método.</span><span class="sxs-lookup"><span data-stu-id="c74ff-116">Specifies that the method is defined.</span></span> <span data-ttu-id="c74ff-117">Esta marca se utiliza principalmente en escenarios de combinación.</span><span class="sxs-lookup"><span data-stu-id="c74ff-117">This flag is used primarily in merge scenarios.</span></span>|  
|`miPreserveSig`|<span data-ttu-id="c74ff-118">Especifica que la firma del método no se puede trastocar para una conversión HRESULT.</span><span class="sxs-lookup"><span data-stu-id="c74ff-118">Specifies that the method signature cannot be mangled for an HRESULT conversion.</span></span>|  
|`miInternalCall`|<span data-ttu-id="c74ff-119">Reservado para uso interno por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="c74ff-119">Reserved for internal use by the common language runtime.</span></span>|  
|`miSynchronized`|<span data-ttu-id="c74ff-120">Especifica que el método tiene un único subproceso a través de su cuerpo.</span><span class="sxs-lookup"><span data-stu-id="c74ff-120">Specifies that the method is single-threaded through its body.</span></span>|  
|`miNoInlining`|<span data-ttu-id="c74ff-121">Especifica que el método no se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="c74ff-121">Specifies that the method cannot be inlined.</span></span>|  
|`miAggressiveInlining`|<span data-ttu-id="c74ff-122">Especifica que el método debe ser entre línea si es posible.</span><span class="sxs-lookup"><span data-stu-id="c74ff-122">Specifies that the method should be inlined if possible.</span></span>|  
|`miNoOptimization`|<span data-ttu-id="c74ff-123">Especifica que el método no se debe optimizar.</span><span class="sxs-lookup"><span data-stu-id="c74ff-123">Specifies that the method should not be optimized.</span></span>|  
|`miMaxMethodImplVal`|<span data-ttu-id="c74ff-124">El valor válido máximo para un `CorMethodImpl`.</span><span class="sxs-lookup"><span data-stu-id="c74ff-124">The maximum valid value for a `CorMethodImpl`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c74ff-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c74ff-125">Requirements</span></span>  
 <span data-ttu-id="c74ff-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c74ff-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c74ff-127">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c74ff-127">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c74ff-128">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c74ff-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c74ff-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="c74ff-129">See Also</span></span>  
 [<span data-ttu-id="c74ff-130">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="c74ff-130">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
