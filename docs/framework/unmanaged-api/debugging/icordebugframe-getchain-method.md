---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 032c1e3dcfe50cd30953ca581ff9f0d83b78518d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995870"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="df859-102">ICorDebugFrame::GetChain (Método)</span><span class="sxs-lookup"><span data-stu-id="df859-102">ICorDebugFrame::GetChain Method</span></span>
<span data-ttu-id="df859-103">Obtiene un puntero a la cadena de de que este marco es una parte.</span><span class="sxs-lookup"><span data-stu-id="df859-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df859-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df859-104">Syntax</span></span>  
  
```  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df859-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df859-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="df859-106">[out] Un puntero a la dirección de un objeto ICorDebugChain que representa la cadena que contiene este marco.</span><span class="sxs-lookup"><span data-stu-id="df859-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df859-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df859-107">Requirements</span></span>  
 <span data-ttu-id="df859-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df859-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df859-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df859-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df859-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df859-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df859-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df859-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
