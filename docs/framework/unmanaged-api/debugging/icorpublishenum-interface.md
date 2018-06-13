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
ms.openlocfilehash: b3536184fa7798ac8eabe851221ec692c126460b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424019"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="6aa01-102">ICorPublishEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6aa01-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="6aa01-103">Actúa como la interfaz base abstracta para los enumeradores que se utilizan en la publicación de información sobre procesos y dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6aa01-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6aa01-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6aa01-104">Methods</span></span>  
  
|<span data-ttu-id="6aa01-105">Método</span><span class="sxs-lookup"><span data-stu-id="6aa01-105">Method</span></span>|<span data-ttu-id="6aa01-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6aa01-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6aa01-107">Clone (método)</span><span class="sxs-lookup"><span data-stu-id="6aa01-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="6aa01-108">Crea una copia de esta `ICorPublishEnum` objeto.</span><span class="sxs-lookup"><span data-stu-id="6aa01-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="6aa01-109">GetCount (método)</span><span class="sxs-lookup"><span data-stu-id="6aa01-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="6aa01-110">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="6aa01-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="6aa01-111">Reset (método)</span><span class="sxs-lookup"><span data-stu-id="6aa01-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="6aa01-112">Mueve el cursor de hasta el principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="6aa01-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="6aa01-113">Skip (método)</span><span class="sxs-lookup"><span data-stu-id="6aa01-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="6aa01-114">Mueve el cursor hacia delante en la enumeración el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="6aa01-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6aa01-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6aa01-115">Remarks</span></span>  
 <span data-ttu-id="6aa01-116">Los enumeradores siguientes derivan de `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="6aa01-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
-   [<span data-ttu-id="6aa01-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="6aa01-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [<span data-ttu-id="6aa01-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="6aa01-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="6aa01-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6aa01-119">Requirements</span></span>  
 <span data-ttu-id="6aa01-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6aa01-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aa01-121">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="6aa01-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6aa01-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6aa01-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6aa01-123">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aa01-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa01-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="6aa01-124">See Also</span></span>  
 [<span data-ttu-id="6aa01-125">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="6aa01-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)  
 [<span data-ttu-id="6aa01-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6aa01-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
