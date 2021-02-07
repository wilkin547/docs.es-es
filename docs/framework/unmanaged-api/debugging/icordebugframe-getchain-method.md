---
description: 'Más información sobre: ICorDebugFrame:: Getchain ((método)'
title: ICorDebugFrame::GetChain (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetChain
helpviewer_keywords:
- ICorDebugFrame::GetChain method [.NET Framework debugging]
- GetChain method [.NET Framework debugging]
ms.assetid: e28e51d3-8f73-494f-bcd4-48bac239fbe1
topic_type:
- apiref
ms.openlocfilehash: d162d484a54f107fb5937e57f60e2b82cad90ca1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693062"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="2dde6-103">ICorDebugFrame::GetChain (Método)</span><span class="sxs-lookup"><span data-stu-id="2dde6-103">ICorDebugFrame::GetChain Method</span></span>

<span data-ttu-id="2dde6-104">Obtiene un puntero a la cadena de la que forma parte este marco.</span><span class="sxs-lookup"><span data-stu-id="2dde6-104">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dde6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2dde6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dde6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2dde6-106">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="2dde6-107">enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena que contiene este marco.</span><span class="sxs-lookup"><span data-stu-id="2dde6-107">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dde6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2dde6-108">Requirements</span></span>  

 <span data-ttu-id="2dde6-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2dde6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dde6-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2dde6-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2dde6-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dde6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dde6-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dde6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
