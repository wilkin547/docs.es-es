---
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
ms.openlocfilehash: 657d2d638a419ba88d4cf7152f4505de1bd23706
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421077"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="5129e-102">ICorPublishProcessEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5129e-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="5129e-103">Una subclase de la interfaz [ICorPublishEnum](icorpublishenum-interface.md) que proporciona métodos para atravesar una colección de objetos [ICorPublishProcess](icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5129e-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5129e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5129e-104">Methods</span></span>  
  
|<span data-ttu-id="5129e-105">Método</span><span class="sxs-lookup"><span data-stu-id="5129e-105">Method</span></span>|<span data-ttu-id="5129e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5129e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5129e-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="5129e-107">Next Method</span></span>](icorpublishprocessenum-next-method.md)|<span data-ttu-id="5129e-108">Obtiene el número especificado de `ICorPublishProcess` instancias de la colección, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="5129e-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5129e-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5129e-109">Remarks</span></span>  
 <span data-ttu-id="5129e-110">La `ICorPublishProcessEnum` interfaz implementa los métodos de la interfaz abstracta, [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5129e-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="5129e-111">`ICorPublishProcessEnum`El método [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) crea una instancia.</span><span class="sxs-lookup"><span data-stu-id="5129e-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="5129e-112">El recorrido de la colección de `ICorPublishProcess` objetos se basa en los criterios de filtro dados en el momento en que `ICorPublishProcessEnum` se creó la instancia.</span><span class="sxs-lookup"><span data-stu-id="5129e-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5129e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5129e-113">Requirements</span></span>  
 <span data-ttu-id="5129e-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5129e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5129e-115">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="5129e-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5129e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5129e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5129e-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5129e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5129e-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="5129e-118">See also</span></span>

- [<span data-ttu-id="5129e-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5129e-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5129e-120">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="5129e-120">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
