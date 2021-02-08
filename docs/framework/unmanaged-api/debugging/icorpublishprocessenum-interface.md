---
description: 'Más información acerca de: interfaz ICorPublishProcessEnum ('
title: ICorPublishProcessEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: 87d80d066995dbeca67f461e01652dd3deb3bf1b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790495"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="52d4b-103">ICorPublishProcessEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="52d4b-103">ICorPublishProcessEnum Interface</span></span>

<span data-ttu-id="52d4b-104">Una subclase de la interfaz [ICorPublishEnum](icorpublishenum-interface.md) que proporciona métodos para atravesar una colección de objetos [ICorPublishProcess](icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="52d4b-104">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="52d4b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="52d4b-105">Methods</span></span>  
  
|<span data-ttu-id="52d4b-106">Método</span><span class="sxs-lookup"><span data-stu-id="52d4b-106">Method</span></span>|<span data-ttu-id="52d4b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="52d4b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="52d4b-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="52d4b-108">Next Method</span></span>](icorpublishprocessenum-next-method.md)|<span data-ttu-id="52d4b-109">Obtiene el número especificado de `ICorPublishProcess` instancias de la colección, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="52d4b-109">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52d4b-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="52d4b-110">Remarks</span></span>  

 <span data-ttu-id="52d4b-111">La `ICorPublishProcessEnum` interfaz implementa los métodos de la interfaz abstracta, [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="52d4b-111">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="52d4b-112">`ICorPublishProcessEnum`El método [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) crea una instancia.</span><span class="sxs-lookup"><span data-stu-id="52d4b-112">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="52d4b-113">El recorrido de la colección de `ICorPublishProcess` objetos se basa en los criterios de filtro dados en el momento en que `ICorPublishProcessEnum` se creó la instancia.</span><span class="sxs-lookup"><span data-stu-id="52d4b-113">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52d4b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52d4b-114">Requirements</span></span>  

 <span data-ttu-id="52d4b-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52d4b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52d4b-116">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="52d4b-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="52d4b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52d4b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52d4b-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52d4b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52d4b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="52d4b-119">See also</span></span>

- [<span data-ttu-id="52d4b-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="52d4b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="52d4b-121">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="52d4b-121">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
