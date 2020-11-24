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
ms.openlocfilehash: dcaa5adc41a9e451b123b088dd900f01d9161689
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688282"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="5919e-102">ICorDebugThread::CreateStepper (Método)</span><span class="sxs-lookup"><span data-stu-id="5919e-102">ICorDebugThread::CreateStepper Method</span></span>

<span data-ttu-id="5919e-103">Crea un objeto ICorDebugStepper que permite recorrer en iteración el marco activo de esta expresión ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="5919e-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5919e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5919e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5919e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5919e-105">Parameters</span></span>  

 `ppStepper`  
 <span data-ttu-id="5919e-106">enuncia Puntero a la dirección de un `ICorDebugStepper` objeto que permite recorrer en iteración el marco activo de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="5919e-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5919e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5919e-107">Remarks</span></span>  

 <span data-ttu-id="5919e-108">El marco activo puede ser código no administrado.</span><span class="sxs-lookup"><span data-stu-id="5919e-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="5919e-109">La `ICorDebugStepper` interfaz se debe utilizar para realizar la ejecución de paso real.</span><span class="sxs-lookup"><span data-stu-id="5919e-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5919e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5919e-110">Requirements</span></span>  

 <span data-ttu-id="5919e-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5919e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5919e-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5919e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5919e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5919e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5919e-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5919e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
