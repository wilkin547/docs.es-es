---
title: "ICorDebugFunction2::SetJMCStatus (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ecbcd5b8171a169fbfdd7175d3d9dfbbcb3855f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="272a1-102">ICorDebugFunction2::SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="272a1-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="272a1-103">Marca la función representada por esta instancia de ICorDebugFunction2 para solo mi código ejecución paso a paso.</span><span class="sxs-lookup"><span data-stu-id="272a1-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="272a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="272a1-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="272a1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="272a1-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="272a1-106">[in] Establecido en `true` para marcar la función como código de usuario; de lo contrario, establézcalo en `false`.</span><span class="sxs-lookup"><span data-stu-id="272a1-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="272a1-107">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="272a1-107">Return Values</span></span>  
  
|<span data-ttu-id="272a1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="272a1-108">HRESULT</span></span>|<span data-ttu-id="272a1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="272a1-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="272a1-110">La función se ha marcado correctamente.</span><span class="sxs-lookup"><span data-stu-id="272a1-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="272a1-111">La función no se pudieron marcar como código de usuario porque no se pueden depurar.</span><span class="sxs-lookup"><span data-stu-id="272a1-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="272a1-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="272a1-112">Remarks</span></span>  
 <span data-ttu-id="272a1-113">Un paso a paso desencadene solo mi código omitirá el código de no usuario.</span><span class="sxs-lookup"><span data-stu-id="272a1-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="272a1-114">Código de usuario debe ser un subconjunto del código depurable.</span><span class="sxs-lookup"><span data-stu-id="272a1-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="272a1-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="272a1-115">Requirements</span></span>  
 <span data-ttu-id="272a1-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="272a1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="272a1-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="272a1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="272a1-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="272a1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="272a1-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="272a1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
