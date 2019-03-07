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
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470177"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="26e57-102">ICorDebugFunction::GetNativeCode (Método)</span><span class="sxs-lookup"><span data-stu-id="26e57-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="26e57-103">Obtiene el código nativo para la función representada por esta instancia ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="26e57-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26e57-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26e57-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26e57-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26e57-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="26e57-106">[out] Un puntero a la instancia de ICorDebugCode que representa el código nativo para esta función, o null, si esta función es código de lenguaje intermedio (MSIL) de Microsoft que no se ha compilado just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="26e57-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26e57-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26e57-107">Remarks</span></span>  
 <span data-ttu-id="26e57-108">Si la función que está representada por este `ICorDebugFunction` instancia ha sido compilado JIT varias veces, como en el caso de tipos genéricos, `GetNativeCode` devuelve un objeto de código nativo aleatorio.</span><span class="sxs-lookup"><span data-stu-id="26e57-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26e57-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26e57-109">Requirements</span></span>  
 <span data-ttu-id="26e57-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26e57-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26e57-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26e57-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26e57-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26e57-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26e57-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26e57-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
