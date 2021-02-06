---
description: 'Más información sobre: ICorDebugChain:: GetPrevious (método)'
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
ms.openlocfilehash: 169c46afd545835e6da87686a8e74ecd12173904
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661290"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="44171-103">ICorDebugChain::GetPrevious (Método)</span><span class="sxs-lookup"><span data-stu-id="44171-103">ICorDebugChain::GetPrevious Method</span></span>

<span data-ttu-id="44171-104">Obtiene la cadena de fotogramas anterior para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="44171-104">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44171-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44171-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44171-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44171-106">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="44171-107">enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena anterior de marcos para este subproceso.</span><span class="sxs-lookup"><span data-stu-id="44171-107">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="44171-108">Si esta cadena es la primera cadena, `ppChain` es NULL.</span><span class="sxs-lookup"><span data-stu-id="44171-108">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44171-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44171-109">Requirements</span></span>  

 <span data-ttu-id="44171-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44171-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44171-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44171-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44171-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44171-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44171-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44171-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
