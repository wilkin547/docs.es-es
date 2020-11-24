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
ms.openlocfilehash: 492d4b727ce507340fec47d30a791aa49d0cecb6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693351"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="14da3-102">ICorPublishEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="14da3-102">ICorPublishEnum Interface</span></span>

<span data-ttu-id="14da3-103">Actúa como la interfaz base abstracta para los enumeradores que se usan en la publicación de información sobre los procesos y los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="14da3-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14da3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="14da3-104">Methods</span></span>  
  
|<span data-ttu-id="14da3-105">Método</span><span class="sxs-lookup"><span data-stu-id="14da3-105">Method</span></span>|<span data-ttu-id="14da3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="14da3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14da3-107">Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="14da3-107">Clone Method</span></span>](icorpublishenum-clone-method.md)|<span data-ttu-id="14da3-108">Crea una copia de este objeto `ICorPublishEnum`.</span><span class="sxs-lookup"><span data-stu-id="14da3-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="14da3-109">GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="14da3-109">GetCount Method</span></span>](icorpublishenum-getcount-method.md)|<span data-ttu-id="14da3-110">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="14da3-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="14da3-111">Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="14da3-111">Reset Method</span></span>](icorpublishenum-reset-method.md)|<span data-ttu-id="14da3-112">Mueve el cursor hasta el principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="14da3-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="14da3-113">Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="14da3-113">Skip Method</span></span>](icorpublishenum-skip-method.md)|<span data-ttu-id="14da3-114">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="14da3-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14da3-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14da3-115">Remarks</span></span>  

 <span data-ttu-id="14da3-116">Los enumeradores siguientes derivan de `ICorPublishEnum` :</span><span class="sxs-lookup"><span data-stu-id="14da3-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="14da3-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="14da3-117">ICorPublishAppDomainEnum</span></span>](icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="14da3-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="14da3-118">ICorPublishProcessEnum</span></span>](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="14da3-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14da3-119">Requirements</span></span>  

 <span data-ttu-id="14da3-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14da3-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14da3-121">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="14da3-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="14da3-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14da3-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14da3-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14da3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14da3-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14da3-124">See also</span></span>

- [<span data-ttu-id="14da3-125">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="14da3-125">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
- [<span data-ttu-id="14da3-126">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="14da3-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
