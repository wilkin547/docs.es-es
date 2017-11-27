---
title: "ICorPublishAppDomain::GetID (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomain.GetID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bfbde806f409f2639b2468e0ba962b1659d1ffc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="c187e-102">ICorPublishAppDomain::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="c187e-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="c187e-103">Obtiene el identificador único para este [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="c187e-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c187e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c187e-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c187e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c187e-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="c187e-106">[out] Un puntero al identificador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c187e-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c187e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c187e-107">Remarks</span></span>  
 <span data-ttu-id="c187e-108">El identificador es único solo en el ámbito del proceso que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="c187e-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c187e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c187e-109">Requirements</span></span>  
 <span data-ttu-id="c187e-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c187e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c187e-111">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="c187e-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c187e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c187e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c187e-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c187e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c187e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c187e-114">See Also</span></span>  
 [<span data-ttu-id="c187e-115">ICorPublishAppDomain (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c187e-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
