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
ms.openlocfilehash: 3a7267548a957d403cfe02aa3d800a410c14b82a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103416"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="f4c0e-102">ICorPublishProcessEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4c0e-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="f4c0e-103">Una subclase de la interfaz [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) que proporciona métodos para atravesar una colección de objetos [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f4c0e-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4c0e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f4c0e-104">Methods</span></span>  
  
|<span data-ttu-id="f4c0e-105">Método</span><span class="sxs-lookup"><span data-stu-id="f4c0e-105">Method</span></span>|<span data-ttu-id="f4c0e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4c0e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4c0e-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="f4c0e-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="f4c0e-108">Obtiene el número especificado de instancias de `ICorPublishProcess` de la colección, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="f4c0e-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4c0e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f4c0e-109">Remarks</span></span>  
 <span data-ttu-id="f4c0e-110">La interfaz de `ICorPublishProcessEnum` implementa los métodos de la interfaz abstracta, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f4c0e-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="f4c0e-111">El método [ICorPublish:: EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) crea una instancia `ICorPublishProcessEnum`.</span><span class="sxs-lookup"><span data-stu-id="f4c0e-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="f4c0e-112">El recorrido de la colección de objetos de `ICorPublishProcess` se basa en los criterios de filtro dados en el momento en que se creó la instancia de `ICorPublishProcessEnum`.</span><span class="sxs-lookup"><span data-stu-id="f4c0e-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4c0e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4c0e-113">Requirements</span></span>  
 <span data-ttu-id="f4c0e-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4c0e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4c0e-115">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="f4c0e-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f4c0e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4c0e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4c0e-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4c0e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4c0e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4c0e-118">See also</span></span>

- [<span data-ttu-id="f4c0e-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f4c0e-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f4c0e-120">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="f4c0e-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
