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
ms.openlocfilehash: ab331145a8147e8830cb9b158a1975bc748c7cce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716868"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="8a4b7-102">ICorPublishAppDomain::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="8a4b7-102">ICorPublishAppDomain::GetID Method</span></span>

<span data-ttu-id="8a4b7-103">Obtiene el identificador único para este [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8a4b7-103">Gets the unique identifier for this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a4b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a4b7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a4b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a4b7-105">Parameters</span></span>  

 `puId`  
 <span data-ttu-id="8a4b7-106">enuncia Puntero al identificador del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8a4b7-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a4b7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a4b7-107">Remarks</span></span>  

 <span data-ttu-id="8a4b7-108">El identificador es único solo en el ámbito del proceso contenedor.</span><span class="sxs-lookup"><span data-stu-id="8a4b7-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a4b7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a4b7-109">Requirements</span></span>  

 <span data-ttu-id="8a4b7-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a4b7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a4b7-111">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="8a4b7-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8a4b7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a4b7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a4b7-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a4b7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a4b7-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a4b7-114">See also</span></span>

- [<span data-ttu-id="8a4b7-115">ICorPublishAppDomain (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a4b7-115">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
