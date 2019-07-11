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
ms.openlocfilehash: 89cf2a12b0a693bbed3e8a3c1134d0f2b2a72a30
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754451"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="dd537-102">ICorDebugFunction2::GetVersionNumber (Método)</span><span class="sxs-lookup"><span data-stu-id="dd537-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="dd537-103">Obtiene la versión de editar y continuar de esta función.</span><span class="sxs-lookup"><span data-stu-id="dd537-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd537-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd537-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd537-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dd537-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="dd537-106">[out] Un puntero a un entero que es el número de versión de la función representada por este objeto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="dd537-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd537-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dd537-107">Remarks</span></span>  
 <span data-ttu-id="dd537-108">El tiempo de ejecución realiza un seguimiento de la cantidad de modificaciones que han tenido lugar para cada módulo durante una sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="dd537-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="dd537-109">El número de versión de una función es uno más que el número de la edición que introdujo la función.</span><span class="sxs-lookup"><span data-stu-id="dd537-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="dd537-110">Versión original de la función es 1.</span><span class="sxs-lookup"><span data-stu-id="dd537-110">The function's original version is version 1.</span></span> <span data-ttu-id="dd537-111">El número se incrementa cada vez para un módulo [Icordebugmodule2](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) se llama en ese módulo.</span><span class="sxs-lookup"><span data-stu-id="dd537-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="dd537-112">Por lo tanto, si se ha reemplazado el cuerpo de una función en la primera y tercera llamada a `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` puede devolver la versión 1, 2 ó 4 para esa función, pero no la versión 3.</span><span class="sxs-lookup"><span data-stu-id="dd537-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="dd537-113">(Esa función no tendría ninguna versión 3).</span><span class="sxs-lookup"><span data-stu-id="dd537-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="dd537-114">El número de versión se realiza un seguimiento por separado para cada módulo.</span><span class="sxs-lookup"><span data-stu-id="dd537-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="dd537-115">Por lo tanto, si realizar cuatro modificaciones en el módulo 1 y ninguna en el módulo 2, la siguiente modificación en el módulo 1 asignará a un número de versión de 6 a todas las funciones modificadas en el módulo 1.</span><span class="sxs-lookup"><span data-stu-id="dd537-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="dd537-116">Si la misma modificación afecta al módulo 2, las funciones del módulo 2 obtendrá un número de versión 2.</span><span class="sxs-lookup"><span data-stu-id="dd537-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="dd537-117">Obtiene el número de versión por el `GetVersionNumber` método puede ser inferior al que obtiene al [ICorDebugFunction:: GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span><span class="sxs-lookup"><span data-stu-id="dd537-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="dd537-118">El [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) método realiza la misma operación que `ICorDebugFunction2::GetVersionNumber`.</span><span class="sxs-lookup"><span data-stu-id="dd537-118">The [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd537-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd537-119">Requirements</span></span>  
 <span data-ttu-id="dd537-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd537-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd537-121">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd537-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd537-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd537-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd537-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd537-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
