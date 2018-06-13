---
title: ICorDebugEval::IsActive (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fe29b3e35d2fbd42fac2d9ec1d1c594abe1239c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411163"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="377be-102">ICorDebugEval::IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="377be-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="377be-103">Obtiene un valor que indica si este objeto ICorDebugEval se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="377be-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="377be-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="377be-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="377be-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="377be-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="377be-106">[out] Puntero a un valor que indica si esta evaluación está activa.</span><span class="sxs-lookup"><span data-stu-id="377be-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="377be-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="377be-107">Requirements</span></span>  
 <span data-ttu-id="377be-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="377be-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="377be-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="377be-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="377be-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="377be-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="377be-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="377be-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
