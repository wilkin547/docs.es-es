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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb85c4b2c26c136a5f9fc05221a42c4bc99f37f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988707"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="70f51-102">ICorDebugFunction::GetNativeCode (Método)</span><span class="sxs-lookup"><span data-stu-id="70f51-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="70f51-103">Obtiene el código nativo para la función representada por esta instancia ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="70f51-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70f51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70f51-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70f51-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70f51-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="70f51-106">[out] Un puntero a la instancia de ICorDebugCode que representa el código nativo para esta función, o null, si esta función es código de lenguaje intermedio (MSIL) de Microsoft que no se ha compilado just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="70f51-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70f51-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="70f51-107">Remarks</span></span>  
 <span data-ttu-id="70f51-108">Si la función que está representada por este `ICorDebugFunction` instancia ha sido compilado JIT varias veces, como en el caso de tipos genéricos, `GetNativeCode` devuelve un objeto de código nativo aleatorio.</span><span class="sxs-lookup"><span data-stu-id="70f51-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70f51-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70f51-109">Requirements</span></span>  
 <span data-ttu-id="70f51-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70f51-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70f51-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70f51-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70f51-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70f51-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70f51-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70f51-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
