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
ms.openlocfilehash: 8122f1b5017faac3425d59d12d77f84180134d65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401634"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="d208f-102">ICorDebugAppDomain::GetId (Método)</span><span class="sxs-lookup"><span data-stu-id="d208f-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="d208f-103">Obtiene el identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d208f-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d208f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d208f-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d208f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d208f-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="d208f-106">[out] El identificador único del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d208f-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d208f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d208f-107">Remarks</span></span>  
 <span data-ttu-id="d208f-108">El identificador para el dominio de aplicación es único dentro del proceso que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="d208f-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d208f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d208f-109">Requirements</span></span>  
 <span data-ttu-id="d208f-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d208f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d208f-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d208f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d208f-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d208f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d208f-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d208f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
