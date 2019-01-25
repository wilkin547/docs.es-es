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
ms.openlocfilehash: e2be3406cd4330fb477e8a1c89945be1e9f777bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706614"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="d6fb0-102">ICorPublishAppDomainEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6fb0-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="d6fb0-103">Una subclase de la [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interfaz que proporciona métodos que atraviesan una colección de [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objetos que existen actualmente dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="d6fb0-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6fb0-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d6fb0-104">Methods</span></span>  
  
|<span data-ttu-id="d6fb0-105">Método</span><span class="sxs-lookup"><span data-stu-id="d6fb0-105">Method</span></span>|<span data-ttu-id="d6fb0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6fb0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d6fb0-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="d6fb0-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="d6fb0-108">Obtiene el número especificado de `ICorPublishAppDomain` instancias de la colección, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="d6fb0-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6fb0-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6fb0-109">Remarks</span></span>  
 <span data-ttu-id="d6fb0-110">El `ICorPublishAppDomainEnum` interfaz implementa los métodos de la interfaz abstracta, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d6fb0-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6fb0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6fb0-111">Requirements</span></span>  
 <span data-ttu-id="d6fb0-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6fb0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6fb0-113">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="d6fb0-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d6fb0-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6fb0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6fb0-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6fb0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6fb0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6fb0-116">See also</span></span>
- [<span data-ttu-id="d6fb0-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d6fb0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d6fb0-118">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="d6fb0-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
