---
title: ICorPublishEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1eac0b9fe252e476f8ff781f2181a203886d3beb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993543"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="5c739-102">ICorPublishEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c739-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="5c739-103">Sirve como la interfaz base abstracta para los enumeradores que se usan en la publicación de información sobre los procesos y dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5c739-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c739-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5c739-104">Methods</span></span>  
  
|<span data-ttu-id="5c739-105">Método</span><span class="sxs-lookup"><span data-stu-id="5c739-105">Method</span></span>|<span data-ttu-id="5c739-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c739-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c739-107">Clone (método)</span><span class="sxs-lookup"><span data-stu-id="5c739-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="5c739-108">Crea una copia de este `ICorPublishEnum` objeto.</span><span class="sxs-lookup"><span data-stu-id="5c739-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="5c739-109">GetCount (método)</span><span class="sxs-lookup"><span data-stu-id="5c739-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="5c739-110">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="5c739-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="5c739-111">Reset (método)</span><span class="sxs-lookup"><span data-stu-id="5c739-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="5c739-112">Mueve el cursor al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="5c739-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="5c739-113">Skip (método)</span><span class="sxs-lookup"><span data-stu-id="5c739-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="5c739-114">Mueve el cursor hacia delante en la enumeración por el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="5c739-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c739-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c739-115">Remarks</span></span>  
 <span data-ttu-id="5c739-116">Los enumeradores siguientes derivan de `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="5c739-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="5c739-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="5c739-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="5c739-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="5c739-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="5c739-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c739-119">Requirements</span></span>  
 <span data-ttu-id="5c739-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c739-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c739-121">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="5c739-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5c739-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c739-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c739-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c739-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c739-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c739-124">See also</span></span>

- [<span data-ttu-id="5c739-125">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="5c739-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="5c739-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="5c739-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
