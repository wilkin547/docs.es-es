---
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
ms.openlocfilehash: 7da12554ba1db9a467aa03c01bfb3b584125b129
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213197"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="fca7a-102">ICorDebugFunction2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="fca7a-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="fca7a-103">Marca la función representada por este ICorDebugFunction2 para Solo mi código Stepping.</span><span class="sxs-lookup"><span data-stu-id="fca7a-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fca7a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fca7a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fca7a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fca7a-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="fca7a-106">de Establezca en `true` para marcar la función como código de usuario; de lo contrario, establézcalo en `false` .</span><span class="sxs-lookup"><span data-stu-id="fca7a-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="fca7a-107">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="fca7a-107">Return Values</span></span>  
  
|<span data-ttu-id="fca7a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fca7a-108">HRESULT</span></span>|<span data-ttu-id="fca7a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="fca7a-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fca7a-110">La función se marcó correctamente.</span><span class="sxs-lookup"><span data-stu-id="fca7a-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="fca7a-111">No se pudo marcar la función como código de usuario porque no se puede depurar.</span><span class="sxs-lookup"><span data-stu-id="fca7a-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fca7a-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fca7a-112">Remarks</span></span>  
 <span data-ttu-id="fca7a-113">Una Solo mi código stepper omitirá el código que no es de usuario.</span><span class="sxs-lookup"><span data-stu-id="fca7a-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="fca7a-114">El código de usuario debe ser un subconjunto del código depurable.</span><span class="sxs-lookup"><span data-stu-id="fca7a-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fca7a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fca7a-115">Requirements</span></span>  
 <span data-ttu-id="fca7a-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fca7a-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fca7a-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fca7a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fca7a-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fca7a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fca7a-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fca7a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
