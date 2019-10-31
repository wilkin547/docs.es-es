---
title: ICorDebugThread::CreateStepper (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
ms.openlocfilehash: d1b058aef66ed32c2cadcc3cfd72320dd8eb7729
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133592"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="fd43a-102">ICorDebugThread::CreateStepper (Método)</span><span class="sxs-lookup"><span data-stu-id="fd43a-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="fd43a-103">Crea un objeto ICorDebugStepper que permite recorrer en iteración el marco activo de esta expresión ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="fd43a-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd43a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd43a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd43a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd43a-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="fd43a-106">enuncia Puntero a la dirección de un objeto `ICorDebugStepper` que permite recorrer en iteración el marco activo de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="fd43a-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd43a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd43a-107">Remarks</span></span>  
 <span data-ttu-id="fd43a-108">El marco activo puede ser código no administrado.</span><span class="sxs-lookup"><span data-stu-id="fd43a-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="fd43a-109">La interfaz de `ICorDebugStepper` debe usarse para realizar la ejecución de paso real.</span><span class="sxs-lookup"><span data-stu-id="fd43a-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd43a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd43a-110">Requirements</span></span>  
 <span data-ttu-id="fd43a-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd43a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd43a-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd43a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd43a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd43a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd43a-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd43a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
