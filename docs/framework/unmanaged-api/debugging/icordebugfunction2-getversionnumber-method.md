---
title: ICorDebugFunction2::GetVersionNumber (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdd2151c4886959647de4f9e27a20a93ffc07429
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420058"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="69bec-102">ICorDebugFunction2::GetVersionNumber (Método)</span><span class="sxs-lookup"><span data-stu-id="69bec-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="69bec-103">Obtiene la versión de editar y continuar de esta función.</span><span class="sxs-lookup"><span data-stu-id="69bec-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69bec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69bec-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69bec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69bec-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="69bec-106">[out] Un puntero a un entero que es el número de versión de la función que está representado por este objeto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="69bec-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69bec-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69bec-107">Remarks</span></span>  
 <span data-ttu-id="69bec-108">El tiempo de ejecución realiza un seguimiento del número de modificaciones que han tenido lugar para cada módulo durante una sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="69bec-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="69bec-109">El número de versión de una función es uno más que el número de la edición que introdujo la función.</span><span class="sxs-lookup"><span data-stu-id="69bec-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="69bec-110">Versión original de la función es 1.</span><span class="sxs-lookup"><span data-stu-id="69bec-110">The function's original version is version 1.</span></span> <span data-ttu-id="69bec-111">El número se incrementa cada vez para un módulo [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) se llama en ese módulo.</span><span class="sxs-lookup"><span data-stu-id="69bec-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="69bec-112">Por lo tanto, si se reemplaza el cuerpo de una función en la primera y la tercera llamada a `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` puede devolver la versión 1, 2 o 4 de esa función, pero no la versión 3.</span><span class="sxs-lookup"><span data-stu-id="69bec-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="69bec-113">(Esa función no tendría versión 3.)</span><span class="sxs-lookup"><span data-stu-id="69bec-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="69bec-114">El número de versión se realiza un seguimiento por separado para cada módulo.</span><span class="sxs-lookup"><span data-stu-id="69bec-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="69bec-115">Por lo tanto, si lleva a cabo cuatro modificaciones en el módulo 1 y ninguna en el módulo 2, la siguiente modificación en el módulo 1 asignará a un número de versión de 6 a todas las funciones modificadas en el módulo 1.</span><span class="sxs-lookup"><span data-stu-id="69bec-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="69bec-116">Si la misma modificación afecta al módulo 2, las funciones en el módulo 2 obtendrá un número de versión de 2.</span><span class="sxs-lookup"><span data-stu-id="69bec-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="69bec-117">Obtiene el número de versión del `GetVersionNumber` método puede ser inferior al obtenido por [ICorDebugFunction:: GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span><span class="sxs-lookup"><span data-stu-id="69bec-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="69bec-118">El [ICorDebugCode:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) método realiza la misma operación que `ICorDebugFunction2::GetVersionNumber`.</span><span class="sxs-lookup"><span data-stu-id="69bec-118">The [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69bec-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69bec-119">Requirements</span></span>  
 <span data-ttu-id="69bec-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69bec-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69bec-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69bec-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69bec-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69bec-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69bec-123">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69bec-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
