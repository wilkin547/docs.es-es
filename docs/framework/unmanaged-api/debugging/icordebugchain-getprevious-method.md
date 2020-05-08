---
title: ICorDebugChain::GetPrevious (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
ms.openlocfilehash: a57e73495ac22a25a5f13c06d4c75dee7dde41e0
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894633"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="4fd30-102">ICorDebugChain::GetPrevious (Método)</span><span class="sxs-lookup"><span data-stu-id="4fd30-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="4fd30-103">Obtiene la cadena de fotogramas anterior para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="4fd30-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fd30-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4fd30-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fd30-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4fd30-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="4fd30-106">enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena anterior de marcos para este subproceso.</span><span class="sxs-lookup"><span data-stu-id="4fd30-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="4fd30-107">Si esta cadena es la primera cadena, `ppChain` es NULL.</span><span class="sxs-lookup"><span data-stu-id="4fd30-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fd30-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fd30-108">Requirements</span></span>  
 <span data-ttu-id="4fd30-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fd30-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fd30-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4fd30-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4fd30-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fd30-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fd30-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fd30-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
