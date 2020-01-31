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
ms.openlocfilehash: 64f6bc9abb8105cdfa942c2aaca71994e8a91765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791412"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="09483-102">ICorDebugThread3::CreateStackWalk (Método)</span><span class="sxs-lookup"><span data-stu-id="09483-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="09483-103">Crea un objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="09483-103">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09483-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09483-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09483-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="09483-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="09483-106">enuncia Puntero a la dirección del objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="09483-106">[out] A pointer to address of the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09483-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="09483-107">Return Value</span></span>  
 <span data-ttu-id="09483-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="09483-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="09483-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09483-109">HRESULT</span></span>|<span data-ttu-id="09483-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="09483-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09483-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="09483-111">S_OK</span></span>|<span data-ttu-id="09483-112">El objeto de `ICorDebugStackWalk` se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="09483-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="09483-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09483-113">E_FAIL</span></span>|<span data-ttu-id="09483-114">No se creó el objeto de `ICorDebugStackWalk`.</span><span class="sxs-lookup"><span data-stu-id="09483-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="09483-115">Excepciones</span><span class="sxs-lookup"><span data-stu-id="09483-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09483-116">Notas</span><span class="sxs-lookup"><span data-stu-id="09483-116">Remarks</span></span>  
 <span data-ttu-id="09483-117">Si el método de `CreateStackWalk` se ejecuta correctamente, el contexto del objeto de `ICorDebugStackWalk` devuelto se establece en el contexto actual del subproceso.</span><span class="sxs-lookup"><span data-stu-id="09483-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09483-118">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="09483-118">Requirements</span></span>  
 <span data-ttu-id="09483-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09483-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09483-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09483-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09483-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09483-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09483-122">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09483-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09483-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="09483-123">See also</span></span>

- [<span data-ttu-id="09483-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="09483-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="09483-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="09483-125">Debugging</span></span>](index.md)
