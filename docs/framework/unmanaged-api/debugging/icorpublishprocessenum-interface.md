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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5186df61eb82b29fcfa9776408498b748068e122
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993491"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="20baa-102">ICorPublishProcessEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20baa-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="20baa-103">Una subclase de la [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interfaz que proporciona métodos que atraviesan una colección de [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objetos.</span><span class="sxs-lookup"><span data-stu-id="20baa-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="20baa-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="20baa-104">Methods</span></span>  
  
|<span data-ttu-id="20baa-105">Método</span><span class="sxs-lookup"><span data-stu-id="20baa-105">Method</span></span>|<span data-ttu-id="20baa-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="20baa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="20baa-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="20baa-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="20baa-108">Obtiene el número especificado de `ICorPublishProcess` instancias de la colección, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="20baa-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20baa-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20baa-109">Remarks</span></span>  
 <span data-ttu-id="20baa-110">El `ICorPublishProcessEnum` interfaz implementa los métodos de la interfaz abstracta, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="20baa-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="20baa-111">Un `ICorPublishProcessEnum` crea instancia el [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="20baa-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="20baa-112">El recorrido de la colección de `ICorPublishProcess` objetos se basa en los criterios de filtro proporcionados en el momento del `ICorPublishProcessEnum` se creó la instancia.</span><span class="sxs-lookup"><span data-stu-id="20baa-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20baa-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20baa-113">Requirements</span></span>  
 <span data-ttu-id="20baa-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20baa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20baa-115">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="20baa-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="20baa-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20baa-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20baa-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20baa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20baa-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="20baa-118">See also</span></span>

- [<span data-ttu-id="20baa-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="20baa-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="20baa-120">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="20baa-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
