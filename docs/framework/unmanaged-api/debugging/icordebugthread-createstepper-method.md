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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95a00e8646589e7897636c1698b7c2647cd233fd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771801"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="8f976-102">ICorDebugThread::CreateStepper (Método)</span><span class="sxs-lookup"><span data-stu-id="8f976-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="8f976-103">Crea un objeto ICorDebugStepper que permite recorrer el marco activo de esta instancia de ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="8f976-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f976-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f976-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f976-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f976-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="8f976-106">[out] Un puntero a la dirección de un `ICorDebugStepper` objeto que permite recorrer el fotograma activo de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="8f976-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f976-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f976-107">Remarks</span></span>  
 <span data-ttu-id="8f976-108">El marco activo puede ser código no administrado.</span><span class="sxs-lookup"><span data-stu-id="8f976-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="8f976-109">El `ICorDebugStepper` interfaz se debe usar para realizar el recorrido en Sí.</span><span class="sxs-lookup"><span data-stu-id="8f976-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f976-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f976-110">Requirements</span></span>  
 <span data-ttu-id="8f976-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f976-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f976-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f976-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f976-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f976-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f976-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f976-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
