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
ms.openlocfilehash: 63346c679efc083dea9ab0eaa4f983a5308695f8
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895252"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="dfb37-102">ICorDebugAppDomain::GetId (Método)</span><span class="sxs-lookup"><span data-stu-id="dfb37-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="dfb37-103">Obtiene el identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="dfb37-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfb37-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfb37-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfb37-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dfb37-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="dfb37-106">enuncia Identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="dfb37-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfb37-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dfb37-107">Remarks</span></span>  
 <span data-ttu-id="dfb37-108">El identificador del dominio de aplicación es único en el proceso contenedor.</span><span class="sxs-lookup"><span data-stu-id="dfb37-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfb37-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dfb37-109">Requirements</span></span>  
 <span data-ttu-id="dfb37-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfb37-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfb37-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfb37-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfb37-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfb37-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfb37-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfb37-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
