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
ms.openlocfilehash: 61cac0922423acabef3d47618d98ddf082d071da
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790678"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="6dde1-102">ICorPublishAppDomainEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6dde1-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="6dde1-103">Una subclase de la interfaz [ICorPublishEnum](icorpublishenum-interface.md) que proporciona métodos para atravesar una colección de objetos [ICorPublishAppDomain](icorpublishappdomain-interface.md) que existen actualmente dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="6dde1-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6dde1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6dde1-104">Methods</span></span>  
  
|<span data-ttu-id="6dde1-105">Método</span><span class="sxs-lookup"><span data-stu-id="6dde1-105">Method</span></span>|<span data-ttu-id="6dde1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6dde1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6dde1-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="6dde1-107">Next Method</span></span>](icorpublishappdomainenum-next-method.md)|<span data-ttu-id="6dde1-108">Obtiene el número especificado de instancias de `ICorPublishAppDomain` de la colección, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="6dde1-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dde1-109">Notas</span><span class="sxs-lookup"><span data-stu-id="6dde1-109">Remarks</span></span>  
 <span data-ttu-id="6dde1-110">La interfaz de `ICorPublishAppDomainEnum` implementa los métodos de la interfaz abstracta, [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6dde1-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dde1-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6dde1-111">Requirements</span></span>  
 <span data-ttu-id="6dde1-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dde1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dde1-113">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="6dde1-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6dde1-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6dde1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6dde1-115">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dde1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dde1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dde1-116">See also</span></span>

- [<span data-ttu-id="6dde1-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6dde1-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6dde1-118">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="6dde1-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
