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
ms.openlocfilehash: 8d6e130981693268ae5c2cd615036b84ca8ed2d8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790699"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="b7526-102">ICorPublishAppDomain::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="b7526-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="b7526-103">Obtiene el identificador único para este [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b7526-103">Gets the unique identifier for this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7526-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7526-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7526-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b7526-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="b7526-106">enuncia Puntero al identificador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7526-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7526-107">Notas</span><span class="sxs-lookup"><span data-stu-id="b7526-107">Remarks</span></span>  
 <span data-ttu-id="b7526-108">El identificador es único solo en el ámbito del proceso contenedor.</span><span class="sxs-lookup"><span data-stu-id="b7526-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7526-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b7526-109">Requirements</span></span>  
 <span data-ttu-id="b7526-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7526-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7526-111">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="b7526-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b7526-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7526-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7526-113">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7526-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7526-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7526-114">See also</span></span>

- [<span data-ttu-id="b7526-115">ICorPublishAppDomain (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7526-115">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
