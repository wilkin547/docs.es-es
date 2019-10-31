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
ms.openlocfilehash: c7598a9d93631ca93187886fd8929ba10726dad7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124735"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="411aa-102">ICorDebugChain::GetPrevious (Método)</span><span class="sxs-lookup"><span data-stu-id="411aa-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="411aa-103">Obtiene la cadena de fotogramas anterior para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="411aa-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="411aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="411aa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="411aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="411aa-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="411aa-106">enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena anterior de marcos para este subproceso.</span><span class="sxs-lookup"><span data-stu-id="411aa-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="411aa-107">Si esta cadena es la primera cadena, `ppChain` es NULL.</span><span class="sxs-lookup"><span data-stu-id="411aa-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="411aa-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="411aa-108">Requirements</span></span>  
 <span data-ttu-id="411aa-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="411aa-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="411aa-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="411aa-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="411aa-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="411aa-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="411aa-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="411aa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
