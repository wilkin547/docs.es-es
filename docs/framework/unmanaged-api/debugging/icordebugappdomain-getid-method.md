---
title: ICorDebugAppDomain::GetId (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0aefc19ca0c255c9c8ea40fcc12fc5cba1b00f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996260"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="93469-102">ICorDebugAppDomain::GetId (Método)</span><span class="sxs-lookup"><span data-stu-id="93469-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="93469-103">Obtiene el identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="93469-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93469-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93469-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93469-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="93469-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="93469-106">[out] El identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="93469-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93469-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93469-107">Remarks</span></span>  
 <span data-ttu-id="93469-108">El identificador del dominio de aplicación es único dentro del proceso que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="93469-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93469-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93469-109">Requirements</span></span>  
 <span data-ttu-id="93469-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93469-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93469-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93469-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93469-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93469-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93469-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93469-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
