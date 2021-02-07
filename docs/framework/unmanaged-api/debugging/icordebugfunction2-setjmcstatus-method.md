---
description: 'Más información acerca de: ICorDebugFunction2:: Setjmcstatus ((método)'
title: ICorDebugFunction2::SetJMCStatus (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
ms.openlocfilehash: d2df9d47808b0220a91bd344e7600f8d16eccdb4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692196"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="23f30-103">ICorDebugFunction2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="23f30-103">ICorDebugFunction2::SetJMCStatus Method</span></span>

<span data-ttu-id="23f30-104">Marca la función representada por este ICorDebugFunction2 para Solo mi código Stepping.</span><span class="sxs-lookup"><span data-stu-id="23f30-104">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23f30-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23f30-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23f30-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23f30-106">Parameters</span></span>  

 `bIsJustMyCode`  
 <span data-ttu-id="23f30-107">de Establezca en `true` para marcar la función como código de usuario; de lo contrario, establézcalo en `false` .</span><span class="sxs-lookup"><span data-stu-id="23f30-107">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="23f30-108">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="23f30-108">Return Values</span></span>  
  
|<span data-ttu-id="23f30-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23f30-109">HRESULT</span></span>|<span data-ttu-id="23f30-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="23f30-110">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="23f30-111">La función se marcó correctamente.</span><span class="sxs-lookup"><span data-stu-id="23f30-111">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="23f30-112">No se pudo marcar la función como código de usuario porque no se puede depurar.</span><span class="sxs-lookup"><span data-stu-id="23f30-112">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23f30-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="23f30-113">Remarks</span></span>  

 <span data-ttu-id="23f30-114">Una Solo mi código stepper omitirá el código que no es de usuario.</span><span class="sxs-lookup"><span data-stu-id="23f30-114">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="23f30-115">El código de usuario debe ser un subconjunto del código depurable.</span><span class="sxs-lookup"><span data-stu-id="23f30-115">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23f30-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23f30-116">Requirements</span></span>  

 <span data-ttu-id="23f30-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23f30-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23f30-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23f30-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23f30-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23f30-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23f30-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23f30-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
