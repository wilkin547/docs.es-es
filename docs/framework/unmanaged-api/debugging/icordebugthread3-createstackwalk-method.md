---
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
ms.openlocfilehash: f2850e6c9cbb2250a08ab4a0e34c69e377d3a23d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375848"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="2d68e-102">ICorDebugThread3::CreateStackWalk (Método)</span><span class="sxs-lookup"><span data-stu-id="2d68e-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="2d68e-103">Crea un objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="2d68e-103">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d68e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d68e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d68e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d68e-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="2d68e-106">enuncia Puntero a la dirección del objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="2d68e-106">[out] A pointer to address of the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d68e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2d68e-107">Return Value</span></span>  
 <span data-ttu-id="2d68e-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="2d68e-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2d68e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d68e-109">HRESULT</span></span>|<span data-ttu-id="2d68e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d68e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d68e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d68e-111">S_OK</span></span>|<span data-ttu-id="2d68e-112">El `ICorDebugStackWalk` objeto se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="2d68e-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="2d68e-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2d68e-113">E_FAIL</span></span>|<span data-ttu-id="2d68e-114">`ICorDebugStackWalk`No se creó el objeto.</span><span class="sxs-lookup"><span data-stu-id="2d68e-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="2d68e-115">Excepciones</span><span class="sxs-lookup"><span data-stu-id="2d68e-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d68e-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2d68e-116">Remarks</span></span>  
 <span data-ttu-id="2d68e-117">Si el `CreateStackWalk` método se ejecuta correctamente, el `ICorDebugStackWalk` contexto del objeto devuelto se establece en el contexto actual del subproceso.</span><span class="sxs-lookup"><span data-stu-id="2d68e-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d68e-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d68e-118">Requirements</span></span>  
 <span data-ttu-id="2d68e-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d68e-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d68e-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d68e-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d68e-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d68e-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d68e-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d68e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d68e-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d68e-123">See also</span></span>

- [<span data-ttu-id="2d68e-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2d68e-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2d68e-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="2d68e-125">Debugging</span></span>](index.md)
