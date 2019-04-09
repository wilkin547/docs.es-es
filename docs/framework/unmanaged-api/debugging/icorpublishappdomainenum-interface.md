---
title: ICorPublishAppDomainEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f6d4af7c01f91dff77d6ba715ef845f523c7fb6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090054"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="2998a-102">ICorPublishAppDomainEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2998a-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="2998a-103">Una subclase de la [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interfaz que proporciona métodos que atraviesan una colección de [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objetos que existen actualmente dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="2998a-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2998a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2998a-104">Methods</span></span>  
  
|<span data-ttu-id="2998a-105">Método</span><span class="sxs-lookup"><span data-stu-id="2998a-105">Method</span></span>|<span data-ttu-id="2998a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2998a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2998a-107">Método Next</span><span class="sxs-lookup"><span data-stu-id="2998a-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="2998a-108">Obtiene el número especificado de `ICorPublishAppDomain` instancias de la colección, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="2998a-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2998a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2998a-109">Remarks</span></span>  
 <span data-ttu-id="2998a-110">El `ICorPublishAppDomainEnum` interfaz implementa los métodos de la interfaz abstracta, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2998a-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2998a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2998a-111">Requirements</span></span>  
 <span data-ttu-id="2998a-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2998a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2998a-113">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="2998a-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2998a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2998a-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2998a-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2998a-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2998a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2998a-116">See also</span></span>

- [<span data-ttu-id="2998a-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2998a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2998a-118">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="2998a-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
