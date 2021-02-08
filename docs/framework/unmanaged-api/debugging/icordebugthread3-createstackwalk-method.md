---
description: 'Más información sobre: ICorDebugThread3:: CreateStackWalk ((método)'
title: ICorDebugThread3::CreateStackWalk (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: b36252160dbad14ca1bee0674b6d042072a36359
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800999"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="6ccb1-103">ICorDebugThread3::CreateStackWalk (Método)</span><span class="sxs-lookup"><span data-stu-id="6ccb1-103">ICorDebugThread3::CreateStackWalk Method</span></span>

<span data-ttu-id="6ccb1-104">Crea un objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="6ccb1-104">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ccb1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ccb1-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ccb1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6ccb1-106">Parameters</span></span>  

 `ppStackWalk`  
 <span data-ttu-id="6ccb1-107">enuncia Puntero a la dirección del objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="6ccb1-107">[out] A pointer to address of the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ccb1-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6ccb1-108">Return Value</span></span>  

 <span data-ttu-id="6ccb1-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="6ccb1-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6ccb1-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6ccb1-110">HRESULT</span></span>|<span data-ttu-id="6ccb1-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ccb1-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ccb1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ccb1-112">S_OK</span></span>|<span data-ttu-id="6ccb1-113">El `ICorDebugStackWalk` objeto se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="6ccb1-113">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="6ccb1-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6ccb1-114">E_FAIL</span></span>|<span data-ttu-id="6ccb1-115">`ICorDebugStackWalk`No se creó el objeto.</span><span class="sxs-lookup"><span data-stu-id="6ccb1-115">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="6ccb1-116">Excepciones</span><span class="sxs-lookup"><span data-stu-id="6ccb1-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ccb1-117">Notas</span><span class="sxs-lookup"><span data-stu-id="6ccb1-117">Remarks</span></span>  

 <span data-ttu-id="6ccb1-118">Si el `CreateStackWalk` método se ejecuta correctamente, el `ICorDebugStackWalk` contexto del objeto devuelto se establece en el contexto actual del subproceso.</span><span class="sxs-lookup"><span data-stu-id="6ccb1-118">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ccb1-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ccb1-119">Requirements</span></span>  

 <span data-ttu-id="6ccb1-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ccb1-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ccb1-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ccb1-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ccb1-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ccb1-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ccb1-123">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ccb1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ccb1-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ccb1-124">See also</span></span>

- [<span data-ttu-id="6ccb1-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="6ccb1-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6ccb1-126">Depuración</span><span class="sxs-lookup"><span data-stu-id="6ccb1-126">Debugging</span></span>](index.md)
