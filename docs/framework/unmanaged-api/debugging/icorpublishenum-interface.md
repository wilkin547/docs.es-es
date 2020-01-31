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
ms.openlocfilehash: f54bb99df60d7b3fb7bb98de75fbae210597e45c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790622"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="feddd-102">ICorPublishEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="feddd-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="feddd-103">Actúa como la interfaz base abstracta para los enumeradores que se usan en la publicación de información sobre los procesos y los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="feddd-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="feddd-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="feddd-104">Methods</span></span>  
  
|<span data-ttu-id="feddd-105">Método</span><span class="sxs-lookup"><span data-stu-id="feddd-105">Method</span></span>|<span data-ttu-id="feddd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="feddd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="feddd-107">Clone (método)</span><span class="sxs-lookup"><span data-stu-id="feddd-107">Clone Method</span></span>](icorpublishenum-clone-method.md)|<span data-ttu-id="feddd-108">Crea una copia de este objeto `ICorPublishEnum`.</span><span class="sxs-lookup"><span data-stu-id="feddd-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="feddd-109">GetCount (método)</span><span class="sxs-lookup"><span data-stu-id="feddd-109">GetCount Method</span></span>](icorpublishenum-getcount-method.md)|<span data-ttu-id="feddd-110">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="feddd-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="feddd-111">Reset (método)</span><span class="sxs-lookup"><span data-stu-id="feddd-111">Reset Method</span></span>](icorpublishenum-reset-method.md)|<span data-ttu-id="feddd-112">Mueve el cursor hasta el principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="feddd-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="feddd-113">Skip (método)</span><span class="sxs-lookup"><span data-stu-id="feddd-113">Skip Method</span></span>](icorpublishenum-skip-method.md)|<span data-ttu-id="feddd-114">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="feddd-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="feddd-115">Notas</span><span class="sxs-lookup"><span data-stu-id="feddd-115">Remarks</span></span>  
 <span data-ttu-id="feddd-116">Los enumeradores siguientes derivan de `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="feddd-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="feddd-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="feddd-117">ICorPublishAppDomainEnum</span></span>](icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="feddd-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="feddd-118">ICorPublishProcessEnum</span></span>](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="feddd-119">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="feddd-119">Requirements</span></span>  
 <span data-ttu-id="feddd-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="feddd-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="feddd-121">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="feddd-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="feddd-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="feddd-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="feddd-123">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="feddd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feddd-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="feddd-124">See also</span></span>

- [<span data-ttu-id="feddd-125">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="feddd-125">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
- [<span data-ttu-id="feddd-126">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="feddd-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
