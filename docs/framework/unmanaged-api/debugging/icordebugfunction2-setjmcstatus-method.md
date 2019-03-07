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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49ced1b4be888c7550c3927d1b319ab2f0bef086
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501011"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="7487f-102">ICorDebugFunction2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="7487f-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="7487f-103">Marca la función representada por este ICorDebugFunction2 solo mi código para la ejecución paso a paso.</span><span class="sxs-lookup"><span data-stu-id="7487f-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7487f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7487f-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7487f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7487f-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="7487f-106">[in] Establecido en `true` para marcar la función como código de usuario; de lo contrario, establézcalo en `false`.</span><span class="sxs-lookup"><span data-stu-id="7487f-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="7487f-107">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="7487f-107">Return Values</span></span>  
  
|<span data-ttu-id="7487f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7487f-108">HRESULT</span></span>|<span data-ttu-id="7487f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7487f-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7487f-110">La función se ha marcado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7487f-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="7487f-111">La función no se pudieron marcar como código de usuario porque no se pueden depurar.</span><span class="sxs-lookup"><span data-stu-id="7487f-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7487f-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7487f-112">Remarks</span></span>  
 <span data-ttu-id="7487f-113">Un motor paso a paso solo mi código omitirá el código de no usuario.</span><span class="sxs-lookup"><span data-stu-id="7487f-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="7487f-114">Código de usuario debe ser un subconjunto del código depurable.</span><span class="sxs-lookup"><span data-stu-id="7487f-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7487f-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7487f-115">Requirements</span></span>  
 <span data-ttu-id="7487f-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7487f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7487f-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7487f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7487f-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7487f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7487f-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7487f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
