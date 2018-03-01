---
title: "ICorDebugFrame::GetFunction (Método)"
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
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8d48ac730f22459a71b126126a7418e73805c7e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="a7eac-102">ICorDebugFrame::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="a7eac-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="a7eac-103">Obtiene la función que contiene el código asociado con este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="a7eac-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7eac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7eac-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7eac-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7eac-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="a7eac-106">[out] Un puntero a la dirección de un objeto ICorDebugFunction que representa la función que contiene el código asociado con este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="a7eac-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7eac-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a7eac-107">Remarks</span></span>  
 <span data-ttu-id="a7eac-108">El `GetFunction` método puede producir un error si el marco no está asociado a ninguna función en particular.</span><span class="sxs-lookup"><span data-stu-id="a7eac-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7eac-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7eac-109">Requirements</span></span>  
 <span data-ttu-id="a7eac-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7eac-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7eac-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7eac-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7eac-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7eac-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7eac-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7eac-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
