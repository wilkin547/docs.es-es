---
title: ICorDebugFunction::GetNativeCode (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
ms.openlocfilehash: 98aee38415709974d84873df50c39263490f2f23
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213275"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="c538d-102">ICorDebugFunction::GetNativeCode (Método)</span><span class="sxs-lookup"><span data-stu-id="c538d-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="c538d-103">Obtiene el código nativo para la función representada por esta instancia de ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="c538d-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c538d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c538d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c538d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c538d-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="c538d-106">enuncia Un puntero a la instancia de ICorDebugCode que representa el código nativo de esta función, o null, si esta función es código del lenguaje intermedio de Microsoft (MSIL) que no se ha compilado Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="c538d-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c538d-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c538d-107">Remarks</span></span>  
 <span data-ttu-id="c538d-108">Si la función representada por esta `ICorDebugFunction` instancia se ha compilado JIT más de una vez, como en el caso de los tipos genéricos, `GetNativeCode` devuelve un objeto de código nativo aleatorio.</span><span class="sxs-lookup"><span data-stu-id="c538d-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c538d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c538d-109">Requirements</span></span>  
 <span data-ttu-id="c538d-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c538d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c538d-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c538d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c538d-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c538d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c538d-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c538d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
