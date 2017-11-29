---
title: "ICorDebugChain::GetCallee (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetCallee
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ed2bf8d8e91799fd0b01012d5d6e212d26a526be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="c3efb-102">ICorDebugChain::GetCallee (Método)</span><span class="sxs-lookup"><span data-stu-id="c3efb-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="c3efb-103">Obtiene la cadena que se llama a esta cadena.</span><span class="sxs-lookup"><span data-stu-id="c3efb-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3efb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3efb-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3efb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3efb-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="c3efb-106">[out] Un puntero a la dirección de un objeto ICorDebugChain que representa la cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="c3efb-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="c3efb-107">Si esta cadena se está ejecutando actualmente (es decir, si esta cadena no está esperando una cadena de llamada devolver), `ppChain` será null.</span><span class="sxs-lookup"><span data-stu-id="c3efb-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3efb-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3efb-108">Remarks</span></span>  
 <span data-ttu-id="c3efb-109">Esta cadena esperará la cadena de llamada devolver antes de que reanuda la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c3efb-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="c3efb-110">La cadena de llamada puede estar en otro subproceso en el caso de llamadas de calcular las referencias entre subprocesos.</span><span class="sxs-lookup"><span data-stu-id="c3efb-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3efb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3efb-111">Requirements</span></span>  
 <span data-ttu-id="c3efb-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3efb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3efb-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3efb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3efb-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3efb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3efb-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3efb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
