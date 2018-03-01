---
title: "ICorPublishEnum::GetCount (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 023965489530e70deb7dc9460418ef0d56654081
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="875ed-102">ICorPublishEnum::GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="875ed-102">ICorPublishEnum::GetCount Method</span></span>
<span data-ttu-id="875ed-103">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="875ed-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="875ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="875ed-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="875ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="875ed-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="875ed-106">[out] Un puntero al número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="875ed-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="875ed-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="875ed-107">Requirements</span></span>  
 <span data-ttu-id="875ed-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="875ed-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="875ed-109">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="875ed-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="875ed-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="875ed-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="875ed-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="875ed-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="875ed-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="875ed-112">See Also</span></span>  
 [<span data-ttu-id="875ed-113">ICorPublishEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="875ed-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
