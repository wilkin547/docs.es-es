---
title: ICorPublishAppDomain::GetID (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41b39597a5a438592d2ae07a16510f5406a91a43
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422837"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="9d0aa-102">ICorPublishAppDomain::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="9d0aa-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="9d0aa-103">Obtiene el identificador único para este [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9d0aa-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d0aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d0aa-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d0aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d0aa-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="9d0aa-106">[out] Un puntero al identificador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9d0aa-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d0aa-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9d0aa-107">Remarks</span></span>  
 <span data-ttu-id="9d0aa-108">El identificador es único solo en el ámbito del proceso que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="9d0aa-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d0aa-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d0aa-109">Requirements</span></span>  
 <span data-ttu-id="9d0aa-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d0aa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d0aa-111">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="9d0aa-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="9d0aa-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d0aa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d0aa-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d0aa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d0aa-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d0aa-114">See Also</span></span>  
 [<span data-ttu-id="9d0aa-115">ICorPublishAppDomain (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d0aa-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
