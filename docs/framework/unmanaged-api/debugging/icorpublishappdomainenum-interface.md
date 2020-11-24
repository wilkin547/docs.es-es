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
ms.openlocfilehash: 5b5a901bef779948467cfcc3d71a1fcd057c1aeb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693720"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="74de4-102">ICorPublishAppDomainEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74de4-102">ICorPublishAppDomainEnum Interface</span></span>

<span data-ttu-id="74de4-103">Una subclase de la interfaz [ICorPublishEnum](icorpublishenum-interface.md) que proporciona métodos para atravesar una colección de objetos [ICorPublishAppDomain](icorpublishappdomain-interface.md) que existen actualmente dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="74de4-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="74de4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="74de4-104">Methods</span></span>  
  
|<span data-ttu-id="74de4-105">Método</span><span class="sxs-lookup"><span data-stu-id="74de4-105">Method</span></span>|<span data-ttu-id="74de4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="74de4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="74de4-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="74de4-107">Next Method</span></span>](icorpublishappdomainenum-next-method.md)|<span data-ttu-id="74de4-108">Obtiene el número especificado de `ICorPublishAppDomain` instancias de la colección, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="74de4-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74de4-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74de4-109">Remarks</span></span>  

 <span data-ttu-id="74de4-110">La `ICorPublishAppDomainEnum` interfaz implementa los métodos de la interfaz abstracta, [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="74de4-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74de4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74de4-111">Requirements</span></span>  

 <span data-ttu-id="74de4-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74de4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74de4-113">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="74de4-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="74de4-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74de4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74de4-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74de4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74de4-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74de4-116">See also</span></span>

- [<span data-ttu-id="74de4-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="74de4-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="74de4-118">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="74de4-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
