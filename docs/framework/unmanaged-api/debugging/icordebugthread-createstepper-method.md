---
description: 'Más información acerca de: ICorDebugThread:: Createstepper ((método)'
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
ms.openlocfilehash: 378ce28281f4f284c36194f993a53598a9de3854
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659366"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="d6fe7-103">ICorDebugThread::CreateStepper (Método)</span><span class="sxs-lookup"><span data-stu-id="d6fe7-103">ICorDebugThread::CreateStepper Method</span></span>

<span data-ttu-id="d6fe7-104">Crea un objeto ICorDebugStepper que permite recorrer en iteración el marco activo de esta expresión ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="d6fe7-104">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6fe7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6fe7-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6fe7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6fe7-106">Parameters</span></span>  

 `ppStepper`  
 <span data-ttu-id="d6fe7-107">enuncia Puntero a la dirección de un `ICorDebugStepper` objeto que permite recorrer en iteración el marco activo de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="d6fe7-107">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6fe7-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d6fe7-108">Remarks</span></span>  

 <span data-ttu-id="d6fe7-109">El marco activo puede ser código no administrado.</span><span class="sxs-lookup"><span data-stu-id="d6fe7-109">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="d6fe7-110">La `ICorDebugStepper` interfaz se debe utilizar para realizar la ejecución de paso real.</span><span class="sxs-lookup"><span data-stu-id="d6fe7-110">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6fe7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6fe7-111">Requirements</span></span>  

 <span data-ttu-id="d6fe7-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6fe7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6fe7-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6fe7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6fe7-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6fe7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6fe7-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6fe7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
