---
description: 'Más información acerca de: ICorPublishEnum (interfaz)'
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
ms.openlocfilehash: c0d50f67bd61eecbade0b226f2f569ac26712faf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721611"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="2578a-103">ICorPublishEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2578a-103">ICorPublishEnum Interface</span></span>

<span data-ttu-id="2578a-104">Actúa como la interfaz base abstracta para los enumeradores que se usan en la publicación de información sobre los procesos y los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2578a-104">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2578a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2578a-105">Methods</span></span>  
  
|<span data-ttu-id="2578a-106">Método</span><span class="sxs-lookup"><span data-stu-id="2578a-106">Method</span></span>|<span data-ttu-id="2578a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2578a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2578a-108">Método Clone</span><span class="sxs-lookup"><span data-stu-id="2578a-108">Clone Method</span></span>](icorpublishenum-clone-method.md)|<span data-ttu-id="2578a-109">Crea una copia de este objeto `ICorPublishEnum`.</span><span class="sxs-lookup"><span data-stu-id="2578a-109">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="2578a-110">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="2578a-110">GetCount Method</span></span>](icorpublishenum-getcount-method.md)|<span data-ttu-id="2578a-111">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="2578a-111">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="2578a-112">Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="2578a-112">Reset Method</span></span>](icorpublishenum-reset-method.md)|<span data-ttu-id="2578a-113">Mueve el cursor hasta el principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="2578a-113">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="2578a-114">Método Skip</span><span class="sxs-lookup"><span data-stu-id="2578a-114">Skip Method</span></span>](icorpublishenum-skip-method.md)|<span data-ttu-id="2578a-115">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="2578a-115">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2578a-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2578a-116">Remarks</span></span>  

 <span data-ttu-id="2578a-117">Los enumeradores siguientes derivan de `ICorPublishEnum` :</span><span class="sxs-lookup"><span data-stu-id="2578a-117">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="2578a-118">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="2578a-118">ICorPublishAppDomainEnum</span></span>](icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="2578a-119">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="2578a-119">ICorPublishProcessEnum</span></span>](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="2578a-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2578a-120">Requirements</span></span>  

 <span data-ttu-id="2578a-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2578a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2578a-122">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="2578a-122">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2578a-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2578a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2578a-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2578a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2578a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2578a-125">See also</span></span>

- [<span data-ttu-id="2578a-126">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="2578a-126">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
- [<span data-ttu-id="2578a-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2578a-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
