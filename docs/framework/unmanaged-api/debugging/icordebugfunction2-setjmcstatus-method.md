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
ms.openlocfilehash: 15b102be5a792f982edeb320199576bdddbd859a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412365"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="e8f8c-102">ICorDebugFunction2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="e8f8c-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="e8f8c-103">Marca la función representada por esta instancia de ICorDebugFunction2 para solo mi código ejecución paso a paso.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8f8c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8f8c-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8f8c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8f8c-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="e8f8c-106">[in] Establecido en `true` para marcar la función como código de usuario; de lo contrario, establézcalo en `false`.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="e8f8c-107">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="e8f8c-107">Return Values</span></span>  
  
|<span data-ttu-id="e8f8c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e8f8c-108">HRESULT</span></span>|<span data-ttu-id="e8f8c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8f8c-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e8f8c-110">La función se ha marcado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="e8f8c-111">La función no se pudieron marcar como código de usuario porque no se pueden depurar.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8f8c-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e8f8c-112">Remarks</span></span>  
 <span data-ttu-id="e8f8c-113">Un paso a paso desencadene solo mi código omitirá el código de no usuario.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="e8f8c-114">Código de usuario debe ser un subconjunto del código depurable.</span><span class="sxs-lookup"><span data-stu-id="e8f8c-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8f8c-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8f8c-115">Requirements</span></span>  
 <span data-ttu-id="e8f8c-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8f8c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8f8c-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8f8c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8f8c-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8f8c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8f8c-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8f8c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
