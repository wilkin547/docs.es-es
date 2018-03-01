---
title: "ICorDebugAppDomain::GetId (Método)"
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
- ICorDebugAppDomain.GetId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetId
helpviewer_keywords:
- GetId method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetId method [.NET Framework debugging]
ms.assetid: 32c27576-71fa-42ee-8230-67b92913ea08
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8b151d5b0774576e98da5845e5c7afc24ada0001
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="260b1-102">ICorDebugAppDomain::GetId (Método)</span><span class="sxs-lookup"><span data-stu-id="260b1-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="260b1-103">Obtiene el identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="260b1-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="260b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="260b1-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="260b1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="260b1-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="260b1-106">[out] El identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="260b1-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="260b1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="260b1-107">Remarks</span></span>  
 <span data-ttu-id="260b1-108">El identificador para el dominio de aplicación es único dentro del proceso que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="260b1-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="260b1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="260b1-109">Requirements</span></span>  
 <span data-ttu-id="260b1-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="260b1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="260b1-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="260b1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="260b1-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="260b1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="260b1-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="260b1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
