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
ms.openlocfilehash: 33a72d9aea09f808d42d1a17a7ec5640d20d7c79
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140372"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="ceb99-102">ICorPublishAppDomain::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="ceb99-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="ceb99-103">Obtiene el identificador único para este [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ceb99-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceb99-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ceb99-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ceb99-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ceb99-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="ceb99-106">enuncia Puntero al identificador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ceb99-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ceb99-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ceb99-107">Remarks</span></span>  
 <span data-ttu-id="ceb99-108">El identificador es único solo en el ámbito del proceso contenedor.</span><span class="sxs-lookup"><span data-stu-id="ceb99-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceb99-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ceb99-109">Requirements</span></span>  
 <span data-ttu-id="ceb99-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ceb99-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceb99-111">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="ceb99-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ceb99-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ceb99-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ceb99-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceb99-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb99-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ceb99-114">See also</span></span>

- [<span data-ttu-id="ceb99-115">ICorPublishAppDomain (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ceb99-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
